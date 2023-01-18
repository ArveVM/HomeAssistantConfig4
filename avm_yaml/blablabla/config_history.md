
### config history:

**v4:**

  Jan ;
  - Remove UI-minimalist, new dashboard using mostly Mushroom and custom "area-card"
  - Adding Frigate-docker and a few cameras (Reolink and D-link)
  - Starting internal code-review,,, aim to publish most of config when cleaned :)
    - need to purify the "solutions-definitions" and do some re-naming.


  Des ;
  - Starting re-use of cards, (combining passing variables in lovelace-yaml and include files (cards))
  - Starting with Mushrom (planning to replace UI minimalist
  - Changing from a clear room-focus to area (rooms/outside/garage/backyard), general (power, hotwater, plants, cameras), backend (server/codelinecount/adguard/restore etc)
  - 12month summary:
    - +6200 lines of yaml in all kinds of packages, +10000 lines of yaml dashboard (mostly UI minimalist)  
    - 3 'levels' of hardware: Pi3b, oldPC with Proxmox, notsooldPc with unRaid
    - +130 integrations
    - far more plans than ability to execute; HA is great FUN!!

  Nov ;
  - Adding ToDo as solution,, presentation of how to collect all other solutions "todo-tasks" in one place.
  - Starting to move out Add-ons to unRaid-dockers; 
    - Adguard, for DNS and adblocking (thanks ThomasH :) )
    - Mosquitto, for mqtt
  - adding Frigate and a couple of cameras, using Coral usb for person detection
  
  Oct ;
  - Adding 'GUI-input' to to 'solutions-concept. Will enable easily adoptation of solutions for new users
  - Hotwater SoC was the conecpt, with settings on tank size, temps etc
  - setup z2m in container outside HA - Sonoff3p as coordinator, start moving devices (renaming and set bindings etc)
  - change remote connection to use Nginx proxy manager (thanks ThomasH :) )
  
  Sept ;
  - Cleanup in 'solutions concept',, starting to re-write code to match concept-trinity of yaml/dashboard/readMe
  - re-posting to new GitHub-repo


**v3:**

  Aug ;
  - Implementing concept of "room status",, certain criterias should be OK in a room - otherwise room should have colorcode for warning

  June 2022;
  - Implementing concept of "room status",, certain criterias should be OK in a room - otherwise room should have colorcode for warning
  - Added concept of "Calculate max energy consumption pr 3 highest hours",, new requirement to keep below certain thresholds to avoid higher power-tarrifs
  - Added concept of "Estimate full hour consumption"

  May 2022; deep deep rabbithole,, UI Minimalist
  - Started creating dashboard for mobile phone
     - focus on area/rooms,, and getting total overview of all rooms on one screen
     - then browse to room,, and use chips with colorcodes/numbers for status  -and popup (click, doubleclick, hold) for different types of info
  
  April 2022; new hardware-setup,, moving from Proxmox to unRaid
  - HAOS as VM.
  
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
  
