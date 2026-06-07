# Usage Sync & Metric Billing

### PUQ Web Hosting module **[WHMCS](https://puqcloud.com/link.php?id=77)**
#####  [Order now](https://puqcloud.com/whmcs-module-web-hosting.php) | [Download](https://download.puqcloud.com/WHMCS/servers/PUQ_WHMCS-WEB-Hosting/) | [Community](https://community.puqcloud.com/)

The module keeps live resource figures (disk, bandwidth, mailboxes, databases…) in the local database so both the admin and client areas render instantly, and it feeds WHMCS metric billing.

## Per‑server batch sync

Usage is collected **per server**, not per service. A `server.syncUsage` worker lists all users on a node in one shot and recomputes every service on it, turning what used to be N × several SSH calls into one batch call per server. The cron schedules these per‑server jobs; **Refresh all**, **Force sync** and bulk actions all enqueue the same per‑server task.

## Statistics page

The addon **Statistics** page reads purely from the database (no SSH at render time): an aggregate summary plus a per‑service usage DataTable, with **Refresh all usage** to enqueue a fresh collection.

## Metric billing

The module exposes usage to WHMCS's **MetricProvider**, so you can bill on actual consumption (e.g. disk or bandwidth over an included allowance) in addition to flat plan pricing. The figures billed are the same ones shown in the client dashboard gauges.

> A customer can pull fresh numbers on demand with **Sync now** on their dashboard; it enqueues the recompute→sync chain for just their service.
