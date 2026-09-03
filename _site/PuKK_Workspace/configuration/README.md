# PuKK Configuration
This documents the fields that can be configured.

## Fields
Elaboration on fields can be found below the table

| Field Name | Type | Required | Description | Default value | Constraints |
|:---|---|:---:|---|:---:|:---:|
| wifi_ssid | string | X | SSID of the WiFi Network |  |  |
| wifi_pass | string | X | Password of the WiFi Network |  |  |
| wifi_hidden | boolean | X | Whether the Wi-Fi network is hidden. |  |  |
| wifi_retry_interval_ms | integer |  | The interval in seconds to wait before retrying Wi-Fi connection. | 600 |  min. 0 |
| protocol | string | X | The protocol to use for communication. | HTTP | 'HTTP' or 'MQTT'
| enable_ota | boolean | X | Whether to perform OTA updates. |  |  |
| http_server_address | string | X | Address of the server for the PuKK to connect to.  |  |  |
| http_poll_interval_ms | integer |  | Interval in ms for polling the CMS server. | 5000 | 0 - 65536 |
| http_authorization_token | string | | The authorization token for the server. | |
| http_custom_headers | array | | Custom headers to be sent to the server. | |
| mqtt_broker | string | | The address of the MQTT broker. Use 'mqtts://' for making use of TLS connections. | |
| mqtt_port | integer | | The port of the MQTT broker. | | 0-65535
| mqtt_username | string | | The username for the MQTT broker. |
| mqtt_password | string | | The password for the MQTT broker. |
| mqtt_topic_prefix | string | | The prefix for the MQTT topics. | pukk/ |

### Communication Protocol
You can use either HTTP (Polling) or MQTT as your main communication protocol. You can select one or the other by the "protocol" option in the configuration.

### HTTP Server Address
The PuKK will **always** put the action and MAC address behind this value as such: 

`?action=example&mac=12:34:56:78:90:ab`.

For example:

A configuration with
```
{
	"http_server_address": "https://cms.example.com/pukk_event"
}
```

would create the request on a button press

```
POST https://cms.example.com/pukk_event?action=short_press&mac=12:34:56:78:90:ab
```
### SSL/TLS (HTTPS/MQTTS)
If your server requires HTTPS ensure that the http_server_address starts with https://


If your broker is TLS secured, ensure that the mqtt_broker starts with mqtts://

