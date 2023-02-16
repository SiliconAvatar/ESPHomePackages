# Dual PZEM-016 Modbus Package
<!-- 
    ToDo:
    Add Photo od device
    Add photo of sensors created
    Describe the TTL adapter
    Describe wiring
-->

---

This is a package for communicating with two PZEM-016 modules over modbus.
This assume the use of a RS485 to TTL UART converter module is used.


## pzem016.yaml
This file contains the full configuration for the device.
This includes the basic device definitions as well as power monitoring.


## Sample configuration of an KMC 4-Outlet (30608) in ESPHome

```
esphome:
  name: ${device_name}
  friendly_name: HousePower
  comment: $device_description

substitutions:
  device_description: Modbus Power Meter

# Note:
# The "friendly_name" name will be used for the config entry, the device name, 
# and will be automatically prefixed to all of the entities where needed by Home Assistant.

packages:
  wifi: !include common/wifi.yaml
  diagnostics_package:
    url: https://github.com/SiliconAvatar/ESPHomePackages
    ref: main #Branch
    files: [Common/diagnostics.yaml]
    refresh: 1d
  kmc30608_packages:
    url: https://github.com/SiliconAvatar/ESPHomePackages
    ref: main #Branch
    files: [PZEM-016/pzem016_dual.yaml]
    refresh: 1d

# Enable Other-The-Air Updates
ota:
  password: "aaa1aaa2aaa3aaa4aaa5aaa6aaa7aaa"         # Enter OTA Password here, if it exists. If not, remove this line (Keep the "ota:" line).

# Enable Home Assistant API
api:
  encryption:                                               # If not using encryption, remove this line, and the one below. Keep the "api:" line.
    key: "AwbCDKVWN7zacrd63maE7mnG45lZsVZH/1HSPmtE0KI="     # Enter encryption Key here, if it exists. If not, remove this line.
```

## Entities Created

This packages create 1 class of entities.


### Sensors:


- Average Voltage </br>
- Total Current </br>
- Average Frequency </br>
- Total Power </br>
- Average Power Factor </br>
- Total Daily Energy </br>
- Phase A Voltage </br>
- Phase A Current </br>
- Phase A Frequency </br>
- Phase A Power </br>
- Phase A Power Factor </br>
- Phase B Voltage </br>
- Phase B Current </br>
- Phase B Frequency </br>
- Phase B Power </br>
- Phase B Power Factor </br>