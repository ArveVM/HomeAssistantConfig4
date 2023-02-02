# Home Assistant config


- This repo contains (part of) the working Home Assistant configuration for our home. It's clearly under development :)
- Below you find an overview of the the configuration, and below that devices currently being used, links to blog/video posts, and other HA enthusists that provided inspiration and configs to help build this config. 
- All of the code is free to use; I only ask that you Star this repo.
<br />

**I'm now moving documentation to the github-wiki, but are trying to get a top-down stucture which is about like this;**


## Table of contents:
|Chapters   |Description/purpose |
| ----------| ----------------------------- |
|[Wiki-home](https://github.com/ArveVM/HomeAssistantConfig4/wiki/Home)| Startpage for documentation|
|[Mentors and Inspirators](https://github.com/ArveVM/HomeAssistantConfig4/wiki/Mentors-and-Inspirators)|Listing a lot of gratitudes and thanks !! |
|||
|[1. Config-"backend"](https://github.com/ArveVM/HomeAssistantConfig4/wiki/1-Configuration)| About the buildup of my configuration, <br /> Packages -> Functionality -> Solutions -> Compartmentalized-solutions -> share |
|[2. Presentation](https://github.com/ArveVM/HomeAssistantConfig4/wiki/2-Presentation) | YAML-dashboard, Mushroom and Popup's |
|[3. Solutions](https://github.com/ArveVM/HomeAssistantConfig4/wiki/3-Solutions)   |About my method(s) for grouping "everything HA" in Solutions|
|[4. Functionality](https://github.com/ArveVM/HomeAssistantConfig4/wiki/4-Functionality)|About added functionality required to produce Solutions|
|||
|[5. General info](https://github.com/ArveVM/HomeAssistantConfig4/wiki/5-General-info)|Yeah, some blabla|
|||
|[9. Disclaimer](https://github.com/ArveVM/HomeAssistantConfig4/wiki/9-Disclaimer)|Because everyone has one ;)|
<br />
<br />
<br />

## 3. Solutions:

### 3.1. Area-specific solutions:

- [Kid S - linen](https://github.com/ArveVM/HomeAssistantConfig4/tree/master/avm_yaml/packages/solutions/kids_linen.md): Settings of last changed linen, length until next, length until warning, create and complete todo 
<br />

### 3.2. General solutions:
- [Cameras](https://github.com/ArveVM/HomeAssistantConfig4/blob/master/avm_yaml/packages/solutions/cameras.md) - Frigate, connection to cameras and card-setup

- Whole house:
  - All lights
  - All heaters 
  - Temp compare
  - Temp all house
- Heating
  - how to control heating
    - With local thermostat (with input to HA)
    - Without local thermostat
    - "smart-heaters"
<details><summary>ToDo; Create dynamic todo-list on other solutions status-entities</summary>
  - [ToDo](https://github.com/ArveVM/HomeAssistantConfig4/blob/master/avm_yaml/packages/solutions/todo.md)  create todo-list (and let other solutions poulate with tasks and status)
<br />
</details>

<details><summary>Hotwater; SoC, Price-adjusted heating, Salmonella-warning   -     (expand for details)</summary>
  - [Hotwater SoC](https://github.com/ArveVM/HomeAssistantConfig4/blob/master/avm_yaml/packages/solutions/hotwater_soc.md) Calculate hotwater-tank SoC, including charge-time and show stats  
  - [Hotwater Temp](https://github.com/ArveVM/HomeAssistantConfig4/blob/master/avm_yaml/packages/solutions/hotwater_temp.md) Adjust hotwater-tank HA-thermostat according to price  
  -  salmonella - pending,,,
  <br />
  </details>      
  
  <details>
    <summary>Power Control; Total/grouped use, Limit hourly usage, Limit mainfuse capacity   -     (expand for details)</summary>
  - PowerControl (PwrCtrl)
    - PwrCtrl Use:  Sum total, Grouped consumption, utility-meters  
    <details>
      <summary>Click me for details</summary>
      Functionality required
      1. HACS PowerCalc integration - for easy grouping energy- and utility-meter-sensors
      4. Dashboard
      yaml-dashboard (but you can copy dashboard-code to UI-dashboard/card    
      How it works
      Create total usage based upon reading from power-meter (EvaHan - Zigbee - Mqtt)
      grouping what is under control (power-metering), calculating some fixed, and using PowerCalc on the rest that is possible to estimate based upon states.
      Will try to calculate ungrouped
      <br /> 
      </details>
  
    - PwrCtrl Limit:  (powerHourSave) - Define capacity-limit, calculate trend and adjust consumption to not overrun the capacity-limit
                    (Might be a Norwegian speciality to limit usage within a clock-hour, with tarrif on max hourly usage throughout the month.  
    <details>
      <summary>Click me for details</summary>
    Functionality required:
    1. Utility meter for hourly consumption
    2. Lots of power-entities to be able to turn of to reduce consumption
    4. Dashboard:
      * yaml-dashboard (but you can copy dashboard-code to UI-dashboard/card    
      
    ### how it works:
    Create input-number as capacity-limit, and security treshold - to give an actionable limit
    
    Calculate full hour trend, and current percentage towards trend (deducted security-treshold)
    
    Create groups of power-entities to turn off (powerhoursave) to get under the target for hourly usage
    
    create action to turn off first group when hourly trend get above security treshold
    
    create action to turn off next group when hourly trend is above security treshold for 10minutes (or go below treshold and then above again)  - and repeat
    
    create action to turn off last group when power get below 80% of security treshold (to use power wanted)
    <br /> 
    </details>    
  </details>        
- Eva HAN Instant power usage, estimate full hour 
      
- [Plants](https://github.com/ArveVM/HomeAssistantConfig4/blob/master/avm_yaml/packages/solutions/plant.md) Get standard settings for each plant, and report thresholds - and present usefull info in cards 
- Weather forecast
<br />
<br />

### 3.9. Backend:
- [HA-stats](https://github.com/ArveVM/HomeAssistantConfig4/blob/master/avm_yaml/packages/solutions/hastats.md) my HA-instance's stats of sensor-count and yaml-line-count development  
- [AdGuard](https://github.com/ArveVM/HomeAssistantConfig4/blob/master/avm_yaml/packages/solutions/adguard.md) | Enable HA-control of AdGuard |
- Network - capacity
- Server - load/capacity

<br /> 
<br /> 
<br />

## 4. Functionality: 
As from my config-principles; addons and integrations are the enablers of functionality.
Only those with some level of config or interest for myself/others are documented.

### Integrations: 

- [HA-documentation; secrets.yaml](https://www.home-assistant.io/docs/configuration/secrets/#using-secretsyaml) - setup to store passwords/area/private-info in file not shared - and use references to it in rest of config
- [default_config.yaml](https://github.com/ArveVM/HomeAssistantConfig4/blob/master/avm_yaml/packages/integrations/default_config.yaml) -  Adding/tweeeking default HA-functionality,, ,se yaml-file for config/comments - [HA-documentation](https://www.home-assistant.io/integrations/default_config/)
- [template](https://www.home-assistant.io/integrations/template/) - Create sensors based upon all sorts of other sensor-data/entities 
  - [Advanced Templating](https://www.home-assistant.io/integrations/template/) - is also used directly in triggers/states in automations/script/dashboards etc 
- [lovelace.yaml](https://github.com/ArveVM/HomeAssistantConfig4/blob/master/avm_yaml/packages/integrations/lovelace.yaml) - enable both GUI and YAML-dashboard [HA-documentation](https://www.home-assistant.io/dashboards/)
  - Documentation on how to combine GUI and YAML-dashboards: https://www.home-assistant.io/dashboards/dashboards/
- [AdGuard](https://www.home-assistant.io/integrations/adguard/) Integration to AdGuard docker in unRaid - see Adguard-solution for my usage
<br />

### HACS-integrations: 

- [PriceAnalyzer](https://github.com/erlendsellie/priceanalyzer) - Nordpool-spot prices with a bunch of analytical input - including blueprints etc for easy adoptation - [MyDocumentation](https://github.com/ArveVM/HomeAssistantConfig4/blob/master/avm_yaml/packages/integrations/priceanalyzer.md)
- [EnergyScore](https://github.com/knudsvik/EnergyScore) - Some wodo-calculation of how well we manage to utilize cheapest hours - [PwrCtrl_EnergyScore.yaml](https://github.com/ArveVM/HomeAssistantConfig4/blob/master/avm_yaml/packages/solutions/pwrctrl/pwrctrl_energyscore.yaml)
- [Lovelace_gen](https://github.com/thomasloven/hass-lovelace_gen) - enable passing of variables to cards (among othther brilliant functionality)
- [Browser_mod2](https://github.com/thomasloven/hass-browser_mod) used "everywhere" for pop-up functionality 
- [PowerCalc](https://github.com/bramstroker/homeassistant-powercalc) - Add power-sensors and power-aggregation - my implementation; [powercalc.yaml](https://github.com/ArveVM/HomeAssistantConfig4/blob/master/avm_yaml/packages/integrations/powercalc.yaml) 
- [Frigate](https://github.com/blakeblackshear/frigate-hass-integration)
- [Easee EV Charger](https://github.com/fondberg/easee_hass)
- [Volkswagenn We Connect ID](https://github.com/mitch-dc/volkswagen_we_connect_id)
- [Monitor Docker](https://github.com/ualex73/monitor_docker)
- [start_time](https://github.com/AlexxIT/StartTime) - used in HAstats-integrations (to count number of integrations loaded, and present their startup-times
- [OpenPlantbook](https://github.com/Olen/home-assistant-openplantbook)
- [Home Assistant Plant](https://github.com/Olen/homeassistant-plant)
- [Team Tracker](https://github.com/vasqued2/ha-teamtracker)
- [Norwegian Tide](https://github.com/tmjo/ha-norwegiantide)
Huge thanks to the creators of those integrations!! 
<br />
 
### HACS-frontend: 
- [ApexCharts-card](https://github.com/RomRider/apexcharts-card)
- [Auto-entities](https://github.com/thomasloven/lovelace-auto-entities)
- [stack-in-card](https://github.com/custom-cards/stack-in-card) - add multiple card into one card (see exampes on room/area-cards)
- [tabbed card](https://github.com/kinghat/tabbed-card) - see example on any area heating card)
- 
- mini-graph-card
- 
<br />


### HA-Add-ons:

- GoogleDrive backup
<br />

### unRaid Docker "Add-ons":

- AdGuard
- Zigbee2mqtt
- Mosquitto (mqtt-broker)
- Ngnix-reverse-proxy
- Frigate (NVR)
- VS-code (for unRaid Dockers) 
  - with the [Home Assistant Configuration Helper extension](https://marketplace.visualstudio.com/items?itemName=keesschollaart.vscode-home-assistant)
  - and "sync/sharing" to my public GitHub-repo enabled  (this actal repo) :) 
<br />

OLD LISTING OF INTEGRATIONS/ADDONS (need a bit of a cleanup):

| Type      | Name                                       | Description/purpose |
| ----------| ------------------------------------------ | ------------------- |
|Integration| [Bluetooth](https://github.com/ArveVM/HomeAssistantConfig4/blob/master/avm_yaml/packages/integrations/bluetooth.md)| Enabler for BT-functionality |
|Integration| [BTHome](https://github.com/ArveVM/HomeAssistantConfig4/blob/master/avm_yaml/packages/integrations/bt_home.md) | BTHome-firmware flashed sensors |
|Integration| [Inkbird](https://github.com/ArveVM/HomeAssistantConfig4/blob/master/avm_yaml/packages/integrations/inkbird.md) | BT-sensors from Inkbird |
|Integration| [Logitech Harmony Hub](https://github.com/ArveVM/HomeAssistantConfig4/blob/master/avm_yaml/packages/integrations/logitech_harmony_hub.md) | Hub for remote-control |
| Integration | [NUT](https://github.com/ArveVM/HomeAssistantConfig4/blob/master/avm_yaml/packages/integrations/nut.md)  | UPS-integration
|Integration| [Shelly](https://github.com/ArveVM/HomeAssistantConfig4/blob/master/avm_yaml/packages/integrations/shelly.md) | Direct integration to puck's and plugs. Power monitoring, garage-doors etc |
|Integration| [Uptime](https://www.home-assistant.io/integrations/uptime/) | Show when Home Assistant was last started
|HACS-int   | [Plant](https://github.com/Olen/homeassistant-plant/) | Create devices of plants, get data from openplantbook, create thresholds, present in card
|HACS-int   | [ OpenPlantbook](https://github.com/Olen/home-assistant-openplantbook) | Let Plant get data from openplantbook, input to thresholds
|HACS-card  | [ Flower Card](https://github.com/Olen/lovelace-flower-card/) | Present plant in card, showing name, picture, thresholds

<br />
<br />
<br />


