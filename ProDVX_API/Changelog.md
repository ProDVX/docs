# ProDVX API Release Notes

## 1.5a

### Changes

- Added Sportable Devices to LED integration

### Bug Fixes

- Fixed an installation flag for FLAG_MUTABLE for Android 14+


<!-- ======================== -->

## 1.4b

### Changes

 - `/hideSystemBars`: Added support for some UW devices to hide the system bars
 - `/getScreenshot`: Now cleares the screenshot folder of PNG files when a screenshot is made to clear space
 - `/clearCache`: Added function to clear the cache memory of the API
 - Added allowance through CORS for localhost requests. All API requests to localhost should now work as expected from the browser.