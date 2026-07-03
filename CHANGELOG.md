## V1.0.0 - 30 June 2026

- Initial release.

## V1.0.1 - 30 June 2026

- Fix bug with saving API Key on fresh install.
- Fix bug with SAM query not working as intended.

## V1.0.2 - 30 June 2026

- Add tooltips to Results table on hover.

## V1.0.3 - 30 June 2026

- Add manual and automatic update checking.

## V1.1.0 - 3 July 2026

- Refactored export file/code format to only store necessary information, retains reverse compatibility for earlier import versions.
- Library names no longer need to be unique, distinctions are made by the user IDs and filters now instead of names.
- Importing files bases a default name on Steam display name and filters present now instead of what the library name was exported as.
- Import conflicts allow option to overwrite existing import.
- `.slc` files are now associated with the app and will launch the app to import when opened.
- Dragging `.slc` files into the app initiates import.
- Duplicate instances of the app should be disallowed.
- CSV import has been removed. CSV export still remains as an option.
- Added safeguards for Steam not running, no detected Steam account login, failures in scanning, detecting less games than a prior scan, etc.
- Failures to request metadata allow several additional retries before cancelling operation.
  - Partial failures retain information instead of discarding it due to the failure.
- Logic to handle delisted/unlisted Steam games.
- More control over how much metadata to download at once based on loaded libraries/filters.
- Fix error with sorting by size/price metadata not ordering properly.
  - Unknown data is always sorted to the bottom of the list in either direction when sorting by size/price.
- Option to save as file or save as new library.
- Update to language localization with approximately double the amount of strings translated between languages.
- Updated README