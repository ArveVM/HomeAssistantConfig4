# Home-Assistant_config #4

- This repo contains (part of) the working Home Assistant configuration for our home. It's clearly under development :)
- Below you find an overview of the the configuration, and below that devices currently being used, links to blog/video posts, and other HA enthusists that provided inspiration and configs to help build this config. 
 -All of the code is free to use; I only ask that you Star this repo.



# Config overview:

## 1. Config; Packages -> Functionality -> Solutions -> Compartmentalized Solutions -> SHARE:

<details><summary>Packages; Core structure</summary>
<br />

About:
- I have moved ALL YAML-configuration into packages,, so it is easier to separate the two config-princpiles/types:
  - Functionality; the technical adding to HA's toolbox. So the setup/enabling HA to do stuff
    - more info under Functionality below
  - Solutions; virtual wrapper around an end-user focused solution. 
    - Collect Instructions, Dashboard/Cards and Config (inputNubers, sensors created, entities, automations etc) in one "wrapper" so that sharing is easier, and also easier future maintenance
    - more info under Functionality below
 
 - This means that the only thing configuration.yaml is actually doing, is loading all YAML-files in packages-folder. 
   - The packages-folder is where all YAML-configuration is structured in files which are named after the actual HA-integration that is configured, or solutions
 - PS: The way the !include is set up is not random!
   - It is set up so that any configuration put into any of the files in packages-folder is on same format as if it was written directly in configuration.yaml. 
   - So in principle, all code in all files in packages-folder can be cut and pasted into configuration.yaml 
     - Which makes copying from guides and friends that much easier)
     - Also I've created sub-folders for 'functionality' and 'solutions within packages-folder, but that is just to have my own logical structure. They are loaded at startup/refresh whereever they are located inside the packages-folder

