                                                  ArveVM, 11.sept.2022
# BTHome-integration
[Official HA-documentation](https://www.home-assistant.io/integrations/bthome/)




## How I use BTHome-integration:  
- Prereqs:
  - Bluetooth-integration (added through 'default_config:' in 2022.8)
  - Bluetooth-radio:
    - Use ESPHome with ESP32's as Bluetooth-proxies to get Bluetooth range of (soon) the entire house
  - Flashing Mijia temp-sensors with BTHome firmware 


# my BTHome-devices:  
- Xiaomi Mijia Thermometer 2 Bluetooth   
  - Indor temp/humidity sensor with display
  - Used as room sensors i misc. rooms
- [Inkbird IBS TH2](https://inkbird.com/products/hygrometer-ibs-th2)
  - Temperature and humidity Hygrometer 
  - Used as sensors for fridge and freezers
- [Inkbird IBT-4XS](https://inkbird.com/products/bluetooth-grill-thermometer-ibt-4xs)
  - 4probe barbeque thermometer


## ADD DEVICE TO HA:
1. Put BT-device within BT-range of dongle/esp32
   - Make sure BT-device is compatible with installed integrations
   - If possible, flash with BTHome to have as much as possible through that integration

2. Power on BT-device

3. Check notifications

4. Add device

5. Rename device/entities



## Firmware upgrade/Flash BTHome:
1. www.BTHome.io 
2. remember to set "BTHome" as advertising type
