# Frequently Asked Questions

### PUQ Web Hosting module **[WHMCS](https://puqcloud.com/link.php?id=77)**
#####  [Order now](https://puqcloud.com/whmcs-module-web-hosting.php) | [Download](https://download.puqcloud.com/WHMCS/servers/PUQ_WHMCS-WEB-Hosting/) | [FAQ](https://faq.puqcloud.com/)

**Do I need separate servers for web, mail and DNS?**
No. One server can do all three. But you *can* split them by capability and balance load by server type — heavy PHP sites on web nodes, mail on mail nodes, an active‑active DNS pool — without changing products. See **Deployment & Segmentation**.

**What's the difference between Split, Unified and Vanity?**
*Split* gives each role its own Hestia user; *Unified* puts web+mail under one user; *Vanity* sells `name.<your-domain>` + `name@<your-domain>` slots on a domain you own. See **Deployment Models**.

**What is Vanity mode for?**
To monetise a domain you own by selling personal sub‑sites and mailboxes on it (e.g. `john.yourbrand.com` + `john@yourbrand.com`). It's a distinct product type with a simplified client area and an optional standalone shop widget. See **Vanity Mode**.

**Why does provisioning happen "in the background"?**
Orders are instant and every step is retryable. `_CreateAccount` enqueues work; the cron task runner builds the service idempotently. See **Cron & Automation → The deploy process**.

**Nothing is provisioning — what's wrong?**
Almost always cron isn't running. Confirm the crontab line from **Settings → Cron** is installed, then watch **Logs → Task Queue**.

**How does SSL work?**
Let's Encrypt is issued and renewed automatically once DNS points at the server; customers can also upload a custom certificate. See **Cron & Automation → SSL automation**.

**Can customers manage their own FTP, databases, DNS, mail, backups and cron?**
Yes — each is a client‑area page, and each is gated by the product's **Client permissions** so you decide what every plan exposes. See **Client Area**.

**How is usage billed?**
Live usage is synced per‑server and exposed to WHMCS metric billing, on top of flat plan pricing. See **Usage Sync & Metric Billing**.

**Which DNS backends are supported?**
HestiaCP and PowerDNS, mixable in one cluster. DNS is active‑active: every record is replicated to all attached DNS servers.

**Does terminating a Vanity service hurt the shared domain?**
No. Vanity operations only ever touch that service's own subdomain, single mailbox and single DNS record — never the shared provider domain, mail user or zone.

**A node went down mid‑deploy — did I lose the service?**
No. Its tasks retry when it's back; if a task is permanently stuck, **Force‑fail stuck** then **Verify & Repair** rebuilds what's missing. See **Troubleshooting**.

**How do I move a product to a new deployment mode or add a role?**
Change it on the product's **General** tab, re‑run **Config options → Create / sync missing** (safe, additive), and redeploy affected services.

**Which PHP version / module build do I need?**
Install the build that matches the PHP version your **WHMCS host** runs on. The module ships builds for PHP **7.4, 8.1 and 8.2**. **WHMCS 8** runs on PHP 7.4, 8.1 or 8.2 → use the matching build; **WHMCS 9** runs on PHP 8.2 → use the 8.2 build; on any host with **PHP 8.3 / 8.4 or newer**, use the **8.2 build**. This is the WHMCS host's PHP — separate from the PHP versions you offer to hosting customers on each Hestia web server. Full table in **Installation & Configuration → Requirements & Installation**.

**Where do I get help or ask questions?**
Join the PUQ community at [community.puqcloud.com](https://community.puqcloud.com/).
