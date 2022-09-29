# Home-Assistant_config #4

This repo contains (part of) the working Home Assistant configuration for our home. 
Below you find an overview of the devices currently being used, blog/video posts, and other HA enthusists that provided inspiration and configs to help build this config. All of the code is free to use.

### Disclaimer:
- I consider myself on the bottom part of "list of greatest coder in the HA-community", but I might introduce a "how to see the big picture" approach that newbies like me might benefit from, both on understanding functionality and easy access to working solutions from others.
- English is NOT my native language - so if in doubt of what I'm thinking, please ask ;). And in advance; please excuse any verbal abuse or bad language,, I somethimes forget that I don't controll who read what I post online :(
- Please verify whatever you take away from my configuration compared to others,, there are so many good examples out theere (and a few of them are listed below).
- "My config principles" might seem obvious to the experienced HA user,, but from my perspective it gives a good overview of some ground-rules that give me structure and ability to add solution-based "packages" or share with others.

### Current focus: 
- Create 'Solutions' where things are of such a standard that it is valuable to share (or I need to share to get input for my improvements,, )
It is still work in progress, so I will only publish what is actually transformed into this new "principle".


# My Config principles; 'Functionality and Solutions'
(under construction, so this is the march-version,,)
1. My world of HA is split into two domains;
   - Solutions are the usage of Functionality to create automagicallity  :)
   - Functionality is the enabler of Solutions 
2. All Home Assistant Functionality comes from either an Integration or an Add-on
   - this includes the HA itself, which I see as 'documented and configurable' as an Integration (maybe a simplification, but it works for this principle)
3. Functionality configuration options:
   - GUI configuration   (preferred by me)
   - .yaml configuration: 
     - yaml-file must be named according to the actual integration/addon to which the functionality is actually loaded
     - as configuration goes,, it can also be like adding sensors or templates to the integration to enable what could/should have been logically incuded
     - all 'manual .yaml-configuration' should (if possible) be separated from installed integrations/addons 
     - by creating /config/avm_yaml/packages/integrations/ I've made a placeholder for this principle
   - Add-ons can also require an manual configuration. If so; add prefix addon to file and add to the other manual functionality config in the /integrations-folder 
4. How do HA enable Functionality?:
   - Addons installed/configured   -> addon-startup (manually or automatically at HA-startup)
   - Integrations installed/configured  -> enabled at HA startup if not disabled. Some can also be re-loaded from integration GUI?
   - configuration.yaml   -> is loaded at startup (using 'packages-functionality' and is in my configuration adding further functionality in Integrations-folder
     - integrations-folder added functionality:
       - default_config.yaml -> is adding loads of 'base functionality'
       - etc etc - see files in folder  
   - and that's it - > through that principle ALL functionality can be controlled; either it's 
     - an Addon
     - installed Integration
     - something .yaml added to the Integrations-folder!
5. All solutions should be kept separate from Functionality
   - One .yaml-file pr solution -> all files in the /config/avm_yaml/packages/solutions/ - folder  (or structure of sub-folders if required)
   - You must decide/create your own structure/namin for your Solutions, based upon your requirements and preferences
     - be prepared to use/change naming-standards according to solution-structure, to be able to find sensors in need for reconfig 
   - Since configuration.yaml is including functionality in solutions-folder,, all files will be loaded at startup
   - all .yaml-files in solutions must have intendation and spaces as if code was written directly in configuration.yaml,, se examples
 6. Combinations (no rule without exeptions)
    - Groups of functionality can be added in Entities-folder (sensors, templates and utilitymeters using !include - principles) 
    - still some cleanup for me there,, but will I get rid of this

## Why the need for "My config principles"?:
I've worked quite a few hours trying to get my head around all different types/styles of config's and have concluded that I have to take a slightly different approach.
My background is from financial/management and not that of code, so it is possible that I'm a bit slow on that department - but I for sure have a need for control and overview. I need to know that the sum of the parts =  the total,, so I need to see how stuff work - and how things cascades

As a newbie to HA it was frustrating to see functionality not defined and not understanding where configuration should go,,, but I loved the actual "everyting works if you tinker a bit"

In my head it will also enable sharing solutions simpler

And overview of small integrations that need a sensor added to their config is now much much easier to explain and to share


### Guidance for others:
One last thing. Everything in this configuration is a combination of the things I want out of a home automation system flavored with the inspiration from others using Home Assistant. In some cases I took someone else's idea and made it my own, and in some I just completely stole it. So I would be remiss if I didn't acknowledge those that inpired this journey. If you like what you see here, please checkout their configs as well. I owe them thanks for sharing their work.

To prove this point; I even stole this text from thejeffreystone :)



