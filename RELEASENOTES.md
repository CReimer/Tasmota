## Migration Information
See [wiki migration path](https://github.com/arendst/Sonoff-Tasmota/wiki/Upgrade#migration-path) for instructions how to migrate to a major version. Pay attention to the following version breaks due to dynamic settings updates:

1. Migrate to **Sonoff-Tasmota 3.9.x**
2. Migrate to **Sonoff-Tasmota 4.x**
3. Migrate to **Sonoff-Tasmota 5.14**
4. Migrate to **Sonoff-Tasmota 6.x**

## Release notes
### Change in default initial configuration tool
Firmware binary **sonoff-classic.bin** supports **WifiManager, Wps and SmartConfig** for initial configuration. The default tool is **Wps**.

To save memory space all other binaries support **WifiManager only**.

See _changelog.ino how to enable them again.
- Define WIFI_CONFIG_TOOL now contains the default behaviour once a SSID has been configured.
- If no SSID is configured making a wifi connection impossible the new define WIFI_CONFIG_NO_SSID will be used.
- While define WIFI_CONFIG_NO_SSID is set to WIFI_WPSCONFIG in my_user_config.h the compiler will check for define USE_WPS and if not enabled WIFI_CONFIG_NO_SSID will default to WIFI_MANAGER using the webserver. If define USE_WEBSERVER is also not enabled WIFI_CONFIG_NO_SSID will default to WIFI_SMARTCONFIG. If define USE_SMARTCONFIG is also not enabled WIFI_CONFIG_NO_SSID will default to a new option WIFI_SERIAL allowing to enter wifi parameters to serial which is always possible.

## Supported Modules
The following hardware modules are supported.

Module            | Description
------------------|-----------------------
01 Sonoff Basic   | Sonoff Basic Wifi Smart Switch
02 Sonoff RF      | Sonoff RF Wifi Smart Switch with RF (434MHz) receiver
03 Sonoff SV      | Sonoff SV Safe Voltage Wifi Smart Switch
04 Sonoff TH      | Sonoff TH10/TH16 Wifi Smart Switch with Sensor connection
05 Sonoff Dual    | Sonoff Dual Wifi Smart Switch
06 Sonoff Pow     | Sonoff Pow Wifi Smart Switch with Energy Monitoring
07 Sonoff 4CH     | Sonoff 4CH 4-gang Wifi Smart Switch
08 Sonoff S2X     | Sonoff S20/S26 Wifi Smart Socket
09 Slampher       | Sonoff Slampher Wifi Smart Light Bulb Socket with RF (434MHz) receiver
10 Sonoff Touch   | Sonoff Touch Wifi Light Switch
11 Sonoff LED     | Sonoff Led Wifi Led Pack (Retired)
12 1 Channel      | 1 Channel Inching/Self Locking Wifi Switch 5V/12V
13 4 Channel      | 4 Channel Inching/Self Locking Wifi Switch (Retired)
14 Motor C/AC     | Motor Clockwise/Antoclockwise Wifi Switch (Retired)
15 ElectroDragon  | Electrodragon Wifi IoT Board
16 EXS Relay(s)   | Electronic Experience Store 1 or 2-gang Wifi Module
17 WiOn           | WiOn Wifi Smart Socket
18 Generic        | Any ESP8266/ESP8285 device like WeMos and NodeMCU
19 Sonoff Dev     | Sonoff Dev Wifi Development Board
20 H801           | H801 Wifi RGBWW Led Controller
21 Sonoff SC      | Sonoff SC Wifi Environmental Monitor
22 Sonoff BN-SZ   | Sonoff BN-SZ01 Wifi Ceiling Led (Retired)
23 Sonoff 4CH Pro | Sonoff 4CH Pro 4-gang Wifi Smart Switch
24 Huafan SS      | HuaFan Wifi Smart Socket
25 Sonoff Bridge  | Sonoff RF (434MHz) transceive to Wifi Bridge
26 Sonoff B1      | Sonoff B1 Wifi RGBWW Led Bulb
27 AiLight        | Ai-Thinker RGBW Led Bulb
28 Sonoff T1 1CH  | Sonoff T1 1-gang Wifi Light Switch
29 Sonoff T1 2CH  | Sonoff T1 2-gang Wifi Light Switch
30 Sonoff T1 3CH  | Sonoff T1 3-gang Wifi Light Switch
31 Supla Espablo  | 2-gang Wifi Module
32 Witty Cloud    | Witty Cloud ESP8266 Wifi Development Board
33 Yunshan Relay  | ESP8266 Wifi Network Relay Module
34 MagicHome      | MagicHome, Flux-light and some Arilux LC10 RGB(W) Led Controller
35 Luani HVIO     | Luani ESP8266 Wifi I/O Module
36 KMC 70011      | KMC Wifi Smart Socket with Energy Monitoring
37 Arilux LC01    | Arilux AL-LC01 RGB Led Controller
38 Arilux LC11    | Arilux AL-LC11 RGBWW Led Controller
39 Sonoff Dual R2 | Sonoff Dual R2 Wifi Smart Switch
40 Arilux LC06    | Arilux AL-LC06 RGB(WW) Led Controller
41 Sonoff S31     | Sonoff S31 Wifi Smart Socket with Energy Monitoring
42 Zengge WF017   | Zengge WF017 Wifi RGB(W) Led Controller
43 Sonoff Pow R2  | Sonoff Pow R2 Wifi Smart Switch with Energy Monitoring
44 Sonoff iFan02  | Sonoff iFan02 Wifi Smart Ceiling Fan with Light
45 BlitzWolf SHP  | BlitzWolf BW-SHP2, BW-SHP6, HomeCube SP1, Gosund SP111, Teckin SP22 Wifi Smart Switch with Energy Monitoring
46 Shelly 1       | Shelly 1 Open Source Wifi Relay Module
47 Shelly 2       | Shelly 2 Wifi 2-gang Relay Module with Energy Monitoring
48 Xiaomi Philips | Xiaomi Philips Wifi WW Led Bulb
49 Neo Coolcam    | Neo Coolcam Wifi Smart Socket
50 ESP Switch     | ESP Switch 4-gang Wifi Switch with Leds
51 OBI Socket     | OBI Wifi Smart Socket
52 Teckin         | Teckin SP20 Wifi Smart Switch with Energy Monitoring
53 AplicWDP303075 | Aplic WDP 303075 CSL Wifi Smart Switch with Energy Monitoring
54 Tuya Dimmer    | MIUO (and other Tuya based) Wifi Dimmer for Incandescent Lights and Led
55 Gosund SP1 v23 | Gosund SP1 v2.3 Wifi Smart Switch with Energy Monitoring
56 ARMTR Dimmer   | ARMtronix Wifi dimmer for Incandescent Lights and Led
57 SK03 Outdoor   | SK03 Outdoor Wifi Smart Switch with Energy Monitoring
58 PS-16-DZ       | PS-16-DZ  Wifi dimmer for Incandescent Lights and Led
59 Teckin US      | Teckin US and ZooZee SA102 Wifi Smart Switch with Energy Monitoring
60 Manzoku strip  | Manzoku Wifi Smart Power Strip with four Relays
61 OBI Socket 2   | OBI 2 Wifi Smart Socket 
62 YTF IR Bridge  | YTF Infra Red Wifi Bridge
63 Digoo DG-SP202 | Digoo DG-SP202 Dual Wifi Smart Switch with Energy Monitoring
64 KA10           | Smanergy KA10 Wifi Smart Wall Switch with Energy Monitoring
65 Luminea ZX2820 | Luminea ZX2820 Wifi Smart Switch with Energy Monitoring
66 Mi Desk Lamp   | Mi Desk Lamp with rotary switch and Wifi
67 SP10           | Tuya SP10 Wifi Smart Switch with Energy Monitoring
68 WAGA CHCZ02MB  | WAGA life CHCZ02MB Wifi Smart Switch with Energy Monitoring
69 SYF05          | Sunyesmart SYF05 RGBWW Wifi Led Bulb

## Provided Binary Downloads
The following binary downloads have been compiled with ESP8266/Arduino library core version **2.4.2** patched with the Alexa fix.

- **sonoff-minimal.bin** = The Minimal version allows intermediate OTA uploads to support larger versions and does NOT change any persistent parameter. This version **should NOT be used for initial installation**.
- **sonoff-classic.bin** = The Classic version allows **initial installation** using either WifiManager, Wps or SmartConfig.
- **sonoff.bin** = The Sonoff version without Wps and SmartConfig configuration but adds more sensors.
- **sonoff-BG.bin** to **sonoff-TW.bin** = The Sonoff version without Wps and SmartConfig configuration in different languages.
- **sonoff-sensors.bin** = The Sensors version without Wps and SmartConfig configuration but adds even more useful sensors.
- **sonoff-display.bin** = The Display version without Wps and SmartConfig configuration but adds display support.
- **sonoff-knx.bin** = The Knx version without Wps and SmartConfig configuration and some other features but adds KNX support.

### Available Features and Sensors

| Feature or Sensor              | minimal | basic | classic | sonoff | knx  | sensors | Remarks
|--------------------------------|---------|-------|---------|--------|------|---------|--------
| MY_LANGUAGE en-GB              | x | x | x | x | x | x |
| MQTT_LIBRARY_TYPE PUBSUBCLIENT | x | x | x | x | x | x |
| USE_WPS                        | - | - | x | - | - | - | WPS
| USE_SMARTCONFIG                | - | - | x | - | - | - | SmartConfig
| USE_ARDUINO_OTA                | - | - | - | - | - | - |
| USE_DOMOTICZ                   | - | - | x | x | x | x |
| USE_HOME_ASSISTANT             | - | - | - | x | x | x |
| USE_MQTT_TLS                   | - | - | - | - | - | - |
| USE_KNX                        | - | - | - | - | x | - |
| USE_WEBSERVER                  | x | x | x | x | x | x | WifiManager
| USE_EMULATION                  | - | x | x | x | - | x |
| USE_DISCOVERY                  | - | - | x | x | x | x |
| WEBSERVER_ADVERTISE            | - | - | x | x | x | x |
| MQTT_HOST_DISCOVERY            | - | - | x | x | x | x |
| USE_TIMERS                     | - | x | - | x | x | x |
| USE_TIMERS_WEB                 | - | x | - | x | x | x |
| USE_SUNRISE                    | - | x | - | x | x | x |
| USE_RULES                      | - | x | - | x | x | x |
|                                |   |   |   |   |   |
| USE_ADC_VCC                    | x | x | x | x | x | - |
| USE_DS18B20                    | - | - | - | - | - | - | Single sensor
| USE_DS18x20                    | - | - | x | x | x | x | Multiple sensors
| USE_DS18x20_LEGACY             | - | - | - | - | - | - | Multiple sensors
|                                |   |   |   |   |   |   |
| Feature or Sensor              | minimal | basic | classic | sonoff | knx  | sensors |
| USE_I2C                        | - | - | - | x | x | x |
| USE_SHT                        | - | - | - | x | x | x |
| USE_HTU                        | - | - | - | x | x | x |
| USE_BMP                        | - | - | - | x | x | x |
| USE_BME680                     | - | - | - | - | - | x |
| USE_BH1750                     | - | - | - | x | x | x |
| USE_VEML6070                   | - | - | - | - | - | x |
| USE_ADS1115                    | - | - | - | - | - | x |
| USE_ADS1115_I2CDEV             | - | - | - | - | - | - |
| USE_INA219                     | - | - | - | - | - | x |
| USE_SHT3X                      | - | - | - | x | x | x |
| USE_TSL2561                    | - | - | - | - | - | x |
| USE_MGS                        | - | - | - | - | - | x |
| USE_SGP30                      | - | - | - | x | x | x |
| USE_SI1145                     | - | - | - | - | - | x |
| USE_LM75AD                     | - | - | - | x | x | x |
| USE_APDS9960                   | - | - | - | - | - | - |
| USE_MCP230xx                   | - | - | - | - | - | - |
| USE_PCA9685                    | - | - | - | - | - | - |
| USE_MPR121                     | - | - | - | - | - | - |
| USE_CCS811                     | - | - | - | - | - | - |
| USE_MPU6050                    | - | - | - | - | - | - |
| USE_DS3231                     | - | - | - | - | - | - |
| USE_MGC3130                    | - | - | - | - | - | - |
| USE_MAX44009                   | - | - | - | - | - | - |
| USE_SCD30                      | - | - | - | - | - | - |
|                                |   |   |   |   |   |   |
| Feature or Sensor              | minimal | basic | classic | sonoff | knx  | sensors |
| USE_SPI                        | - | - | - | - | - | - |
| USE_MHZ19                      | - | - | - | x | x | x |
| USE_SENSEAIR                   | - | - | - | x | x | x |
| USE_PMS5003                    | - | - | - | x | x | x |
| USE_NOVA_SDS                   | - | - | - | x | x | x |
| USE_PZEM004T                   | - | - | - | x | x | x |
| USE_PZEM_AC                    | - | - | - | x | x | x |
| USE_PZEM_DC                    | - | - | - | x | x | x |
| USE_MCP39F501                  | - | x | - | x | x | x |
| USE_SERIAL_BRIDGE              | - | - | - | x | x | x |
| USE_SDM120                     | - | - | - | - | - | x |
| USE_SDM630                     | - | - | - | - | - | x |
| USE_MP3_PLAYER                 | - | - | - | - | - | x |
| USE_TUYA_DIMMER                | - | x | - | x | x | x |
| USE_ARMTRONIX_DIMMERS          | - | x | - | x | x | x |
| USE_PS_16_DZ                   | - | x | - | x | x | x |
| USE_AZ7798                     | - | - | - | - | - | - |
| USE_PN532_HSU                  | - | - | - | - | - | - |
| USE_IR_REMOTE                  | - | - | - | x | x | x |
| USE_IR_HVAC                    | - | - | - | - | - | x |
| USE_IR_RECEIVE                 | - | - | - | x | x | x |
| USE_WS2812                     | - | - | x | x | x | x |
| USE_WS2812_DMA                 | - | - | - | - | - | - |
| USE_ARILUX_RF                  | - | - | - | x | x | x |
| USE_SR04                       | - | - | - | x | x | x |
| USE_TM1638                     | - | - | - | - | - | x |
| USE_HX711                      | - | - | - | x | x | x |
| USE_RF_FLASH                   | - | - | - | x | x | x |
| USE_TX20_WIND_SENSOR           | - | - | - | x | x | x |
| USE_RC_SWITCH                  | - | - | - | x | x | x |
| USE_RF_SENSOR                  | - | - | - | - | - | x | AlectoV2 only
| USE_SM16716                    | - | x | x | x | x | x |
| USE_DISPLAY                    | - | - | - | - | - | - |

## Changelog
Version 6.5.0 20190315

 * Tbd