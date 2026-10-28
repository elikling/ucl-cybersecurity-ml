# Web Server Anomaly Detection Dataset

Real web-server traffic from a small, volunteer-run UK leisure/ecommerce site
(identity genericized — see Anonymization), covering **2026-09-06 to
2026-10-07** (31 days), with ground-truth attack labels derived from a live
intrusion-prevention system (fail2ban) running against the same traffic.

## Files

- `access_log.csv` — one row per HTTP request (129,145 rows).
  Columns: `timestamp, ip_id, method, path, protocol, status, bytes, referrer, user_agent, ip_ever_flagged_by_fail2ban`
- `error_log.csv` — Apache error log entries (6,452 rows): module, client, message.
- `attack_labels.csv` — ground-truth attack episodes (1,155 rows).
  Columns: `ban_time, unban_time, ip_id, jail, category`
- `raw_sanitized/access.log`, `raw_sanitized/error.log` — the same data in
  original Apache combined-log / error-log text format, for anyone who wants
  to practice log parsing from scratch rather than starting from the CSV.

## Ground-truth labels: how they were derived

The source host runs fail2ban with several purpose-built jails that watch the
access/error logs in real time and ban an IP once it crosses a threshold
(e.g. 10+ requests for non-existent pages within 10 minutes). Every `Ban` /
`Unban` event is in `attack_labels.csv` with the exact time window the IP was
considered hostile. `access_log.csv.ip_ever_flagged_by_fail2ban` is a coarse
per-IP version of the same signal (true if that IP was *ever* banned,
regardless of which specific request). For a tighter, time-windowed label,
join `access_log.csv.timestamp` against `[ban_time, unban_time]` per `ip_id`
in `attack_labels.csv`.

**Category breakdown** (ban episodes):

| category | jail | count |
|---|---|---|
| forbidden_path_scan | apache-403-scan | 614 |
| missing_page_scan | apache-404-scan | 394 |
| ssh_bruteforce | sshd | 55 |
| repeat_offender_escalation | recidive | 52 |
| wp_login_bruteforce | wordpress-login | 37 |
| xmlrpc_abuse | wordpress-xmlrpc | 2 |
| bad_bot_useragent | apache-badbots | 1 |

Unique attacker IPs: 743. Total unique IPs seen in the window: 7,607 — so
roughly **1 in 10 distinct visitors was, at some point, an attacker** by this
definition. That imbalance (and the fact it's measured per-IP, not
per-request) is itself worth discussing in a report: per-request class
balance is far more skewed, since each attacker IP typically fires many
requests in a burst.

**Important caveat for the project**: these labels are *fail2ban's own rule
thresholds*, not an independent ground truth. They're a reasonable proxy for
"known attack" training cases, but:
- They will miss low-and-slow attacks that never cross a jail's threshold
  (a genuine blind spot worth discussing — what would a good anomaly
  detector catch that this rule-based system didn't?).
- `ssh_bruteforce` labels are on a *different port/service* (SSH, not HTTP)
  and won't correlate with rows in `access_log.csv` — useful as a separate
  mini-dataset, not for request-level HTTP anomaly features.
- `recidive` is a meta-jail (it watches fail2ban's own ban history for
  repeat offenders), not an independent detection — treat it as a severity
  escalation flag on an IP already caught elsewhere, not a new attack type.

## Anonymization

This dataset is derived from a real production website and was sanitized
before leaving the organization:

1. **Every client IP** (attacker and genuine visitor alike) is replaced with
   a consistent pseudonymous token (`ip_xxxxxxxxxx`, from an HMAC-SHA256 of
   the real IP with a random per-export salt that was discarded after
   generating this dataset — the mapping cannot be reversed). The same real
   IP always maps to the same token everywhere in this dataset, which
   preserves exactly the behavioral patterns (burst frequency, repeat
   visits, breadth of paths touched) that matter for anomaly detection.
2. **The real site identity** (domain name, server's public IP/hostname) is
   replaced with placeholder values (`www.example-leisurecentre.test`,
   `203.0.113.10` — an RFC 5737 documentation-only IP range).
3. **Secret/capability tokens** embedded in URLs (order-view keys, cron
   keys, signatures, nonces, an uptime-monitor check endpoint slug, and any
   other long random-looking hex string in a path) are redacted to
   `REDACTED` / `REDACTEDTOKEN`, since these could otherwise grant access to
   real resources or reveal the real site's monitoring setup.
4. **Email addresses** (mostly bot/crawler self-identification strings in
   User-Agent headers, e.g. `+bot@example.com`) are replaced with a single
   placeholder.
5. Apache's combined log format doesn't capture POST bodies, so no
   passwords or usernames typed into login forms are present in these logs
   to begin with.

## Suggested starting points for the project

- **Feature engineering per IP / per time-window**: requests-per-minute,
  unique paths touched, 404-rate, status-code entropy, path-string entropy
  or n-gram rarity, user-agent rarity, inter-request timing (burstiness vs.
  human browsing rhythm), ratio of requests with a referrer vs. none.
- **Framing choices worth comparing**: point-anomaly detection on individual
  requests vs. contextual/collective anomaly detection on a sliding window
  per IP — the two fail2ban jail types (`403/404-scan` = collective
  behavior over many requests; a single request alone usually isn't
  anomalous) map naturally onto this distinction.
- **Classical baselines to compare against modern tabular models (e.g.
  TabPFN)**: robust z-score / EWMA on request rate, Isolation Forest,
  Local Outlier Factor, on the same engineered feature table — gives a
  concrete "did the fancy model actually beat the simple one" result.
- **Known limitation to discuss in the writeup**: training/evaluating
  against fail2ban's own rule-based labels risks just re-learning those
  rules. A stronger project would also hold out a subset of *unlabeled*
  traffic and manually eyeball whatever the model flags as anomalous that
  fail2ban didn't — that's where a genuinely novel detector would show its
  value.
