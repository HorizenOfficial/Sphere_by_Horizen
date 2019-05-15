## [1.1.1-beta](https://github.com/ZencashOfficial/Sphere_by_Horizen/releases/tag/desktop-v1.1.1-beta) - 2019-05-15
### Changed
- Fix an issue where some ledger seeds would not fully restore
- Fix an issue handling spaces in Windows account usernames

## [1.1.0-beta](https://github.com/ZencashOfficial/Sphere_by_Horizen/releases/tag/desktop-v1.1.0-beta) - 2019-04-19
### Added
- Support restoring mnemonic seeds with multiple accounts (e.g. Ledger wallet seeds)
- Terminal restricted to `zen-cli` commands to enable advanced wallet usage
- Ability to reindex & reindex-chainstate the local node

### Changed
- Upgraded the bundled zend to 2.0.17
- Fix an issue where the application would crash when dealing with large transaction data sets
- Rework data refresh logic to reduce resource consumption and reliance on explorer API calls
- General performance improvements
- Fix an issue connecting to the local node
- RPC credentials are now randomised each time the application starts
- Fix issues with transaction history not displaying as intended
- Fix an issue where some accounts would become corrupted during encryption

## [1.0.1-beta](https://github.com/ZencashOfficial/Sphere_by_Horizen/releases/tag/desktop-v1.0.1-beta) - 2019-01-17
### Added
- Progress indicator for downloading the proving keys

### Changed
- Upgraded the bundled zend to 2.0.16
- Fixed installation issues on Windows systems
- Improved support for Windows 8 systems
- General improvements and bug fixes to the zend installer
