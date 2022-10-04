                                                  ArveVM, October.2022
# Hotwater State of Charge (SoC)


## Why Hotwater SoC??  
Splitting hotwater-control in several packages,, and this particular looks at the State of Charge
- State of Charge in %
- Time to charge full


Shamelessly copied code from Asbjørn Bergsland, re-named to my naming convention, and created my 'Solution'
- changed to my tank sice and heating-element sixe

Created dashboard-chip:
- to see SoC% and currentTemp
- with popup-functionality:
  - Target-temp/current
  - chargetime
  - energy max/charged/toBeCharged
  - (will add history grap??)


## Solution-Yaml:
[hotwater_soc.yaml](hotwater_soc.yaml)
- input-value for target temp
- input-definition of tank-sice
- input-definition of heater-element sice
- a bunch of sensors created to track: 
  - max capacity of kWh chargable to the tank
  - current state kWh
  - kWh that can be charged
  - SoC in %






## Dashboard(s):
[Chip Hotwater SoC](https://github.com/ArveVM/HomeAssistantConfig4/blob/master/avm_yaml/dashboard/cards/chip_hotwater_soc.yaml)

<img width="88" alt="image" src="https://user-images.githubusercontent.com/96014323/193773226-887a50c5-87e2-4641-93d8-b29f8be2b8e9.png">
_click - and you will get pop-up with more details_

---
<img width="235" alt="image" src="https://user-images.githubusercontent.com/96014323/193773471-53f1f846-4f87-4724-b5fe-627840d78eca.png">
_unfortunately no statistic available on sensor,,, is on toDo-list  :(_

# toDo/improvements planned:
- Check with Asbjørn,, is my re-naming of formulas #¤%&-ing something up??   soc 40% when 55degrees out of 76 ??
- new average temp, must check differance between temp-sensor on mixer and the one in the bottom of the tank
- add history graph to popup


# Credits/inspiration:
- Asbjørn Bergsland, Facebook-group; Home Assistant Norge
 

# prereq:
- browser mod - for popup-functionality
- custom:multiple-entity-row - for multiple entities in one row in a card

# template-editor test-code:
nah,,

