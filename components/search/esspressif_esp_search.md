# Esspressif ESP32 micro/radio search

## Selection criteria
- Price
  - $2-3
    - ESP32-S2
    - ESP32-C*
  - $3-4
    - ESP32-S3
- Power
- Module / Dev kits
- Availability

## Lead contenders

- ESP-WROOM-02
  - Main selection reasons:
   - 2.7-3.6V
   - $3-$3.50
   - [7-16k in stock](https://octopart.com/search?q=esp-wroom-02&currency=USD&specs=0)
   - [dev kit](https://octopart.com/search?q=ESP8266-DevKitC&currency=USD&specs=0)


## Module Notes

- [Product selector](https://products.espressif.com/#/product-selector?language=en&names=)
- ESP (classic?) WROOM | Xtensa LX6 micro
  - 2.7V-3.6V
    - Having this voltage margin above a coin-cell will improve the life of the device and speed up development/testing
    - all other modules use 3.0 V min, which is right where most coincells sit. We would have to add step-up regulator, and that will drain more current.
  - ESP32 WRoom-DA (two complementary antennas)
  - dev kits
    - ESP8266-DevKitC-02D-F ESP-WROOM-02D
    - ESP8266-DevKitC-02U-F ESP-WROOM-02U

- ESP32-S2 Mini/Solo still in production $2-3 (mcu + wifi)
  - Price: $2-3
  - Power: Ivdd 0.5A min (too much current draw)
    - Work mode Description Peak (mA)
    - Active (RF working)
      - TX
        - 802.11b, 20 MHz, 1 Mbps, @19.5 dBm 310mA
        - 802.11g, 20 MHz, 54 Mbps, @15 dBm 220mA
        - 802.11n, 20 MHz, MCS7, @13.5 dBm 200mA
        - 802.11n, 40 MHz, MCS7, @13.5 dBm 160mA
       - RX 2
        - 802.11b/g/n, 20 MHz 63
        - 802.11n, 40 MHz 68
- ESP32-S2 Wroom / Wrover NRFND (S3 in production)
- power same as S2

- ESP32-S3 WROOM/Mini $3-4 (mcu/ble/2.4 ghz wifi)

- ESP32-C2 ESP8684-mini $2-3
  - 13 mA with radio off
- ESP32-C3 ESP8685-WROOM $2-3
  - 17-22mA with modem off
  - deep sleep RTC counter 5 uA
- ESP32-C6 Mini $2.50-$3
  - deep sleep 5 uA
- ESP32-H2 Mini/WROOM no stock



- ESP8266 WROOM $3+

