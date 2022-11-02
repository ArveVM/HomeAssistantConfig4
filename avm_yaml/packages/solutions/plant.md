                                                  ArveVM, November.2022
# my Plants


## Why Plants? 
- I'm not a gardener, but like to have some large plants. Combined with short term memory,, plant sensors and input on how to attend plants seems like a good idea
- So I googled a bit, and found something I found useful, and created a 'solution' for my Plants.

Focus so far have been on 
- Getting control of what are correct tolerances for light, water and fertilizer for each type of plant


## How it works (for me):
- First set up HA with Bluetooth (see my doc on Bluetooth/espHome BT-proxy)
- then buy a MiFlora BT flower-sensor
- connect MiFlora to HA,, it will give 5 sensors    (rename sensor to Plant-xx (change xx to next number of physical plant-sensors, and physically label the actual device))
- add integration Plant Monitor,, add name of plant and choose the sensors from the MiFlora (and possible a humidity-sensor from the room)
  - you might want to check for latin plant names at [Pl@ntNet](https://identify.plantnet.org/the-plant-list/species)


## Solution-Yaml:
- n/a,, this solution is just a combination of hacs-integration(s) and a card

## Dashboard(s):
PS; the card has no UI,, so you have to configure in YAML (but good guides on the github)


---


---

## Functionality:


| Type      | Name                                       | Description/purpose |
| ----------| ------------------------------------------ | ------------------- |
|HACS-int   | [Plant](https://github.com/Olen/homeassistant-plant/) | Create devices of plants, get data from openplantbook, create thresholds, present in card
|HACS-int   | [ OpenPlantbook](https://github.com/Olen/home-assistant-openplantbook) | Let Plant get data from openplantbook, input to thresholds
|HACS-card  | [ Flower Card](https://github.com/Olen/lovelace-flower-card/) | Present plant in card, showing name, picture, thresholds




# toDo/improvements planned:
- might want to add link to 
- battery-status on mi-sensors??


# Credits/inspiration:
- ThomasH - co-proofing concept
- Author(s) of HACS-integrations 


# template-editor test-code:
(because HA-team is constantly adding new functionality/domains,, it is useful to get to check/verify that we actually got all configured with sensors,,,)
```ruby
_____________________________________________________________________
Stats of how many entities pr domain are in my HA-instance, by ArveVM


# check ONE specific domain:
   Automations =  {{ states.automation | count}}

# check ALL domain:
   {%- for domain in states | map(attribute='domain') | unique %}
   {{ domain ~ 's : ' ~ states[domain] | count }}
   {%- endfor %}
   {{ '  Total: ' ~ states | count }}     
```


