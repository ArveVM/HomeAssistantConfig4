                                                  ArveVM, 11.sept.2022
# BTHome-integration
[Official HA-documentation](https://www.home-assistant.io/integrations/bthome/)

<br />

## How I use this integration:  
- Prereqs:
  - Bluetooth-integration installed
  - Bluetooth-radio:
    - Use ESPHome with ESP32's as Bluetooth-proxies to get Bluetooth range of (soon) the entire house
  - Flashing Mijia temp-sensors with BTHome firmware
    - Add devices through integration and get sensors/entities


## my BTHome-devices:  
- Xiaomi Mijia Thermometer 2 Bluetooth   
  - Indor temp/humidity sensor with display
  - Used as room sensors i misc. rooms



### Firmware upgrade/Flash BTHome:
I prefer to flash with BThome to get rid of the requirement of a bindkey. It opens up for others to see the temp, but they're welcome :)

<details>
  <summary>Click to expand details on how to flash BThome</summary>
  Check updated information on www.BTHome.io 
  - make sure you have a PC with BT enabled, as the MiFlasher will use the BT on computer via the browser
  
  - click the link to [TelinkMiFlasher](https://pvvx.github.io/ATC_MiThermometer/TelinkMiFlasher.html)
  
    - select "Connect"-button 0* - and you will see a range of BT-devices, 
  
      <img width="320" alt="image" src="https://user-images.githubusercontent.com/96014323/205151840-1e0810de-6e01-45ee-9537-16443f8eb627.png">

    <br />
  
      1* click the LYWSD03MMC with best signal (closest to your computer?) and click 2* PAIR 
  
  <img width="335" alt="image" src="https://user-images.githubusercontent.com/96014323/205148307-2e8c4875-fa95-47cb-9909-e7b6cba95f2a.png">

    <br />
 
  - after a while you get to this view , click 3* "Do Activation" 
    
  <img width="743" alt="image" src="https://user-images.githubusercontent.com/96014323/205149073-b31d1680-8c66-446a-b091-7618b5c4e76d.png">

    <br />
  
  - then you will be able to select the BThome "custom firmwarare" marked by 4*
  - then the "Start flashing" 5* will appear - click it
  
  <img width="318" alt="image" src="https://user-images.githubusercontent.com/96014323/205151619-f9e6d81d-dedf-4c65-9839-8c5e54c41ece.png">

  <br />

  - it will take some time, and most times the device will disconnect - so you have to repeat 0*  (connect)
  - 
  
  3. remember to set "BTHome" as advertising type
 
  
</details>
  
1. Information on www.BTHome.io 
   - click the link to [TelinkMiFlasher](https://pvvx.github.io/ATC_MiThermometer/TelinkMiFlasher.html)
     - select Connect
   - 
3. remember to set "BTHome" as advertising type

## ADD DEVICE TO HA:
1. Put BT-device within BT-range of dongle/esp32
   - Make sure BT-device is compatible with installed integrations
   - If possible, flash with BTHome to have as much as possible through that integration

2. Power on BT-device

3. Check notifications

4. Add device

5. Rename device/entities


## toDo / plans ahead:
- some sort of presence?
  only get Signal strenth and not distance or from which BT-proxy the signal is reported,, would like some espresence-like data ;)
