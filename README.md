# walt.id SCIM 2.0 library — design

Design for an open-source SCIM 2.0 library for walt.id (`waltid-libraries/protocols/waltid-scim` and `waltid-scim-server`). The library lets enterprise directories such as Microsoft Entra ID and Okta create, update, deactivate and delete accounts and groups in walt.id products.

**Current version: [Design v2.2](waltid-scim-design-v2.md)** (November 2026). Start with the executive summary at the top. It takes about two minutes to read.

## Versions

| Version | Date | What changed |
|---|---|---|
| [v2.2](waltid-scim-design-v2.md) | November 2026 | Second architecture review: three PATCH modes (lenient, RFC, interop profile), tenant-qualified provisioning scope, mandatory conditional writes, a trust boundary for unknown attributes, event ordering by revision, a durable revocation intent for deactivation, read limits for large groups, and an issuer-owned credential policy |
| v2.1 | November 2026 | First architecture review: authorization and isolation, identity correlation, group membership rules, capability-driven discovery, wire format, operational limits, and Phase 1 split into PRs |
| v2.0 | October 2026 | Revised after walt.id's review: library-applied PATCH and PUT, schema-described documents, request context, module split, vendor compatibility layer, lifecycle callback, x509-first credential binding |
| [v1](waltid-scim-use-cases-and-architecture.md) | August 2026 | Use cases and architecture sketch (superseded, kept for history) |

v2.0 and v2.1 are not kept as separate files. Each review is traced in §1 of the current document.

## Repository layout

```
waltid-scim-design-v2.md                 current design (v2.2)
waltid-scim-use-cases-and-architecture.md  v1, superseded
images/                                  rendered diagrams (fig01–fig17 for v2, fig1–fig5 for v1)
diagrams/                                Mermaid sources for the v2 diagrams, plus the shared theme (config.json)
```

To re-render a diagram after editing its source:

```
npx @mermaid-js/mermaid-cli -c diagrams/config.json -i diagrams/fig07-concurrency.mmd -o images/fig07-concurrency.png -s 2 -b white
```

## Author

Saurabh Kushwaha ([@saujam](https://github.com/saujam)). Written in a personal capacity as a contribution to the walt.id open-source project.
