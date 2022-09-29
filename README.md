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

Have focused a lot this summer on home improvements outside the HA-sphere,, but used some time on UI minimalist and browser_mod popup,, to enable more info on/behind small chips/cards


### Guidance for others:
One last thing. Everything in this configuration is a combination of the things I want out of a home automation system flavored with the inspiration from others using Home Assistant. In some cases I took someone else's idea and made it my own, and in some I just completely stole it. So I would be remiss if I didn't acknowledge those that inpired this journey. If you like what you see here, please checkout their configs as well. I owe them thanks for sharing their work.

To prove this point; I even stole this text from thejeffreystone :)



### If not yet bored,, check out more specs/principles:
 - [Config principles:](https://github.com/ArveVM/HomeAssistantConfig4/blob/master/ReadMe_configPrinciples.md)

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

Further acknowlegement is added in code,, ,I've tried to add references to persons or sources whenever I've stolen something ;)


### config history:

**v3:**

  April 2022; new hardware-setup,, moving from Proxmox to unRaid
  - HAOS as VM.
  - Focus a bit on rooms


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
  
