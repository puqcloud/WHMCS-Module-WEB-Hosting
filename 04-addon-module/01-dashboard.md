# Dashboard

### PUQ Web Hosting module **[WHMCS](https://puqcloud.com/link.php?id=77)**
#####  [Order now](https://puqcloud.com/whmcs-module-web-hosting.php) | [Download](https://download.puqcloud.com/WHMCS/servers/PUQ_WHMCS-WEB-Hosting/) | [Community](https://community.puqcloud.com/)

The addon **Home** page is a one‑glance view of your whole hosting operation.

![Addon dashboard](../img/addon-home-dashboard.png)

## Cards

| Card | Shows |
|------|-------|
| **Services** | Total provisioned services (View → the Services list). |
| **Servers** | Total servers (Manage → Infrastructure). |
| **Task Queue** | Tasks currently in the queue (View → Logs → Task Queue). |
| **DNS Zones** | Total logical DNS zones (Manage). |
| **Server Groups** | Shortcut to group management. |
| **Settings** | Shortcut to cron / retry policy / tables. |

## Panels

* **Server capacity** — every node by **type** (web/mail/dns), its capacity used/max and its **last sync** time. A quick health view of each tier.
* **Recent terminal errors** — services whose deploy terminally failed (so you can act fast). Empty is good.
* **Recent services** — the latest provisioned services with their WHMCS and deploy status.

## Navigation

The top bar is the same everywhere:

* **Home** — this dashboard.
* **Services** — the cross‑service admin list (search/filter, open the admin panel, redeploy/verify).
* **Statistics** — per‑domain usage (web/mail split).
* **Infrastructure** — Web / Mail / DNS Servers, Server Groups, DNS Zones, DNS Zone Templates.
* **Logs** — Task Queue, Operation Log.
* **Settings** — General, Cron, Vanity widget.
* **Help** — documentation & support links.
