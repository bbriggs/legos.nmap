# Change Log

All notable changes to this project will be documented in this file.
This project adheres to [Semantic Versioning](http://semver.org/).

## [0.1.2] 2017-02-20
### Fixed

- Lego was checking for wrong message field and crashing on every request. No longer!
- Lego was bad about only returning the results of simple rolls, not sums. Fixed that too.
- Calling Lego without arguments no longer fails silently

### Added

- Improved the help messaging. Now points to upstream docs for the `dice` library.

## [0.1.1] 2017-02-15
### Fixed

- No longer crashes when receiving `None` as content of message

## [0.1.0] 2017-01-03
### Added

- Initial release
