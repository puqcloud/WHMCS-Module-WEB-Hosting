# Requirements & Installation

### PUQ Web Hosting module **[WHMCS](https://puqcloud.com/)**
#####  [Order now](https://puqcloud.com/) | [Download](https://download.puqcloud.com/WHMCS/servers/PUQ_WHMCS-WEB-Hosting/) | [FAQ](https://faq.puqcloud.com/)

## Requirements

* A working **WHMCS** installation.
* One or more **HestiaCP** servers reachable over **SSH** from the WHMCS host. The module drives Hestia entirely over SSH (the panel HTTP API is not required); set up `sudo` NOPASSWD for the management user, or use the Hestia `admin` user with key/password auth.
* (Optional) **PowerDNS** servers if you want PowerDNS as a DNS backend alongside HestiaCP.
* Outbound HTTPS from the Hestia nodes for Let's Encrypt and for the optional file‑manager / PHP installers.

## Install both modules

The product is **two** WHMCS modules — install both:

| Upload to | Module |
|-----------|--------|
| `modules/servers/puqWebHosting/` | the **server module** |
| `modules/addons/puq_web_hosting/` | the **addon module** |

Then in WHMCS go to **Setup → Addon Modules**, find **PUQ Web Hosting**, and **Activate** it (grant access to the admin roles that should manage hosting). Activating the addon creates the database tables the server module needs.

## First run: check the schema & find the panels

After activation you have a new **PUQ Web Hosting** admin page (via *Addons*). Its top navigation gives you everything: **Home, Services, Statistics, Infrastructure, Logs, Settings, Help**.

![Addon nav + Settings menu](../img/addon-settings-general-nav.png)

Open **Settings → Maintenance** and click **Run schema check** once. It scans every module table and brings it in sync with the current code — creating missing tables, adding missing columns and dropping columns that no longer exist. You should run this after every module update.

![Maintenance — schema check](../img/addon-settings-maintenance.png)

> The same tab has a *“delete all tables on deactivate”* toggle — leave it **off** unless you are fully uninstalling, so your data survives an accidental deactivation.

## What's next

With both modules installed you build your service from the bottom up:

1. **Add your servers** and tag their capabilities — see *Add web / mail / DNS servers*.
2. **Group them** and apply role‑targeted configuration — see *Server groups*.
3. **Create a product** pointed at a group — see *Create a product*.

The module **Settings** (timeouts, retry policy, SSL cadence, DNS/SOA defaults, integrations, notifications) are covered in *Addon Module → Settings*; the defaults are sensible, so you can come back to them later.
