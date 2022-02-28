# Changelog
All notable changes to this project will be documented in this file.

## 1.1.1 - 10.02.2022

### Changed
  
- Removed gzip compression handling
 
## 1.1.0 - 08.02.2022
   
### Added

- Content Interaction Tracking
- Track traffic source by platform and version of SDK
- Added possibility to assign a device ID
 
### Changed
  
- Dispatch interval was changed from 120 to 30s
 
### Fixed
 
- Issue with handling response status code 202 
- Tracking ecommerce transactions: handling of thousandths separator fixed in `price()` method; fixed an issue with `quantity()` method sending data as a strings instead of integers
- Fixed an issue of missing e-mail in the request after using the method `setUserMail()` 
- Fixed an issue with incorrect URL keyword parsing in the Tracking campaigns method
- Anonymisation has been improved and optimised. Now, when anonymisation is enabled, device ID, e-mail and user ID are not sent to the adience manager
- Minor fixes and improvements