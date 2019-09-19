## [1.2.1-beta](https://github.com/ZencashOfficial/Sphere_by_Horizen/releases/tag/desktop-v1.2.1-beta)
### Changed
- Upgraded project dependencies

## [1.2.0-beta](https://github.com/ZencashOfficial/Sphere_by_Horizen/releases/tag/desktop-v1.2.0-beta)
### Added
- Batch withdraw, used to withdraw funds from multiple addresses in a single transaction
- Batch split, used to deposit funds to multiple addresses in a single transaction
- Private Key Balance Sweep entry in the application Tools menu, enabling the ability to sweep all funds from private keys / WIFs
- View a wallet's backup phrase in its settings window

## [1.1.2-beta](https://github.com/ZencashOfficial/Sphere_by_Horizen/releases/tag/desktop-v1.1.2-beta)
### Bugfix
- Fixed an issue with handling null data (OP_RETURN) transactions
- Fixed full mode seed restores taking an unusual length of time to complete
- Fixed an issue where some addresses would not be restored
### Changed
- Restoring a seed will now search every layer of the BIP39/44 derivation path, providing support for external HD wallets
- Upgraded the bundled Zend to 2.0.18
### Added
- User can now specify how many shielded addresses to restore, up to a hard limit of 20
- User can now specify how many transparent addresses to restore, up to a hard limit of 500 per active account & chain on the BIP39/44 derivation path (https://github.com/bitcoin/bips/blob/master/bip-0039.mediawiki)

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
