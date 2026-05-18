# ArtisanPack UI — Security Full

A Composer meta-package that pulls in the entire ArtisanPack UI security suite in one require. No source code lives here — installing `artisanpack-ui/security-full` is equivalent to requiring the seven sibling packages listed below at their `^1.0` / `^2.0` constraints.

Use this if you want every security capability the ecosystem ships. If you only need a subset (for example, just RBAC, or just secure uploads), require those packages individually instead.

## Installation

```bash
composer require artisanpack-ui/security-full
```

Then run the migrations published by the bundled packages:

```bash
php artisan migrate
```

Each sibling package publishes its own config + assets. See the individual package READMEs for per-package setup steps (service provider auto-discovery, optional config publish, optional Livewire view publish, etc.).

## What's bundled

| Package | Scope |
|---|---|
| [`artisanpack-ui/security`](https://github.com/ArtisanPack-UI/security) | Core: input sanitization, output escaping, KSES, CSP, security headers, rate limiting |
| [`artisanpack-ui/rbac`](https://github.com/ArtisanPack-UI/rbac) | Roles, permissions, role hierarchy, Blade directives, Gate integration |
| [`artisanpack-ui/security-auth`](https://github.com/ArtisanPack-UI/security-auth) | 2FA (email + TOTP), password complexity, account lockout, session management, step-up auth |
| [`artisanpack-ui/security-advanced-auth`](https://github.com/ArtisanPack-UI/security-advanced-auth) | WebAuthn / passkeys, SAML + OIDC SSO, social login, biometric, device fingerprinting |
| [`artisanpack-ui/secure-uploads`](https://github.com/ArtisanPack-UI/secure-uploads) | File validation, malware scanning (ClamAV / VirusTotal), signed-URL serving, quarantine workflow |
| [`artisanpack-ui/security-analytics`](https://github.com/ArtisanPack-UI/security-analytics) | Security event logging, anomaly detection, SIEM exporters, dashboards |
| [`artisanpack-ui/compliance`](https://github.com/ArtisanPack-UI/compliance) | GDPR / CCPA / LGPD consent management, data subject rights (erasure + portability), DPIA, retention, compliance monitoring + reporting |

## Version compatibility

| `security-full` | `security` | `rbac` / `security-auth` / `security-advanced-auth` / `secure-uploads` / `security-analytics` / `compliance` |
|---|---|---|
| `^1.0` | `^2.0` | `^1.0` |

`security-full` follows semantic versioning. A major bump indicates that one or more bundled packages have shipped a breaking-change major release.

## Why a meta-package?

The security suite was split out of the monolithic `artisanpack-ui/security` 1.x package as part of the 2.0 redesign so consumers could pull only what they need. A meta-package gives the inverse: a single require for projects that want the full set, plus a single dependency line that gets coordinated upgrades across all six packages.

## License

MIT — see [LICENSE](LICENSE).

## Contributing

This repository is a meta-package — it does not contain source code. Issues and pull requests should be filed against the individual sibling packages.

Please read the [contributing guidelines](CONTRIBUTING.md) for the general ecosystem contribution workflow.
