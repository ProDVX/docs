# Configuration
This documents the fields that can be configured.

## Fields
Elaboration on certain fiels can be found below the table
| Field Name | Type | Required | Description | Default value | Constraints |
|---|---|:---:|---|:---:|:---:|
| wifi_ssid | string | X | SSID of the WiFi Network |  |  |
| wifi_pass | string | X | Password of the WiFi Network |  |  |
| wifi_hidden | boolean | X | Whether the Wi-Fi network is hidden. |  |  |
| cms_server_address | string | X | Address of the server for the PuKK to connect to.  |  |  |
| do_ota | boolean | X | Whether to perform OTA updates. |  |  |
| poll_interval_ms | integer |  | Interval in ms for polling the CMS server. | 5000 | 0 - 65536 |
| wifi_retry_interval_ms | integer |  | The interval in seconds to wait before retrying Wi-Fi connection. | 600 |  min. 0 |

### CMS Server Address
The PuKK will **always** put the action and MAC address behind this value as such: `?action=example&mac=12:34:56:78:90:ab`.

For example:

A configuration with
```
{
	"cms_server_address": "https://cms.example.com/pukk_event"
}
```

would create the request on a button press

```
POST https://cms.example.com/pukk_event?action=short_press&mac=12:34:56:78:90:ab
```