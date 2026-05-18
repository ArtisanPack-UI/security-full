# ArtisanPack UI Security Full Changelog

All notable changes to this project will be documented in this file.

The format is based on [Keep a Changelog](https://keepachangelog.com/en/1.0.0/),
and this project adheres to [Semantic Versioning](https://semver.org/spec/v2.0.0.html).

## [Unreleased]

## [1.0.0] - 2026-05-18

### Added

- Initial release of the `artisanpack-ui/security-full` meta-package. Installing it pulls in the full ArtisanPack UI security suite:
  - `artisanpack-ui/security` `^2.0` — core sanitization, output escaping, KSES, CSP, security headers, rate limiting
  - `artisanpack-ui/rbac` `^1.0` — roles, permissions, role hierarchy, Blade directives, Gate integration
  - `artisanpack-ui/security-auth` `^1.0` — 2FA, password complexity, account lockout, session management, step-up auth
  - `artisanpack-ui/security-advanced-auth` `^1.0` — WebAuthn / passkeys, SSO, social login, biometric, device fingerprinting
  - `artisanpack-ui/secure-uploads` `^1.0` — file validation, malware scanning, signed-URL serving, quarantine
  - `artisanpack-ui/security-analytics` `^1.0` — security event logging, anomaly detection, SIEM, dashboards
  - `artisanpack-ui/compliance` `^1.0` — GDPR / CCPA / LGPD consent management, data subject rights (erasure + portability), DPIA, retention, compliance monitoring + reporting
- Composer `type: metapackage` — no source files, no autoload, no tests; the meta-package is purely a dependency aggregator.
