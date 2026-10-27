# PuKK Workspace Firmware Changelog
<!-- ## Version 1.x.x -->
<!-- ### Features -->

<!-- ### Bug Fixes -->

<!-- ### Documentation -->

<!-- ======================== -->

# Version 1.1.0

### Features
- Added MQTT implementation
	- Replaces HTTP when specified in configuration
		- Use `"protocol": "MQTT"`
	- Configure MQTT using the configuration
	- Allows for Username/Password Authentication
	- Also available with TLS. Use `mqtts://` instead of `mqtt://` as URI prefix
- Added outbound Authorization header for Bearer tokens.
	- A value in the configuration of `"token123"` will translate to `"authorization": "Bearer token123"`
- Added REST API Authorization requirement using ProDVX API Authorization tokens
	- A Bearer token must be provided by using `ProdvxPukk` as device key
- Added custom header support. Define these in the configuration.
- Added Received Signal Strength Indicator as header `"X-RSSI"`.
- Added `force=1` query parameter to the first `/api/poll` request after boot.


### Bug fixes
- Fix of HTTP Asynchronous issues
- Fix /deviceInfo endpoint
- Fix trailing slash
- Fixed NFC implementation to improve capabilities
	- Now also supports Phone Tag Emulation through a `HostApduService`.
- Fix multiple durations not being used for leds
- Fix rainbow mode not applying counter_clockwise


### Documentation
- Added `configuration/` to documentation for configuration specific examples and guidance.
- Added `configuration/example_config.json`
- Updated User Manual
	- Added Mounting paragraph
	- Added more detailed information about NFC card requirements
	- Added FAQ
	- Improved clarity in various paragraphs
	- Fixed Heading Numbering
- Updated Event Specification
- Updated REST API Specification
- Removed `default_config.jsonc` as it was not default, and did not improve 

<!-- ======================== -->

## Version 1.0.3
- Added Changelog text
- Implement NFC Request on all other NFC Tag Types
- Implement WiFi retry logic on network disconnect
	- By default retries immediately after losing connection, then retries every 10 minutes.
	- Configurable via configuration per seconds.
- Integrated SSL Certficates for HTTPS connection on outgoing requests (List for certificates can be found [here](https://www.dropbox.com/scl/fi/l58gqt4un3gx0zneoh0eg/PuKK_Certs_v1.0.3.csv?rlkey=1r3kq06mj1ega16jqkdjh4ygl&st=sfzk7l8u&dl=0))
- Removed some PuKK API Endpoints that were focused on On Premise solutions. Might return at a later point.
- Updated API Specification

<!-- ### Bug fixes -->

### Documentation
- Updated User Manual

<!-- ======================== -->

## Version 1.0.2

### Bug fixes
- Fix subscription issue appending server address to subscription address

---
