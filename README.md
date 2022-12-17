# ESPHome Packages

This repository is a collection of premade packages for various ESP based devices, intended for use in ESPHome as remote packages.

Each folder contains packages for a specific device, with the folders named for devices themselves.
Each folder also contains a readme describing the use of each package in the folder.

## Supported Devices

[Sonoff S31](Sonoff_S31/README.md)

[Sonoff MiniR2](Sonoff_MiniR2/README.md)

[BN-Link BNC-60](BN-Link_BNC-60/README.md)

[KMC 4-Outlet (30608)](KMC_30608/README.md)

## Generic Helper Packages

Diagnostics

D1-Mini

DeepSleep

Bosch BMP280

Sensirion SHT31

## Using Remote Packages

There are three ways to add these remote packages to an ESPHome configuration:

```
packages:

  s31_package_short_single: github://SiliconAvatar/ESPHomePackages/Sonoff_S31/s31.yaml

  s31_package_long_single:
    url: https://github.com/SiliconAvatar/ESPHomePackages
    ref: main #Branch
    file: Sonoff_S31/s31.yaml
    refresh: 1d
    
  s31_package_long_multiple:
    url: https://github.com/SiliconAvatar/ESPHomePackages
    ref: main #Branch
    files: [Sonoff_S31/s31.yaml, Sonoff_S31/s31power.yaml]
    refresh: 1d
```

The first two methods specify only an individual file to add. This must be repeated for each file you wish to include.
The third method allows you to specify multiple packages to include.

The second two methods allow additional configuration options such as specifying which branch of the repository you wish to pull from, and how frequently to refresh the remote package.

See the readme files in the specific device folders for further usage information.
