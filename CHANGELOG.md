# Changelog
All notable changes to this project will be documented in this file.

## 1.1.7 - 08.11.2022

### Changed
- Changed data type for `idGoal` parameter in `goal` method from `Int` to `String`
- The `outling` method will accept any type of scheme in the URL parameter

## 1.1.6 - 16.09.2022

### Changed
- Upgrade of libraries versions. Internal fixes and improvements.
- Removed warnings about unsupported parameters in social interaction and exception events. Removed deprecated parameters.

## 1.1.5 - 01.05.2022

### Changed
- Campaign details are not immediately sent out as a separate event but are attached to the first screen event.

## 1.1.4 - 10.05.2022

### Changed
- The `socialInteraction`, `exception` and `sendApplicationDownload` events are no longer tracked as screen views but as custom events.
- The `target` argument in the `socialInteraction` method and `isFatal` in the `exception` method are no longer used and will soon be removed from the signatures of these methods.

## 1.1.3 - 31.03.2022

### Changed
  
- Unified with Piwik PRO iOS SDK the methods for creating custom variables, both visit and screen scope
- Unified with Piwik PRO iOS SDK the method for creating custom dimensions


## 1.1.2 - 02.03.2022

### Changed
  
- Added an empty initializer to the exception event

### Added

- New application download event
- New download event

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
- Minor fixes and improvements- Minor fixes and improvements- Minor fixes and improvements
