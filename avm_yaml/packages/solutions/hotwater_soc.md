                                                  ArveVM, October.2022
# Hotwater State of Charge (SoC)


## Why Hotwater SoC??  
Splitting hotwater-control in several packages,, and this particular looks at the State of Charge
- State of Charge in %
- Time to charge full


Shamelessly copied code from Asbjørn Bergsland, re-named to my naming convention, and created my 'Solution'
- Created inpust for temps, tank sice and heating-element sixe

Created dashboard-chip:
- to see SoC% and currentTemp
- with popup-functionality:
  - Target-temp/current
  - chargetime to SoC-target
  - energy toBeCharged 
    - EnergyMax, 100% charged tank
    - Charged (energy used to charge tank to current status) 
    - toBeCharged 
  - SoC-settings:
    - SoC-target
    - SoC-min (consider temp when hotwater is not actually defined as hotwater)
    - intake-temp (water temp into hotwater-tank
    - Tank size
    - Tank emement size  
  - History grap  (first version,, enough today,,)


## Solution-Yaml:
[hotwater_soc.yaml](hotwater_soc.yaml)
- input-number for target temp 
- input-number for min temp
- input-number of tank-sice
- input-number of heater-element sice
- a bunch of sensors created to track: 
  - max capacity of kWh chargable to the tank
  - current state kWh
  - kWh that can be charged
  - SoC in %






## Dashboard(s):
[Chip Hotwater SoC](https://github.com/ArveVM/HomeAssistantConfig4/blob/master/avm_yaml/dashboard/cards/chip_hotwater_soc.yaml)

<img width="88" alt="image" src="https://user-images.githubusercontent.com/96014323/193773226-887a50c5-87e2-4641-93d8-b29f8be2b8e9.png">
click - and you will get pop-up with more details:

---
<img width="237" alt="image" src="https://user-images.githubusercontent.com/96014323/194163431-6e819073-f961-4de4-abe7-53352f2ce04c.png">
---
with all lines expanded:
<img width="236" alt="image" src="https://user-images.githubusercontent.com/96014323/194163560-e9ab8e04-e2a7-42c1-83b5-f3cedf8823dc.png">

---


# toDo/improvements planned:
- new average temp, must check differance between temp-sensor on mixer and the one in the bottom of the tank
- add acceptable quality on history graph to popup,,,
- must also create legionella warning


# Credits/inspiration:
- Asbjørn Bergsland, Facebook-group; Home Assistant Norge
 

# prereq:
- browser mod - for popup-functionality
- custom:multiple-entity-row - for multiple entities in one row in a card
- custom:fold-entity-row     - for fold-entity-rows
- UI minimalist - for templates (on chip),, should be easy to remove/adopt to your own themes

# template-editor test-code:
nah,,

