# PlatformIO ESP-MDF example 

## Description 

This project provides a base example for the usage of ESP-MDF within PlatformIO. 

## Configuring 

Refer to [esp-mdf](https://github.com/espressif/esp-mdf/tree/master/examples/get-started). This is the "get started" example, which lets two or more nodes communicate with each other. There is one root node and 1 or more non-root nodes. 

To configure a device to be a root or non-root device, look into the `platformio.ini` regarding the macro `CONFIG_DEVICE_TYPE` (either 0 for root of 1 for non-root). 

All other configurable settings for the components reside there, too, for the moment. The settings there are all default settings from the several `Kconfig` files ([mcommon](https://github.com/espressif/esp-mdf/blob/master/components/mcommon/Kconfig), [mwifi](https://github.com/espressif/esp-mdf/blob/master/components/mwifi/Kconfig))

Default configuration flag for other components are still underway, but the 'get started' example compiles.

## More examples / refactor ? 

This project has all libraries locally in `lib/` and doesn't use globally-registered libraries. This will be refactored so that these libraries are registered with PlatformIO's library registry.  Then this repository will also contain multiple example folders (every example provided in esp-mdf).

## Enable PSRAM? 

For examples which may need more RAM and boards which have PSRAM, add the needed PSRAM flags from [here](https://github.com/maxgerhardt/pio-esp-adf-example/blob/master/platformio.ini#L12-L26).

## Caveats

When creating a new project based from this, don't forget to add import `sdkconfig.h` overrides as e.g. seen in https://github.com/espressif/esp-mdf/blob/master/examples/get-started/sdkconfig.defaults, as this may drastically change the behaviour / stability of the code.

## Codebase

All ESP-MDF code present is a momentary snapshot at [esp-mdf@67a0a5b](https://github.com/espressif/esp-mdf/commit/67a0a5bd72ed284f7a5bf50694f1ab942319dd6b) (09 May 2019).

## License

All ESP-MDF code has the 'ESPRESSIF MIT License'.
