# The Deploy Process

### PUQ Web Hosting module **[WHMCS](https://puqcloud.com/link.php?id=77)**
#####  [Order now](https://puqcloud.com/whmcs-module-web-hosting.php) | [Download](https://download.puqcloud.com/WHMCS/servers/PUQ_WHMCS-WEB-Hosting/) | [Community](https://community.puqcloud.com/)

Provisioning is **not** done synchronously inside the WHMCS order. `_CreateAccount` simply records the desired service and enqueues the work; the cron‑driven task runner then builds the service step by step. This is what keeps orders instant and makes every step retryable.

## The chain

A new order fans out into a chain of idempotent tasks, roughly:

```
create package  →  create web user   →  add web domain   →  (PHP/SSL/proxy)
                →  create mail user   →  add mail domain  →  DKIM/SPF/DMARC
                →  create dns user    →  add zone         →  add records (× every DNS server)
                →  mark service active
```

Each task does exactly one thing on one target, checks whether it's already done before acting, and reports back. Because every step is **idempotent**, re‑running the chain (a retry, a Redeploy, a Factory reset) converges on the same end state instead of duplicating resources.

## What the customer sees

While the chain runs, the customer sees a live progress splash with a timeline; on success they land on the dashboard, on failure an error screen with **Try again**. This is covered visually in **Deployment & Segmentation → How deployment works**.

## Why async

* **Instant orders** — checkout doesn't block on SSH to several servers.
* **Resilience** — a momentarily unreachable node just delays its tasks; the rest proceed and the failed ones retry.
* **Observability** — every step is a row you can watch, retry or inspect in the Task Queue and Operation Log.

> See the next page for the retry/back‑off policy and failure tickets.
