# Ploos Hosting — master roadmap

**Status:** strategic roadmap; phases indicate dependencies, not promised release dates. Product independence and security are release criteria throughout.

## Phase 0 — Existing foundation and inventory
- [x] Establish separate web-hosting and app-hosting infrastructure.
- [x] Start Ploos Deploy and Ploos Domains as separate repositories.
- [ ] Inventory current production services, owners, backups, credentials, DNS and support obligations.
- [ ] Define service ownership, product boundaries and readiness criteria.

## Phase 1 — Domains + deployment foundation (current priority)
- [ ] Finish Ploos Domains API security and operational readiness; review its product-specific roadmap.
- [ ] Integrate Ploos Domains with Ploos Deploy and publish a reproducible deployment.
- [ ] Set up verified `domains.ploos.no` routing, TLS, monitoring, secrets and rollback.
- [ ] Validate external DNS-provider integration using explicit approval and dry-run flows.

## Phase 2 — Shared customer platform
- [ ] Choose and deploy production-capable customer authentication/SSO.
- [ ] Design customer/organization mapping and per-product entitlements.
- [ ] Build minimal customer portal and provisioning workflows.
- [ ] Define independent subscription, invoicing, tax and cancellation semantics.
- [ ] Set policies for support, backups, incident response and data exports.

## Phase 3 — Ploos Mail + transactional SMTP
- [ ] Evaluate Stalwart vs mailcow, licensing and automation APIs.
- [ ] Build dedicated mailbox hosting with IMAP/SMTP, webmail, spam controls, aliases and domain validation.
- [ ] Separately design transactional outbound email and IP/reputation controls.
- [ ] Prove email delivery, migration, restore and tenant isolation before paid launch.

## Phase 4 — Ploos Storage
- [ ] Validate Nextcloud-based storage/sync/share service and capacity economics.
- [ ] Implement independent Storage entitlements, quotas, backups and data exports.
- [ ] Pilot file sharing and tested restore with isolated tenants.

## Phase 5 — Ploos Workspace
- [ ] Add calendar, contacts and online document collaboration to Storage foundation.
- [ ] Verify Workspace can be sold without Ploos Mail and can use third-party email.
- [ ] Test optional upgrades/downgrades without destroying Storage content.

## Phase 6 — Bundles, self-service and external integrations
- [ ] Offer Web + Mail, Mail + Workspace and Business Complete as composed subscriptions.
- [ ] Implement independent cancellation, proration, provisioning and billing.
- [ ] Integrate selected Forenio organization onboarding and other Ploos services.
- [ ] Add operational reporting, support tooling, and controlled expansion.

## Cross-cutting release gates
- [ ] Independent lifecycle tests: activating/cancelling one product must not disrupt another.
- [ ] Tenant-isolation and privilege tests across all products.
- [ ] Verified encrypted backups and restore drills.
- [ ] Monitoring, SLAs/terms, GDPR/DPA and data portability.
- [ ] DNS/email safety and explicit customer approval for externally visible changes.

## Related roadmaps

- [Ploos Domains](https://github.com/Ploos-AS/Ploos-Domains/blob/main/docs/ROADMAP.md)
- [Ploos Deploy](https://github.com/Ploos-AS/Ploos-Deploy)

These phases describe **intent**, not a statement that products are generally available.
