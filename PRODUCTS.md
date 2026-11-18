# Product catalog and packaging

## Separately purchasable products

| Product | Scope | Proposed entry point | Delivery status |
| --- | --- | --- | --- |
| Ploos Web | Website hosting, domains as aliases, site lifecycle and backups | `web.ploos.no` | Existing hosting infrastructure; standardized self-service pending |
| Ploos Apps | Hosting of Ploos SaaS and potentially customer apps | `apps.ploos.no` | Existing infrastructure and Ploos Deploy development |
| Ploos Domains | Domain inventory, control verification, DNS and delegated subdomains | `domains.ploos.no` | Under active development; not production-ready |
| Ploos Mail | Mailboxes, IMAP/SMTP, webmail, aliases, anti-spam and domain mail | `mail.ploos.no` | Planned |
| Ploos SMTP | Transactional outbound email for apps and notifications | `smtp.ploos.no` (provisional) | Planned |
| Ploos Storage | File synchronization, storage and sharing without full collaboration suite | `cloud.ploos.no` (provisional) | Planned |
| Ploos Workspace | Storage plus calendar, contacts, collaborative editing and related tools | `cloud.ploos.no` (provisional) | Planned |

Subdomains are **proposals**, not proof of active services or DNS records. A later customer portal may be offered at `portal.ploos.no`.

## Commercial principles

1. **Independent subscriptions.** Each service can be bought and billed on its own. Customers can use external domains, DNS, web hosting or email providers.
2. **Bundles are compositions, not separate technical silos.** Potential bundles include Web + Mail, Mail + Workspace, and Business Complete (Web + Mail + Workspace + Domains).
3. **Portable data and clean termination.** Plan exports for websites, mailboxes and files. Cancelling Web cannot erase Mail or Workspace data.
4. **No forced DNS migration.** Domain registration, DNS hosting and product activation are separate customer choices. MX records must not change when only Web is ordered.
5. **Tenant separation.** Organizations, users, permissions, quotas and billing are scoped per tenant and product.

## Proposed product tiers — not pricing decisions

- Web Start / Web Plus: site counts, capacity, backup/restore options.
- Mail Start / Mail Plus: mailbox count, aliases and mailbox quotas.
- Storage: storage capacity and sharing/sync functionality.
- Workspace: storage plus collaboration functions, priced and provisioned separately.
- Mail + Workspace and Business Complete: discounts or consolidated billing while preserving lifecycle independence.

**Open decisions:** resource quotas, exact features, consumer vs business focus, tax/invoicing, terms/SLA, backups and retention, and whether Storage and Workspace share one Nextcloud deployment with separate entitlements. Do not advertise products as live until operational acceptance is complete.
