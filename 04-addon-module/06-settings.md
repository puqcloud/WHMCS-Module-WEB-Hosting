# Settings

### PUQ Web Hosting module **[WHMCS](https://puqcloud.com/link.php?id=77)**
#####  [Order now](https://puqcloud.com/whmcs-module-web-hosting.php) | [Download](https://download.puqcloud.com/WHMCS/servers/PUQ_WHMCS-WEB-Hosting/) | [Community](https://community.puqcloud.com/)

**Settings** has three pages — **General**, **Cron** and **Vanity widget**. The General page is organised into tabs. The defaults are sensible; tune them as you scale.

## General

The **General** tab itself holds API timeouts and the **task retry policy** (max attempts, back‑off minutes, batch size per cron run, finished‑task retention):

![Settings — General content](../img/addon-settings-general-content.png)

The remaining tabs:

| Tab | Controls |
|-----|----------|
| **Provisioning** | Defaults for new users — FTP root path, login shell (`nologin` for managed hosting), Hestia admin/SSH usernames. ![Provisioning](../img/addon-settings-provisioning.png) |
| **DNS** | Record TTL (default/min/max, max value length) and module‑wide **SOA defaults**. ![DNS](../img/addon-settings-dns.png) |
| **SSL** | Auto‑SSL cadence (fast‑mode count/interval, normal interval, active‑cert interval) and the Let's Encrypt **rate‑limit guard**. ![SSL](../img/addon-settings-ssl.png) |
| **Mail & Security** | Webmail / phpMyAdmin URL patterns, DKIM key size, max auto‑reply length, minimum password length. ![Mail & Security](../img/addon-settings-mail-security.png) |
| **Logging & Performance** | Log download size cap, tail line limits, mail‑log filter window, SSH heavy‑bash & apt‑lock timeouts. ![Logging](../img/addon-settings-logging-performance.png) |
| **Integrations** | Overridable upstream URLs — FileGator/net2ftp zips, FTP host fallback, PHP repos (Ondrej PPA, Sury), GPG keyserver, IonCube installer. ![Integrations](../img/addon-settings-integrations.png) |
| **Notifications** | Failure‑ticket toggle (department + priority), client‑area toast/poll durations, analytics lookback windows. ![Notifications](../img/addon-settings-notifications.png) |
| **Maintenance** | The schema **Check & repair** tool + the deactivation data‑retention toggle. ![Maintenance](../img/addon-settings-maintenance.png) |

## Cron

The **Cron** page picks the cron mode (WHMCS vs Standalone), shows the crontab line to install, and lists every scheduled task with its enable/interval/last‑run/status, plus concurrency limits.

![Settings — Cron](../img/addon-settings-cron.png)

## Vanity widget

Generates the standalone "claim your name" shop widget — see **Vanity Mode → The vanity shop widget**.
