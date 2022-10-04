                                                  ArveVM, October.2022
# Hotwater State of Charge (SoC)


## Why Hotwater SoC??  
- Splitting hotwater-control in several packages,, and this particular looks at the State of Charge

State of Charge in %
Time to charge full

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
[hastats.yaml](hastats.yaml)
- input-value for target temp
- input-definition of tank-sice
- input-definition of heater-element sice
- a bunch of sensors created to track: 
  - max capacity of kWh chargable to the tank
  - current state kWh
  - kWh that can be charged
  - SoC in %






## Dashboard(s):
[Entities by domain](https://github.com/ArveVM/HomeAssistantConfig4/blob/master/avm_yaml/dashboard/cards/hastats_entities_by_domain.yaml)

<img width="239" alt="image" src="https://user-images.githubusercontent.com/96014323/193137965-f7cf24ed-00c2-4362-a2ef-79efaee6e442.png">
_click on 'sensors', and you will get pop-up with development-graph and details_
<img width="196" alt="image" src="https://user-images.githubusercontent.com/96014323/193138169-866d38a5-88a1-4882-9c95-cc464f0ef478.png">
_click on other domains and you will get history/details_

---

[YAML lines](https://github.com/ArveVM/HomeAssistantConfig4/blob/master/avm_yaml/dashboard/cards/hastats_yaml_lines_count.yaml)

<img width="242" alt="image" src="https://user-images.githubusercontent.com/96014323/193139300-3259e7fe-1661-4acc-b3d6-ec6c7a55b10c.png">
_unfortunately no statistic available on sensor,,, is on toDo-list  :(_

# toDo/improvements planned:
- Check with Asbjørn,, is my re-naming of formulas #¤%&-ing something up??   soc 40% when 55degrees out of 76 ??
- new average temp, must check differance between temp-sensor on mixer and the one in the bottom of the tank
- add history graph to popup


# Credits/inspiration:
- Asbjørn Bergsland, Facebook-group; Home Assistant Norge
 


# template-editor test-code:
nah,,

