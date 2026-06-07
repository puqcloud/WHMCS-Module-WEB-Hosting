# Service Management

### PUQ Web Hosting module **[WHMCS](https://puqcloud.com/link.php?id=77)**
#####  [Order now](https://puqcloud.com/whmcs-module-web-hosting.php) | [Download](https://download.puqcloud.com/WHMCS/servers/PUQ_WHMCS-WEB-Hosting/) | [Community](https://community.puqcloud.com/)

Every hosting service is managed from inside its WHMCS service page. At the top you get the standard WHMCS editor with the Configurable‑Option dropdowns and the **Module Commands** (Create / Suspend / Unsuspend / Terminate / Change Package):

![WHMCS service — module commands](../img/whmcs-admin-service-products-services.png)

Below that, the module embeds a full **admin service panel** — your staff's day‑to‑day console for the service.

## Overview

The Overview shows two role cards. **Web & DNS** lists the web Hestia user, the DNS user and zones (with deploy badges) and the website usage gauges; **Mail** lists the mail user, mail/webmail links and the mailbox gauges. Both show the SSL state. Top buttons: **Edit DB row · Reveal credentials · Redeploy service · Factory reset · Change domain**.

![Admin service panel — overview](../img/admin-service-panel-overview-full.png)

## Per‑resource tabs

The tab bar mirrors the client area but read/write for staff:

| Tab | What you do |
|-----|-------------|
| **Web settings** | PHP version, HTTPS redirect, proxy extensions. ![Web settings](../img/admin-service-panel-web-settings.png) |
| **SSL** | Auto‑SSL state per role + custom‑cert upload; Issue/Renew now. ![SSL](../img/admin-service-panel-ssl.png) |
| **FTP** | FTP accounts (full prefixed username). ![FTP](../img/admin-service-panel-ftp.png) |
| **Databases** | Databases (name/user, engine, charset, size). ![Databases](../img/admin-service-panel-databases.png) |
| **DNS** | The service's zone records (type/name/value/pri/TTL) with per‑server deploy state. ![DNS](../img/admin-service-panel-dns.png) |
| **Mailboxes** | The service's mailboxes (email, quota, status). ![Mailboxes](../img/admin-service-panel-mailboxes.png) |
| **Cron** | Cron jobs (schedule, command, status). ![Cron](../img/admin-service-panel-cron.png) |
| **Backups** | Web + Mail backup lists with Backup now / Sync from server / Restore / Delete / Check restore. ![Backups](../img/admin-service-panel-backups.png) |
| **Logs** | Real Hestia log tail (Apache/Exim/Dovecot), grep‑filtered to the domain. ![Logs](../img/admin-service-panel-logs.png) |

## Deploy & Tasks

The **Deploy** tab shows live deploy status, a full event timeline and **Redeploy (hard reset)**. The **Tasks** tab lists this service's tasks (action, target, server, status, attempts, timestamps); each opens a detail modal with the streamed SSH log.

![Deploy timeline](../img/admin-service-panel-deploy-timeline.png)
![Tasks tab](../img/admin-service-panel-tasks.png)
![Task detail](../img/admin-service-panel-task-detail.png)

## Limits, usage & power tools

The Overview tab also carries the **Resolved limits** and live **Usage** tables, with **Force usage sync** and a **Verify & Repair** panel:

![Resolved limits + usage](../img/admin-service-panel-resolved-limits-usage.png)

* **Reveal credentials** — decrypted logins/passwords for the web (FTP/panel/unix), mail and DNS Hestia users.

  ![Reveal credentials](../img/admin-service-panel-reveal-credentials.png)
* **Edit DB row** — a raw editor of the service record for fixing rows that got into a bad state (bypasses provisioner validation — power users only).

  ![Edit DB row](../img/admin-service-panel-edit-db-row.png)
* **Factory reset** — wipes the Hestia users + local child rows and re‑runs the full deploy chain (two‑step confirm).

## Cross‑service list

The addon **Services** page is the fleet‑wide view — search/filter by deploy or DNS state, see each service's **Mode** (Split/Vanity) and DNS ownership, open the admin panel, redeploy, unlock or force‑delete, and run **Verify** (probe panels + DNS and repair).

![Services list](../img/addon-services-list.png)
