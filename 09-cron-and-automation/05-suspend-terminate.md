# Suspend, Unsuspend & Terminate

### PUQ Web Hosting module **[WHMCS](https://puqcloud.com/)**
#####  [Order now](https://puqcloud.com/) | [Download](https://download.puqcloud.com/WHMCS/servers/PUQ_WHMCS-WEB-Hosting/) | [FAQ](https://faq.puqcloud.com/)

The WHMCS lifecycle commands map onto the same async, idempotent task model as provisioning.

## Suspend / Unsuspend

* **Suspend** — disables the service's users across its servers (web/mail/dns) so sites and mail stop serving, without deleting anything. While suspended, client‑area write actions are blocked.
* **Unsuspend** — re‑enables them. Because the data was never removed, the service comes straight back.

These follow WHMCS automation (overdue suspend, etc.) or can be triggered manually from the service's Module Commands.

## Terminate

**Terminate** removes the service's resources from every server it touches and cleans up the local rows in a transaction. A pending‑terminate state is finalised by cron, and a **force‑terminate** path exists for cases where a node is unreachable at termination time so the service can still be closed out cleanly.

## The Vanity invariant

On a **Vanity** service these operations are deliberately scoped: they only ever touch that service's **own** subdomain, its **single** mailbox and its **single** DNS record. The shared provider domain, its mail user and its DNS zone are never modified — that invariant holds through suspend, unsuspend, terminate, redeploy and factory reset alike. See **Vanity Mode → What it is & why**.

> Lifecycle commands always report `success` to WHMCS immediately and do the real work via the queue, mirroring the provisioning model — so a slow or temporarily unreachable node never blocks the WHMCS workflow.
