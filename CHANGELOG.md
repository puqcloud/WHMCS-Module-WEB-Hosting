# Changelog

## v1.0 — first release

Full HestiaCP web + email hosting automation for WHMCS.

**Provisioning & infrastructure**
- Asynchronous, cron‑driven, idempotent deploy pipeline (instant orders, retryable steps, failure tickets).
- Server **capabilities** (Web / Mail / DNS) and **server groups** for load segmentation by server type.
- Role‑targeted, centrally‑managed `hestia.conf` and rebrandable standard files per group.
- Active‑active **DNS cluster** with HestiaCP **and** PowerDNS backends, mixable in one cluster.

**Deployment modes**
- **Split** — a separate Hestia user per role.
- **Unified** — web + mail under one user.
- **Vanity** — sell `name.<your-domain>` sites + `name@<your-domain>` mailboxes on a domain you own, with a standalone shop‑widget generator. The shared parent domain, mail user and DNS zone are never touched per order.

**Client area**
- Self‑service Web settings, FTP, Databases, DNS, Mailboxes, SSL, Backups, Cron and Logs — each gated by per‑product client permissions.

**Admin**
- Addon dashboard, infrastructure & server actions, group editor, DNS zones/templates, settings, task queue & operation log, statistics.
- Embedded per‑service admin panel: overview, every resource tab, reveal credentials, edit‑DB‑row, deploy timeline, verify & repair, factory reset.

**Automation**
- Let's Encrypt auto‑SSL with adaptive cadence and rate‑limit guards; custom‑certificate upload.
- Per‑server batch usage sync feeding WHMCS metric billing.
- Suspend / unsuspend / terminate following the same async, idempotent model.
