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

