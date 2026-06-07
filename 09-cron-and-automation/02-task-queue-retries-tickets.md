# Task Queue, Retries & Tickets

### PUQ Web Hosting module **[WHMCS](https://puqcloud.com/link.php?id=77)**
#####  [Order now](https://puqcloud.com/whmcs-module-web-hosting.php) | [Download](https://download.puqcloud.com/WHMCS/servers/PUQ_WHMCS-WEB-Hosting/) | [FAQ](https://faq.puqcloud.com/)

Every action — deploys, client‑area changes, status collection, SSL, usage sync — is a row in the task queue, processed by the cron runner.

## How a task runs

1. The cron runner picks up due tasks (respecting per‑server concurrency limits and the **batch size** per run).
2. Each task is dispatched to its **target server** (critical for the DNS active‑active cluster — a task carries its `server_id`).
3. On success the row is marked done; on failure it's scheduled for **retry**.

## Retry & back‑off

The retry policy lives in **Settings → General**:

* **Max attempts** — how many times a failing task retries.
* **Back‑off minutes** — growing delay between attempts, so a flaky node isn't hammered.

A task that exhausts its attempts is marked **error** and stops retrying.

## Failure tickets

When **Settings → Notifications → failure ticket** is enabled, a task that fails terminally opens (or notes on) a WHMCS **support ticket** in the chosen department/priority, so staff are alerted without watching the queue. Subsequent failures on the same operation append a note rather than spamming new tickets.

## Watching & cleaning up

The addon **Logs → Task Queue** page shows the live queue with bulk controls (delete success/error/cancelled, clean completed, **force‑fail stuck**). **Logs → Operation Log** keeps the persistent history. See **Addon Module → Task Queue & Logs**.

> Stuck tasks (node permanently gone) can be cleared with **Force‑fail stuck**; the matching **Verify & Repair** on the service then rebuilds whatever's missing.
