# Ploos Hosting

**Modular hosting services from Ploos AS.** This repository documents the product portfolio, shared architecture and delivery roadmap. It is a planning and coordination repository, not a running hosting control plane.

## Products

- **Ploos Web** — website and web application hosting.
- **Ploos Mail** — hosted mailboxes, IMAP/SMTP, webmail and domain email.
- **Ploos Storage** — file storage, sync and sharing.
- **Ploos Workspace** — collaboration, calendars, contacts and document editing.
- **Ploos Domains** — domain inventory, verification, DNS management and subdomain delegation.
- **Ploos Apps** — hosted applications and SaaS workloads.
- **Ploos SMTP** — transactional outbound email for applications, distinct from mailboxes.
- **Ploos Hosting bundles** — optional combinations of independent products.

**Product independence is a requirement:** customers can buy, add, upgrade or cancel one product without automatically losing other products. A domain may remain registered and DNS-hosted elsewhere. Web hosting must not require Ploos Mail; Workspace must not require Ploos Mail.

## Documents

- [Product catalog and packaging](PRODUCTS.md)
- [Platform architecture and boundaries](ARCHITECTURE.md)
- [Delivery roadmap](ROADMAP.md)

Existing and related projects: [Ploos Domains](https://github.com/Ploos-AS/Ploos-Domains), [Ploos Deploy](https://github.com/Ploos-AS/Ploos-Deploy), [Forenio](https://github.com/Ploos-AS/Forenio). The repository does not claim that proposed products are launched.

## Status

**Planning stage.** Existing web hosting and app infrastructure are separate from planned customer-facing Mail, Storage and Workspace products. Pricing, service levels, providers, licensing choices and production readiness are not yet approved.
