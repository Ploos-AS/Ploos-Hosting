# Ploos Hosting — reference architecture

## Control plane versus data plane

The shared **control plane** manages customer organizations, identity, product entitlements, orders, billing, provisioning requests, support and status. Each service retains its own **data plane**, credentials, storage, uptime and lifecycle.

```text
                 Customer portal (planned)
                 portal.ploos.no
                         |
             Identity + tenant management
                         |
             Entitlements / billing / jobs
                         |
         +---------------+---------------+
         |               |               |
      Ploos Web       Ploos Mail    Ploos Storage/Workspace
         |               |               |
      web.ploos.no    mail.ploos.no    cloud.ploos.no
         |
      Ploos Apps -------- Ploos Domains
      apps.ploos.no       domains.ploos.no
         |                      |
      Ploos Deploy        Provider DNS adapters
```

## Independence rules

- Ploos Mail and Ploos Web are different products and may run on different hosts.
- Ploos Workspace works with external mail services; an email client is not an email server.
- Storage is an independent product even if its technical foundation is shared with Workspace. Entitlement boundaries, quotas and cancellation semantics must be tested.
- Domain management coordinates *requested* DNS changes but never rewrites unrelated records. In particular, provisioning a website may not silently replace MX/SPF/DKIM/DMARC records.
- Products communicate through versioned APIs and event/job workflows rather than sharing mutable application databases.
- Shared SSO must consider availability, disaster recovery and break-glass admin access.

## Proposed technology candidates (not selections)

- **Ploos Mail:** evaluate Stalwart and mailcow; confirm current licensing, multi-tenancy, admin APIs, quotas, migration tools and operational resource costs.
- **Ploos Storage and Workspace:** evaluate Nextcloud, Collabora Online and optional Talk/CalDAV/CardDAV functions; confirm resource isolation, licensing, upgrades and storage economics.
- **Identity:** evaluate Authelia or an equivalent standards-based OIDC provider against customer-facing account management requirements.
- **Transactional email:** dedicated outbound relay/provider; avoid combining app-generated traffic with customer mailbox IP reputation.
- **Deployment:** Ploos Deploy, container images pinned by digest, rollout checks and rollback.
- **Monitoring:** existing Prometheus/Grafana stack on mimir; separate public status page.
- **Backups:** encrypted, off-site, scheduled backups with tested restores and tenant-specific recovery.

## Existing environment (subject to operational verification)

- `bragi`: existing customer web hosting.
- `forseti`: planned/active application deployment environment.
- `mimir`: central infrastructure monitoring.

Dedicated mail and collaboration infrastructure is **proposed**, not purchased or deployed by this document.

## Security and operational gates

Before onboarding paying customers: enforce tenant authorization, least-privilege production roles, TLS and encrypted transport, data residency and GDPR terms, incident response, anti-abuse controls, outbound email reputation management, abuse handling, recovery-point/recovery-time targets, verified restore tests, uptime monitoring, product lifecycle isolation and customer data export/deletion.

DNS and email-specific gates: control DNS delegation before writes, verify domain ownership, apply SPF/DKIM/DMARC correctly, configure PTR/rDNS for sending IPs and monitor delivery/reputation. Running independent authoritative DNS is optional, not an initial dependency.
