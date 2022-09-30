                                                  ArveVM, 12.sept.2022
# Inkbird-integration
[Official HA-documentation](https://www.home-assistant.io/integrations/inkbird/)




## How I use this integration:  
- Prereqs:
  - Bluetooth-integration
  - Bluetooth-radio:
    - Use ESPHome with ESP32's as Bluetooth-proxies to get Bluetooth range of (soon) the entire house
  - Add devices with discovery/add 


# my devices:  
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



## toDo / plans ahead:
- some sort of dashboard for barbeque-thermometer
  with sensors for target temperature and warnings/alerts,, have had a look at a few excamples, but not high-pri :(
