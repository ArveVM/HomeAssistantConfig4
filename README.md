# Home-Assistant_config #4

This repo contains (part of) the working Home Assistant configuration for our home. 
Below you find an overview of the devices currently being used, blog/video posts, and other HA enthusists that provided inspiration and configs to help build this config. All of the code is free to use; I only ask that you Star this repo.


### Current focus: 
- Create 'Solutions' where things are of such a standard that it is valuable to share (or I need to share to get input for my improvements,, )
It is still work in progress, so I will only publish what is actually transformed into this new "principle".

Have focused a lot this summer on home improvements outside the HA-sphere,, but used some time on UI minimalist and browser_mod popup,, to enable more info on/behind small chips/cards.


## Solutions: 
Current concept is moving towards a 'Solution' beeing: 
1. ReadMe-file to present concept and show screenshots, with references 
2. YAML-file with config  
3. One or more yaml-files for dashboard/card/chips

| Area         | Solution      | Description/purpose |
| ------------ | ------------- | ------------------- |
| General todo | [ToDo](https://github.com/ArveVM/HomeAssistantConfig4/blob/master/avm_yaml/packages/solutions/todo.md) | create todo-list (and let other solutions poulate with tasks and status)
| PowerControl | Eva HAN  | Instant power usage, estimate full hour |
| Hotwater     | [Hotwater SoC](https://github.com/ArveVM/HomeAssistantConfig4/blob/master/avm_yaml/packages/solutions/hotwater_soc.md)  | Calculate hotwater-tank SoC, including charge-time and show stats  |
| Server/HA    | [HA-stats](https://github.com/ArveVM/HomeAssistantConfig4/blob/master/avm_yaml/packages/solutions/hastats.md)  | my HA-instance's stats of sensor-count and yaml-line-count development  |

## Functionality: 
As from my config-principles; addons and integrations are the enablers of functionality.
All listed, but only those with some level of config or interest for myself/others are documented.

| Type      | Name                                       | Description/purpose |
| ----------| ------------------------------------------ | ------------------- |
|Integration| [Bluetooth](https://github.com/ArveVM/HomeAssistantConfig4/blob/master/avm_yaml/packages/integrations/bluetooth.md)| Enabler for BT-functionality |
|HACS-int   | Browser mod  | v1.5.3 - used primarily for pop-up functionality |
|Integration| [BTHome](https://github.com/ArveVM/HomeAssistantConfig4/blob/master/avm_yaml/packages/integrations/bt_home.md) | BTHome-firmware flashed sensors |
|Integration| [Default config](https://github.com/ArveVM/HomeAssistantConfig4/blob/master/avm_yaml/packages/integrations/default_config.yaml) | Adding default HA-functionality,, ,se yaml-file for config/comments |
|Integration| [Inkbird](https://github.com/ArveVM/HomeAssistantConfig4/blob/master/avm_yaml/packages/integrations/inkbird.md) | BT-sensors from Inkbird |
|Integration| [Logitech Harmony Hub](https://github.com/ArveVM/HomeAssistantConfig4/blob/master/avm_yaml/packages/integrations/logitech_harmony_hub.md) | Hub for remote-control |
|Dashboard  | [UI-/YAML-dashboards](https://github.com/ArveVM/HomeAssistantConfig4/blob/master/avm_yaml/packages/integrations/lovelace_yaml_dashboards.md) | Enable both UI- and YAML-dashboards |
| Integration | [NUT](https://github.com/ArveVM/HomeAssistantConfig4/blob/master/avm_yaml/packages/integrations/nut.md)  | UPS-integration
|HACS-int   | [PowerCalc](https://github.com/ArveVM/HomeAssistantConfig4/blob/master/avm_yaml/packages/integrations/powercalc.yaml) | Add power-sensors and power-aggregation (mostly used on lights) |
|Integration| [Shelly](https://github.com/ArveVM/HomeAssistantConfig4/blob/master/avm_yaml/packages/integrations/shelly.md) | Direct integration to puck's and plugs. Power monitoring, garage-doors etc |
|Integration| [Uptime](https://www.home-assistant.io/integrations/uptime/) | Show when Home Assistant was last started
|HACS-int   | [Plant](https://github.com/Olen/homeassistant-plant/) | Create devices of plants, get data from openplantbook, create thresholds, present in card
|HACS-int   | [ OpenPlantbook](https://github.com/Olen/home-assistant-openplantbook) | Let Plant get data from openplantbook, input to thresholds
|HACS-card  | [ Flower Card](https://github.com/Olen/lovelace-flower-card/) | Present plant in card, showing name, picture, thresholds


### Guidance for others:
One last thing. Everything in this configuration is a combination of the things I want out of a home automation system flavored with the inspiration from others using Home Assistant. In some cases I took someone else's idea and made it my own, and in some I just completely stole it. So I would be remiss if I didn't acknowledge those that inpired this journey. If you like what you see here, please checkout their configs as well. I owe them thanks for sharing their work.

To prove this point; I even stole this text from thejeffreystone :)

https://github.com/ArveVM/HomeAssistantConfig4/blob/master/avm_yaml/blablabla/ReadMe_configHistory.md
### If not yet bored,, check out more specs/principles:
 - [Config principles:](https://github.com/ArveVM/HomeAssistantConfig4/blob/master/avm_yaml/blablabla/ReadMe_configPrinciples.md)
 - [Config history:](https://github.com/ArveVM/HomeAssistantConfig4/blob/master/avm_yaml/blablabla/ReadMe_configHistory.md)
 - [Current setup](https://github.com/ArveVM/HomeAssistantConfig4/blob/master/avm_yaml/blablabla/ReadMe_currentSetup.md)
 - Fist round of Github-config is archived [HERE](https://github.com/ArveVM/Home-Assistant_config-packages-solutions-1)


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

### Further acknowlegement is added in code,,
### I've tried to add references to persons or sources whenever I've stolen something ;)


### Disclaimer:
- I consider myself on the bottom part of "list of greatest coder in the HA-community", but I might introduce a "how to see the big picture" approach that newbies like me might benefit from, both on understanding functionality and easy access to working solutions from others.
- English is NOT my native language - so if in doubt of what I'm thinking, please ask ;). And in advance; please excuse any verbal abuse or bad language,, I somethimes forget that I don't controll who read what I post online :(
- Please verify whatever you take away from my configuration compared to others,, there are so many good examples out theere (and a few of them are listed below).
- "My config principles" might seem obvious to the experienced HA user,, but from my perspective it gives a good overview of some ground-rules that give me structure and ability to add solution-based "packages" or share with others.