Why:
 - Read my config principles :) 
   - [My config principles](https://github.com/ArveVM/HomeAssistantConfig4/blob/master/avm_yaml/blablabla/config_principles.md)
 
 ---
 Required Functionality:
   - [HA-intgration; Packages](https://www.home-assistant.io/docs/configuration/packages/)
   - Some way of editing yaml-files (my choice is vs-code, but FileManager addon and many others will do just fine)
     - [VS-code-addon](https://community.home-assistant.io/t/home-assistant-community-add-on-visual-studio-code/107863)  

 
 My implementation:
   - [packages-folder](https://github.com/ArveVM/HomeAssistantConfig4/tree/master/avm_yaml/packages)
   - [configuration.yaml](https://github.com/ArveVM/HomeAssistantConfig4/blob/master/configuration.yaml)
 ---
<br />
<br />
</details>      

<details><summary>Functionality; Integrations/Add-ons etc.</summary>
<br /> 

I'm defining Functionality as:
- the HA-core ('latest' with 'default config')   (or whatever functionality is included in my [current version](https://github.com/ArveVM/HomeAssistantConfig4/blob/master/.HA_VERSION))
- added Integrations (both GUI and YAML-added)
- HACS-integrations
- HACS-frontend (cards)
- Ad-dons inside HA
- Additional Docker containers (current replacement for Add-ons inside HA, but I guess most of them can run as Add-on)
<br /> 
For each Solution documented, there should be referenced which functionality is required, if the functionality is not defined within "default HA"
<br /> 

 ---
 Required Functionality:
   - my basics: Packages
   - HA-superviced or some docker-host. I'm using :
     - HA-OS which enables add-ons inside HA
     - [unRaid](https://unraid.net/) (virtualization platform) which enables equivalent of add-on-functionality as Docker-containers outside HA

 
 My implementation:
   - [Integrations-folder](https://github.com/ArveVM/HomeAssistantConfig4/tree/master/avm_yaml/packages/integrations)
   - List of noteworthy functionality is here: 
     - https://github.com/ArveVM/HomeAssistantConfig4/edit/master/README.md#functionality
     - PS: The ones which is self-explainde or thoroughly documented by bloggers&youtubers you'll have to figure out yourself :)
 ---
 

<br />
</details>

<details><summary>Solutions: Main</summary> 
<br />
 
 - Create 'Solutions' where things are of such a standard that it is valuable to share (or I need to share to get input for my improvements,, ).
 It is still work in progress, so I will only publish what is actually transformed into this new "principle".
 Current concept is moving towards a 'Solution' beeing: 
      - 1. ReadMe-file to present concept and show screenshots, with references 
      - 2. YAML-file with config  
      - 3. One or more yaml-files for dashboard/card/chips
<br />

Why:
 - Read my config principles :) 
   - [My config principles](https://github.com/ArveVM/HomeAssistantConfig4/blob/master/avm_yaml/blablabla/config_principles.md) 
 <br /> 

 ---
 Required Functionality:
   - my basics: Packages
 
 My implementation:
   - [Solutions-folder](https://github.com/ArveVM/HomeAssistantConfig4/tree/master/avm_yaml/packages/solutions)
   - List of noteworthy solutions are here: 
     - https://github.com/ArveVM/HomeAssistantConfig4/edit/master/README.md#solutions
     - PS: The ones which is self-explainde or thoroughly documented by bloggers&youtubers you'll have to figure out yourself :)
 ---
 
<br /> 
<br /> 
</details>      

<details><summary>Solutions: Compartmentalized Solutions </summary> 
<br />
 
 - Create 'Sub-Solutions' where things are of such scale that it is most usefull to split a solution into several parts
   - Example Power-control:
     - One sub-solution for PwrCtrl_use, which have a solution-yaml configuring current total usage and summary into grouping of power-consumptions, and a card-file with visualization of that one
     - one sub-solution for PwrCtrl_limit, which estimates total hourly usage, has settings for max load pr hour and supporting settings/definitions to autmate the shutoff of power-consumers to stay below limit  (and ofcourse a card to support it)
   - Compartmentalized solutions are currently always created with a separate card, so that any config is easy to link back to actual sub-solution-yaml-config
     - preferred visual presentation is tabbed-card, in which one can have status on one tab, settings on one, and history on one (and add more when needed)   (and ofcouse a solution can add the tabbbed card of a sub-solution in it's tabbed card :) )
<br />
<br />
</details>

</details>      
<details><summary>Configuration: SHARE </summary> 
<br />
 
 - Have deliberately gathered YAML-config in one folder,, so it is easy to share (and not share if private or not completed)
   - Some dockumentation in a blablabla-folder
   - YAML-files for view/dashboards in one folder
   - One folder with files added to configuration as 'pacakges' (integrations+solutions)

 ---
 Required Functionality:
   - my basics: Packages
   - File-editor My choice is VS-code
   - secrets.yaml
   - GitHub-repo to share to   (it's free, but you have to register an account)
 
 My implementation:
   - [AVM_yaml-folder](https://github.com/ArveVM/HomeAssistantConfig4/tree/master/avm_yaml)
   - my own secrets.yaml - and config principle to store personally sensitive information there and refer to it, so that rest of config is sharable
   - create public GitHub repo
   - create .gitignore-file to remove private or sensitive stuff (also remove db and other install-like stuff - it is only config that is interresting for others
   - use VS-code to push your seleced config to GitHub and start spreading the word and get feedback 
     - and whenever you change code,, vs-code will suggest to update your gitHub-repo
 
 ---

<br />
<br /> 
</details>  
<br />

## 2. Presentation; YAML-dashboard/Mushroom/Popup's:
I'm combining GUI and YAML-dashboard with include and re-use of cards with push-entitites to card. Also heavily using YAML-node anchors in both solutions and dashboards/card, so some guidance on that is added here:
<br />
<details><summary>Both GUI and YAML-dashboard; Easy sharing, include one card several places, entity-inject in cards</summary>
<br />
 
By using YAML-dashboard it opens up a few more tools one can use:
 - easier copy/share with others (because the card-yaml-file is actually automagically uploadable to GitHub)
 - Can include one card in several views  ( !include-functionality enabled in YAML-dashboards)
 - Can use node-anchors easily for reuse of card-mod etc  (also applicable for gui-mode??)
 - Can re-use same card with mulitiple entities (see description below)
 
<br />
 
 ---
 Required Functionality:
   - my basics: Packages
   - HA-integration: Lovelace
 
 My implementation:
   - [Dashboard-folder](https://github.com/ArveVM/HomeAssistantConfig4/tree/master/avm_yaml/dashboard)
   - [lovelace.yaml](https://github.com/ArveVM/HomeAssistantConfig4/blob/master/avm_yaml/packages/integrations/lovelace.yaml)
     - adding YAML-config in addition to GUI to my setup

 ---
<br />
 
</details>      
<details><summary>YAML-dashboard-guide: Card include </summary>
<br />
How I use it:
  - Including dashboard-files see to add cards/viwes wherever you want,, se example in "My implementation"
  - No additional functionality required, using standard [!include functionality](https://www.home-assistant.io/docs/configuration/splitting_configuration/)  
<br />
 
 ---
 Required Functionality:
   - YAML-dashboard enabled (see above)
 
 My implementation:
   - use "!include" to map/reuse views; [mob_dashboard.yaml](https://github.com/ArveVM/HomeAssistantConfig4/blob/master/avm_yaml/dashboard/mob_dashboard.yaml) 
   - use "!include" to map/reuse cards; [home_mob_view.yaml](https://github.com/ArveVM/HomeAssistantConfig4/blob/master/avm_yaml/dashboard/views/home_mob_view.yaml) - adding multiple area-cards in one view 

 --- 
<br />
<br />
 
</details>      

<details><summary>YAML-guide: Node-anchors, "entity-inject"</summary>
<br />
 YAML-tutorials:
  
  - Beguinner:	http://thomasloven.com/blog/2018/08/YAML-For-Nonprogrammers/
  - Normal:	    https://spacelift.io/blog/yaml
  - Advanced: 	https://yaml.org/spec/1.2.2/
  
  How I use it
  
  - node_anchors:
    - to avoid duplicate code on card-mod 
    - to declare entities as variables in solution-yaml-files (so it can be referrred to in several automations/climates/sensors
  - Re-use dashboard-files, "entity-inject", see example heater_card.yaml which is used by several room-cards by calling heater_card with different entities
    - [Lovelace_gen; 'passing arguments to included files'](https://github.com/thomasloven/hass-lovelace_gen#passing-arguments-to-included-files)
      #thanksThomasLoven
<br />
 
 ---
 Required Functionality:
   - my basics: Packages
   - HACS; Lovelace_gen
 
 My implementation:
   - use "!include" to map/reuse files; [mob_dashboard.yaml](https://github.com/ArveVM/HomeAssistantConfig4/blob/master/avm_yaml/dashboard/mob_dashboard.yaml) 
   - node_anchor to re-use code

 --- 
<br />
<br />
 
</details>      


<details><summary>Mushroom/popup's: Card-in-card, templating colours, popups, tabbed-card </summary>
  Trying to make one card pr "Solution", so there is one tab for status, one for config and one for histori
  see example on heater_card.yaml
  
  
<br />
 
 
 ---
 Required Functionality:
   - my basics: Packages
   - HACS; Mushroom
   - HACS; Browser_mod (v2)
   - HACS; stack-in-card
   - HACS; tabbed-card
 
 My implementation:
   - use "!include" to map/reuse files; [mob_dashboard.yaml](https://github.com/ArveVM/HomeAssistantConfig4/blob/master/avm_yaml/dashboard/mob_dashboard.yaml) 
   - node_anchor to re-use code
   - area-cards, one card pr area with colored chips for status of most important stuff. 
    - Then drilldown with popups
    - status-card pr area, will gather small solutions and preferred status in those (And alert if not OK)
  - tabbed card, one card pr "Solution"
  - templating, change colours by entity state (see chips in area-cards)
  - Popup, on most chips in room-cards,, 
  - (this requires BrowserMod2,, #thanksThomasLoven)
  

 --- 
 
</details>      
<br />
  

## 3. Solutions:

### 3.1. Area-specific solutions:

- Whole house:
  - All lights
  - All heaters 
- [Kid S - linen](https://github.com/ArveVM/HomeAssistantConfig4/tree/master/avm_yaml/packages/solutions/kids_linen.md): Settings of last changed linen, length until next, length until warning, create and complete todo 
<br />

### 3.2. General solutions:
<br />
  <details>
    <summary>ToDo; Create dynamic todo-list on other solutions status-entities</summary>
  - [ToDo](https://github.com/ArveVM/HomeAssistantConfig4/blob/master/avm_yaml/packages/solutions/todo.md)  create todo-list (and let other solutions poulate with tasks and status)
  <br />
  </details>      
  
  <br />
  <details>
    <summary>Hotwater; SoC, Price-adjusted heating, Salmonella-warning   -     (expand for details)</summary>
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
- [Cameras](https://github.com/ArveVM/HomeAssistantConfig4/blob/master/avm_yaml/packages/solutions/cameras.md) - Frigate, connection to cameras and card-setup
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

## 4. Functionality: 
As from my config-principles; addons and integrations are the enablers of functionality.
Only those with some level of config or interest for myself/others are documented.

### Integrations: 

- [HA-documentation; secrets.yaml](https://www.home-assistant.io/docs/configuration/secrets/#using-secretsyaml) - setup to store passwords/area/private-info in file not shared - and use references to it in rest of config
- [default_config.yaml](https://github.com/ArveVM/HomeAssistantConfig4/blob/master/avm_yaml/packages/integrations/default_config.yaml) -  Adding/tweeeking default HA-functionality,, ,se yaml-file for config/comments - [HA-documentation](https://www.home-assistant.io/integrations/default_config/)
- [lovelace.yaml](https://github.com/ArveVM/HomeAssistantConfig4/blob/master/avm_yaml/packages/integrations/lovelace.yaml) - enable both GUI and YAML-dashboard [HA-documentation](https://www.home-assistant.io/dashboards/)
  - Documentation on how to combine GUI and YAML-dashboards: https://www.home-assistant.io/dashboards/dashboards/
- [AdGuard](https://www.home-assistant.io/integrations/adguard/) Integration to AdGuard docker in unRaid - see Adguard-solution for my usage
<br />

### HACS-integrations: 

- [PriceAnalyzer](https://github.com/erlendsellie/priceanalyzer) - Nordpool-spot prices with a bunch of analytical input - including blueprints etc for easy adoptation - [MyDocumentation](https://github.com/ArveVM/HomeAssistantConfig4/blob/master/avm_yaml/packages/integrations/priceanalyzer.md)
- [Lovelace_gen](https://github.com/thomasloven/hass-lovelace_gen) - enable passing of variables to cards (among othther brilliant functionality)
- [PowerCalc](https://github.com/bramstroker/homeassistant-powercalc) - Add power-sensors and power-aggregation - my implementation; [powercalc.yaml](https://github.com/ArveVM/HomeAssistantConfig4/blob/master/avm_yaml/packages/integrations/powercalc.yaml) 

Huge thanks to the creators of those integrations!! 

<br />
 
### HACS-frontend: 

- [Browser_mod2](https://github.com/thomasloven/hass-browser_mod) used primarily for pop-up functionality 
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

## 5. General info:

### Guidance for others:
One last thing. Everything in this configuration is a combination of the things I want out of a home automation system flavored with the inspiration from others using Home Assistant. In some cases I took someone else's idea and made it my own, and in some I just completely stole it. So I would be remiss if I didn't acknowledge those that inpired this journey. If you like what you see here, please checkout their configs as well. I owe them thanks for sharing their work.

To prove this point; I even stole this text from thejeffreystone :)
<br />

### If not yet bored,, check out more specs/principles:
 - [Config principles:](https://github.com/ArveVM/HomeAssistantConfig4/blob/master/avm_yaml/blablabla/config_principles.md)
 - [Config history:](https://github.com/ArveVM/HomeAssistantConfig4/blob/master/avm_yaml/blablabla/config_history.md)
 - [Current setup](https://github.com/ArveVM/HomeAssistantConfig4/blob/master/avm_yaml/blablabla/current_setup.md)
 - Fist round of Github-config is archived [HERE](https://github.com/ArveVM/Home-Assistant_config-packages-solutions-1)
<br />

### First phase Inspirators-extraordinare;
- the HA-dev-team:  :  https://www.home-assistant.io/docs/configuration/
- Jeff @ SlackerLabs:  https://slacker-labs.com/  /  https://github.com/thejeffreystone/home-assistant-configuration
- Franck Nijhof     :  https://github.com/frenck/home-assistant-config
- Rob @ TheHookup:  :  https://www.youtube.com/c/TheHookUp / https://www.facebook.com/groups/473812443269387
- JuanMtech         :  https://www.youtube.com/channel/UCR7Xa7cU9wfkSY9v3yN2Vtw
- mr RR             :  HA mentor
- mr RL             :  Hardware provider and solutions guiding
- mr ML and mr ØB   :  Home network setup guiding (and huge inspiration -> division shift upwards on how much cash to spend on network equipment :) )
- mr KISS           :  longlived principle of simplicity of code, inspiration from 'back in the days' -> nolug hhelgesen  :)
- Norway HA-Q&A-team:  Robert, Kim, Erlend, ThomassH and Kenneth in particular, but lots of guiding and great ideas from everyone!  Yjuge thanks ;) 
<br />


### Further acknowlegement is added in code wherever appliacable
### I've tried to add references to persons or sources whenever I've stolen something ;)
<br />

### Disclaimer:
- I consider myself on the bottom part of "list of greatest coder in the HA-community", but I might introduce a "how to see the big picture" approach that newbies like me might benefit from, both on understanding functionality and easy access to working solutions from others.
- English is NOT my native language - so if in doubt of what I'm thinking, please ask ;). And in advance; please excuse any verbal abuse or bad language,, I somethimes forget that I don't controll who read what I post online :(
- Please verify whatever you take away from my configuration compared to others,, there are so many good examples out theere (and a few of them are listed below).
- "My config principles" might seem obvious to the experienced HA user,, but from my perspective it gives a good overview of some ground-rules that give me structure and ability to add solution-based "packages" or share with others.
