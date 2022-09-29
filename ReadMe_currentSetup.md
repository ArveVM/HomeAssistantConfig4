
# Current setup;
HA-hardware:
- Dell optiplex 9020 SFF, i5-4590, 16GB ram -> unRaid
- ConbeeII zigbee-stick - HA-addon
- Sonoff3p  - unRaid-docker

Devices:
- Various Android Devices (phones, android-tablets)
- Windows laptops
 
Networking:
- Ubiquiti UniFi Dream Machine Pro
- Ubiquiti UniFi USW Flex Mini
- Ubiquiti UniFi 6 Lite
- HP switch

Media:
- Google Chromecast 
- Google Mini 
- Lenovo Smartwatch
 
Switches/Plugs:
- Shelly1
- Shelly1pm
- Shelly+1
- Shelly+1pm
- ShellyS
- ApexPlug (https://www.zigbee2mqtt.io/devices/HLU2909K.html#datek-hlu2909k)
- Ikea E1603 (https://www.zigbee2mqtt.io/devices/E1603_E1702_E1708.html)
 
Lights:
- Ikea styrbar
- Ikea bulbs
- Namron led-strip RGBW
- Some RF-controlled "kubbelys"

Sensors:
- Aquara temp/humidity sensor
- Reed-switch (wired to Shelly1)
- Netatmo
- Mi BT-temp 
- Inkbird TH2/P01B 012
- Inkbird iBBQ4
- Eva meeter-reader (https://www.zigbee2mqtt.io/devices/HSE2905E.html#datek-hse2905e)

Integrations:
- Browser Mod
- BTHome
- ESPHome
- Glances
- Google Assistant
- Google Calendar
- Google Cast
- Supervisor
- Inkbird
- Logitec Harmony Hub
- Meterologisk institutt
- Mobile App
- Mosquitto broker (MQTT)   (note that Mosquitto is both an add-on and an integration :))
- Netatmo
- Shelly
- Sun
- Uptime
- WLED
- HACS:
  - Easee EV Charger
  - Nordpool
  - Priceanalyzer
  - UI Lovelace Minimalist
  - Local Tuya (not working properly ;( )  - DISABLED
  - Volksvagen We Connect ID
  - Min renovasjon


Add-ons:
- Chrony (NTP for Shellys on NoT)
- Dnsmasq
- ESPHome
- File editor
- Home Assistant Google Drive Backup
- Mosquitto broker (MQTT)
- Node-RED  (not used, had a plan, came up with other plans,,,, )
- Samba share
- SQLite web (not used, had a plan, came up with other plans,,,, )
- Studio Code Server (started using, also using to share config)
- Terminal & SSH
- Zigbee2mqtt 

Blueprints:
- Aquara qube: https://raw.githubusercontent.com/golles/Home-Assistant-Blueprints/main/zigbee2mqtt_aqara_magic_cube.yaml
- PriceAnalyzer - Control Climate - https://github.com/erlendsellie/HomeAssistantConfig/blob/master/blueprints/automation/erlendsellie/priceanalyzer.yaml

Frontend:
- HACS:
  - Custom button card: https://github.com/custom-cards/button-card
  - Custom apexcharts-card: https://github.com/RomRider/apexcharts-card
  - Custom charger-card: https://github.com/tmjo/charger-card

