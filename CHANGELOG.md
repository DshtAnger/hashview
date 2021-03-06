# Change Log
Notable changes will be documented here

## Current Release

## [v0.7.0-beta] - 2017-07-22
### Added
 - Support for distributed cracking through hashview-agents
 - New type of wordlist 'Smart Wordlist'
 - Beta Hashview Hub (tm) integration
 - New management console for agents and Rules (you can now edit your rules within the app)
 - 3 new analytic portlets
 - Support for 50 more hashes

### Fixed
 - Calculation error on Analytics where on the global page for number of cracked hashes vs uncracked hashes.
 
## [v0.6.1-beta] - 2017-04-25
### Added
 - Support for 38 more hashes
### Fixed
 - Raced condition when importing wordlists (both via gui and cli)
 - Bug where NetNTLMv1 and NetNTLMv2 hashes were not properly importing
 - Bug where usernames were not being parsed when importing NetNTLMv1 and NetNTLMv2 hashes

## [v0.6.0-beta] - 2017-03-28
### Added
 - Resque 'management' queue for system jobs
 - Background job for automatically importing wordlists scp'd to control/wordlists
 - Background job for removing old temp files.
 - Support for user to set a SMTP Sender Name
 - Themes!! (we personally like slate)
 - Support for new hashcat settings: --force, --opencl-device-types, --workload-profile, --gpu-temp-disable, --gpu-temp-abort, --gpu-temp-retain
 - Ability to copy/paste hashfiles into new jobs as their being created
 - Support for smart hashdump and username:[NTLM hash] hashfiles
 - Two new rule sets for high and low utility
 - Support for cracking and importing hashes with salts
 - Support for more hashes: [import only] md5($pass.$salt), md5($salt.$pass), md5(unicode($pass).$salt), md5($salt.unicode($pass)), 	HMAC-MD5 (key = $pass), HMAC-MD5 (key = $salt), sha1($pass.$salt), sha1($salt.$pass), sha1(unicode($pass).$salt), sha1($salt.unicode($pass)), HMAC-SHA1 (key = $pass), HMAC-SHA1 (key = $salt), Domain Cached Credentials (DCC), MS Cache, 	sha256($pass.$salt), sha256($salt.$pass), sha256(unicode($pass).$salt), sha256($salt.unicode($pass)), HMAC-SHA256 (key = $pass), HMAC-SHA256 (key = $salt), vBulletin < v3.8.5 and vBulletin >= v3.8.5
 
### Changed
 - Moved queue management for cracking tasks from redis/resqueu to mysqld
 - Expanded hashes table to allow for hashes up to 1024 characters in length
 - Rake task db:upgrade will now automatically detect previous versions (starting with v0.5.1) and automatically upgrade your db and import current settings, users, cracked hashes, wordlists to new versions as they come out
 - Startup proccess from two cmds to single foreman cmd
 - Cracked output is now in hex format (better for importing symbols and other characters)
 - Default sender address of emails from no-reply@Pony to no-reply@hashview
 - Global settings is split into multiple panels for easier use.
 
### Fixed
 - Bug in combinator crack command
 - Searches now include wildcards before/after submitted string
 - Searches now remember what search type you entered
 - Jumbo tron now properly updates status on page refresh
 - Issue where Queued jobs are not being displayed on home page should be fixed
 - You should now be prevented from editing a job that is running or queued
 - Prevent the assignment of the same task twice to a job

## [v0.5.1-beta] - 2016-02-19
### Changed
- changed from Sinatra classic style to modular style

## [v0.5-beta] - 2016-02-04
### Changed
- changed db schema to accomadate very large datasets
- improved performance via db queries

## [v0.4-beta] - 2016-10-18
### Changed
- Encompasses all changes since the v0.3 tagged release

## [v0.3-beta] - 2016-10-18
### Changed
- Moved retrochecks from hashfile import to job start

### Fixed
- Fixed unauth message on invalid login attempts

## 2016-10-11
### Added
- Added download of uncracked hashes in download section

### Fixed
- Fixed bug where download file name of cracked passwords was not properly rendering

## 2016-10-10
### Fixed
- Fixed bug where stopping jobs and tasks failed to handle properly

### Changed
- Updated Job descriptions

## 2016-10-09
### Changed
- Changed support format for DSUser from v1.2 to v1.3

## 2016-10-07
### Changed
- Code Cleanup

## 2016-10-06
### Added
- Added support for Combinator attacks

## 2016-10-03
### Added
- Added Support for NTDSXtract (dsusers)
- Added 'importing' status for jobs and tasks

## 2016-10-02
### Removed
- Removed ability for basewords in analytics to be null

### Changed
- Rounded Run time calculated in analytics
- Prevented the deletion of a task if un an active job

## 2016-09-29
### Changed
- Code Cleanup

## 2016-09-28
### Added
- Expanded test cases
- Removed old 

## 2016-09-26
### Changed
- Fixed NetNTLMv1 and NetNTLMv2 parse bug
- Updated Jobsq to support NetNTLMv1 and NetNTLMv2

## 2016-09-23
### Removed
- Removed implicit downcase for non-LM hash imports


[v0.5.1-beta]: https://github.com/hashview/hashview/compare/v0.5-beta...v0.5.1-beta
[v0.5-beta]: https://github.com/hashview/hashview/compare/v0.4-beta...v0.5-beta
[v0.4-beta]: https://github.com/hashview/hashview/compare/v0.3-beta...v0.4-beta
[v0.3-beta]: https://github.com/hashview/hashview/compare/v0.1-alpha...v0.3-beta
