# Changelog

All notable changes to this project will be documented in this file.

The format is based on [Keep a Changelog](https://keepachangelog.com/en/1.0.0/),
and this project adheres to [Semantic Versioning](https://semver.org/spec/v2.0.0.html).

## [2.0.0] - 2026-08-10

### Added
- Granular control over contract types through new configuration options:
  - `IncludePlacements`: Include placements (plaatsingen) as contracts (default: `true`)
  - `IncludeClassGroups`: Include class groups (lesgroepen) as contracts (default: `true`)
  - `IncludeSubjectChoices`: Include subject choices (vakkeuzes) as contracts (default: `true`)
- Contract ExternalId now includes UUID and validity period in format: `uuid_startdatum_einddatum`
- Automatic contract deduplication based on ExternalId
- Migration guide section with configuration and data structure changes
- Comprehensive field mapping examples in README for person and contract mappings
- Dynamic StartDate mapping based on contract type
- Department mapping based on contract type

### Changed
- **BREAKING:** Renamed connection setting `Instelling` to `Institution`
- **BREAKING:** Person DisplayName now includes student number in format: `"Roepnaam Achternaam (12345)"`
  - This may affect HelloID correlation when upgrading from v1.0.0
- Connection settings table now includes version information and notes for each setting

### Removed
- **BREAKING:** Connection setting `Instelling` (replaced by `Institution`)

## [1.0.0]

### Added
- Initial release
- Student data synchronization from Topicus SOMToday Connect API
- Support for three contract types: placements (plaatsingen), class groups (lesgroepen), and subject choices (vakkeuzes)
- OAuth authentication via proxy token URL
- Optional access card information collection (`CollectCardInfo`)
- Optional safe information collection (`CollectSafeInfo`)
- Debug logging option (`IsDebug`)