### Inspirators-extraordinare;
- the HA-dev-team:  :  https://www.home-assistant.io/docs/configuration/
- Jeff @ SlackerLabs:  https://slacker-labs.com/  /  https://github.com/thejeffreystone/home-assistant-configuration
- Franck Nijhof     :  https://github.com/frenck/home-assistant-config
- Rob @ TheHookup:  :  https://www.youtube.com/c/TheHookUp / https://www.facebook.com/groups/473812443269387
- JuanMtech         :  https://www.youtube.com/channel/UCR7Xa7cU9wfkSY9v3yN2Vtw
- mr RR             :  HA mentor
- mr RL             :  Hardware provider and solutions guiding
- mr ML and mr ØB   :  Home network setup guiding (and huge inspiration -> division shift upwards on how much cash to spend on network equipment :) )
- mr KISS           :  longlived principle of simplicity of code, inspiration from 'back in the days' -> nolug hhelgesen  :)



### Current setup;
HA-hardware:
- HP Compaq dc7900 -> Proxmox7
- ConbeeII zigbee-stick

Devices:
- Various Android Devices (phones, android-tablets)
- Windows laptops
 
Networking:
- Ubiquiti UniFi Dream Machine Pro
- Ubiquiti UniFi USW Flex Mini
- Ubiquiti UniFi 6 Lite
- Deco M5
- HP switch

Media:
- Google Chromecast (pending integration)
- Google Mini (pending integration)
- Lenovo Smartwatch (pending integration)
 
Switches/Plugs:
- Shelly1
- Shelly1pm
- Shelly+1
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
- Eva meeter-reader (https://www.zigbee2mqtt.io/devices/HSE2905E.html#datek-hse2905e)

Integrations:
- Supervisor
- Logitec Harmony Hub
- Meterologisk institutt
- Mobile App
- Mosquitto broker (MQTT)   (note that Mosquitto is both an add-on and an integration :))
- Netatmo
- Shelly
- HACS:
  - Nordpool
  - Easee EV Charger
  - Local Tuya (not working properly ;( )
  - Min renovasjon


Add-ons:
- Chrony (NTP for Shellys on NoT)
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

Frontend:
- HACS:
  - Custom button card: https://github.com/custom-cards/button-card
  - Custom apexcharts-card: https://github.com/RomRider/apexcharts-card
  - Custom charger-card: https://github.com/tmjo/charger-card


### config history:

**v3:**

  March 2022; reconfigure all config to new principle - while building the actual principle (sound plan :))
  Start splitting/categorizing all config into Functionality vs Solutions.
  - Start on configuration principles
  - Move the previous included packages-folder further into new re-named folder-structure, to enable cleaner principles
  - Adding documentation to GitHub - knowledge-sharing and try to get some feeback/improvements


**v2:**

  January 2022; Upgrade of EVERYTHING, both server/network and HA-configuration
  - new HA setup on HP Compaq dc7900 -> Proxmox7 ->  
    - setup using guide from Juan: https://www.youtube.com/watch?v=42gopfIrPBY
    - but got into trouble with enabling boot, both bios on Host, and VM-bios and VM boot-order,, if in trouble - google those ;)
  - new network:
    - firewall investment: DreamMachinePro, miniswitch and a couple of AP's
    - setup using guide from Rob: https://www.youtube.com/watch?v=ufJ3dPAgFiM   (and following tutorials)
    - adding LAN, IoT and NoT network (leaving the Deco M5 as guest-network until further reconfig)and some ad-hoc cabling/switches because unfortunately 8-port unify-switches are globally out of stock :(
    - adding SSID's for each network
    - migration of Shelly's to NoT - and got into issues with power-metering - had to add chrony-addon to enable an internal NTP-server 
  - new config-structure; 
    - initially inspired by Ronny; started splitting up configuration:
      - https://www.home-assistant.io/docs/configuration/splitting_configuration/
      - created folder Entities and sub-folders for each type functionality (sensor, template, utilitymeters) with a loooot of help and guiding from Ronny !! 
      - inspired by Franck Nijhof - started removing all functionality into their respective integration,,, that gave med understanding of functionality,, but I lost overview of the 'solution' i was trying to make work
      - got thoroughly frustrated by the "a bit here and a bit there - where do I see the fulll picture?")


**v1:**

  December 2021; Launch of my HA-enedevour
  - Pi3, image from HA
  - wifi on Deco M5
  - created simple garage-door automation with Shelly1's  mostly like Rob's at https://www.youtube.com/watch?v=WEZUxXNiERQ&t=41s - but reversed the reed-switch to confirm when door is closed 
  - Some lights added, conbeeII and z2M/mosquitto and wifi (nedis)
  - Aquara-sensors (temp, button, cube)
  - happy go puppuy,, install EVERYTHING, HA IS AWSOME    (insert soundtrack; https://www.youtube.com/watch?v=StTqXEQ2l-Y !!!!!)
  - trying to connect Nedis-bulbs, but failed, then localTuya - but failed horribly :(
  - got an 'awakening' looking at the current number on IoT-devices on my LAN, and the likely addition of further wifi-bulbs and all other possibilities that will be added created a side-project;
  -    -> network capacity/security/have to increase significantly to keep up with my further HA-plans
  - then installed studio code addon and the Pi3 DIED!    (who told me that Pi3 is more than sufficiant for HA,, don't you know my apetite for all the worlds integrations and addons ?  :)
  -   end of v1 - RIP
  
