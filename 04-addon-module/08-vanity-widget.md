# Vanity Widget

### PUQ Web Hosting module **[WHMCS](https://puqcloud.com/link.php?id=77)**
#####  [Order now](https://puqcloud.com/whmcs-module-web-hosting.php) | [Download](https://download.puqcloud.com/WHMCS/servers/PUQ_WHMCS-WEB-Hosting/) | [Community](https://community.puqcloud.com/)

**Settings → Vanity widget** generates a standalone "claim your name" landing page (two files) that you can drop on any marketing domain to sell vanity slots outside the WHMCS portal.

![Vanity widget config](../img/addon-vanity-widget-config.png)

In short, you: (1) get/regenerate a **shared API key**, (2) pick the **vanity product**, (3) copy the config block into `proxy.php`, (4) choose the **cart behaviour**, then **download** `proxy.php` + `index.html` and upload both to each marketing domain's web root.

![Vanity widget download](../img/addon-vanity-widget-download.png)

The browser only ever talks to the widget's own `proxy.php` (which holds the key and caches answers) — the key never reaches the visitor.

> The full setup, the buyer's flow and the security model are documented in the dedicated **Vanity Mode → The vanity shop widget** page.
