# Changelog
All notable changes to this project will be documented in this file.

## 2.2.0 - 29.07.2025

### Added
- VersionCode next to versionName. From now on, versionCode will be sent with each event, just as build number is sent in PIWIK PRO iOS SDK.

### Fixed
- Missing _viewts parameter in some request on Android SDK.

## 2.1.0 - 21.02.2025

### Added

- Currency conversion for `goal` and all ecommerce methods.

## 2.0.0 - 05.09.2024

### Added
Cross-platform tracking features

The release will disable session hash support by default (sh=0 parameter). 
The main reason is the high likelihood of mobile devices sharing altogether the same User-Agent header (due to visitors using the same mobile app) and the same public IP address due to being connected to the same network (e.g. shopping malls, train stations, airports). The more densely the area is populated, the more it impacts the quality of data collection. Another important reason is that the cookie ID (primary visitor identifier) is much less likely to change when using mobile SDKs compared to the browser environment.
Documentation with instructions on how to configure the cross-platform feature should appear soon in the Help Center.

- property `sessionHash` to control the SessionHash feature
- new methods dedicated to cross-platform tracking `setVisitorIdFromDeepLink`, `getUserAgent`

## 1.2.3 - 10.06.2024

### Added
- `visitorIDLifetime` property. 
The variable introduces the possibility of setting the expiry time of the visitorID. If the visitorID expires, a new visitorID will be created automatically. In the tracker, the user whose visitorID expires will appear as a new visitor.
The mechanism needs the visitorID creation time to work properly. After upgrading to this version of the SDK, the visitorID creation time will be the time of the first SDK initialisation after the upgrade.
Default value for this variable is 0, which results in this feature being disabled.
The `visitorIDLifetime` is in miliseconds.

## 1.2.2 - 11.03.2024

### Fixed
- Fixed the issue with a dispatcher that in some cases sent only the first batch of events.

## 1.2.1 - 15.02.2024

### Added
- New events" `applicationInstall` and `applicationUpdate`.

### Fixed
- Fixed the issue with the change of dispatchIntervalTime not affecting already queued events.
- Fixed the issue with events not being saved in device memory after being sent.

## 1.2.0 - 13.09.2023

### Added
- New e-commerce events: `ecommerceProductDetailView`, `ecommerceAddToCart`, `ecommerceRemoveFromCart`, `ecommerceCartUpdate`, `ecommerceOrder`.

### Fixed
- Fixed the issue with emptying the queue of pending events when the opt out flag is switched from true to true.

### Changed
- Changed the number of allowed characters for custom dimension value from 256 to 1024.

## 1.1.13 - 03.07.2023

### Fixed
- Fixed the issue with decreasing number of returning visitors.

## 1.1.12 - 24.04.2023

### Added
- 's', 'm' 'h' parameters in requests from Android SDK.

### Changed
- Changed the parameter type in the `campaign` method from `URL` to `String`.

## 1.1.11 - 24.03.2023

### Added
- `preserveSessionParameters` parameter was added to the `startNewSession` method. By default, calling this method deletes all parameters(`custom variables`, `custom dimensions`, `campaigns`) of the current session. If you want the parameters of the current session to be preserved, pass the flag `true` as a parameter to the method.

### Changed
- The mechanism for initiating a new session every 30 minutes has been removed. From now on, a new session can only be triggered using the `startNewSession` method.

## 1.1.10 - 04.02.2023

### Fixed
- Fixed the issue with wrong order of events in the tracker.

### Added
- Introduced support for UTM tags and custom tags in campaign tracking and deep links.

### Changed
- The way in which the `deviceID` is created has been changed. From now on, the `deviceID` is `null` by default. The `deviceID` can be set using the `setDeviceId` method.
The `setTrackDeviceId` method has been removed.

## 1.1.9 - 20.01.2023

### Fixed
- Fixed a bug that appears under certain circumstances related to an exception java.lang.ClassNotFoundException.

## 1.1.8 - 08.12.2022

### Changed
- Removed deprecated `download` method responsible for sending the event of application installation. 

### Fixed
- Fixed the issue with the incorrect order of values for properties in the `EcommerceItems` object in the Tracking ecommerce method when one of the properties(e.g. category) does not have an assigned value.

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
