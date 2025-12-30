# Changelog

All notable changes to this Frappe fork will be documented in this file.

The format is based on [Keep a Changelog](https://keepachangelog.com/en/1.0.0/),
and this project adheres to [Semantic Versioning](https://semver.org/spec/v2.0.0.html).

## [v15.78.1+medis1] - 2025-12-30

### Added

- **[Monitoring]** Added LoggingIntegration to Sentry SDK for enhanced error tracking
  - Captures Python logging events and sends them to Sentry
  - Enables better correlation between logs and exceptions in Sentry

## [medis-v15.78.3] - 2025-11-17

### Changed

- **[Database]** Increased decimal precision for Float field type in MariaDB from `decimal(21,9)` to `decimal(23,9)`
  - Aligns Float precision with Currency field precision

## [medis-v15.78.2] - 2025-11-15

### Changed

- **[Database]** Adjusted Currency field decimal precision to prevent overflow issues
  - Reduced precision from `decimal(25,9)` to `decimal(23,9)` in both MariaDB and PostgreSQL
  - Maintains 9 decimal places while preventing database overflow errors
  - Ensures consistency across both supported database engines

## [v15.78.1-currency-size] - 2025-11-15

### Changed

- **[Database]** Initial increase of Currency field decimal precision from `decimal(21,9)` to `decimal(25,9)`
  - Applied to both MariaDB and PostgreSQL databases
  - Note: This change was later refined in v15.78.2 to address overflow concerns

---

## Summary of Custom Changes

This fork contains the following key modifications from upstream Frappe:

### Database Precision Improvements

- **Currency Fields**: Optimized to `decimal(23,9)` precision (23 total digits, 9 decimal places)
- **Float Fields**: Increased to `decimal(23,9)` precision for consistency and accuracy
- **Impact**: Better handling of large currency values and precise float calculations
- **Databases Affected**: MariaDB and PostgreSQL

### Developer Experience Enhancements

- **Request Tracing**: Added unique request ID tracking via HTTP headers
- **Debugging**: Improved ability to correlate client requests with server logs
- **Monitoring**: Better support for distributed tracing and request flow analysis

### Observability & Monitoring

- **Sentry Integration**: Enhanced Sentry SDK with LoggingIntegration
- **Error Tracking**: Improved error context and log correlation in Sentry
- **Log Visibility**: Python logging events automatically captured and sent to Sentry for better diagnostics

---

## Versioning Scheme

This fork uses the following version naming scheme:

- `{UPSTREAM_VERSION}+medis.{N}` - Patches on stable upstream releases
- `medis-vX.Y.Z` (deprecated) - Previous stable release patches

## Contributing

When making changes to this fork:

1. Create a feature branch from `main`
2. Make your changes with clear, descriptive commit messages
3. Update this CHANGELOG.md under the `[Unreleased]` section
4. Submit a pull request with a clear description of the changes

## Links

- [Keep a Changelog](https://keepachangelog.com/en/1.0.0/)
- [Semantic Versioning](https://semver.org/spec/v2.0.0.html)
- [Upstream Frappe Repository](https://github.com/frappe/frappe)
