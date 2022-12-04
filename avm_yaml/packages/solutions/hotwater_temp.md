                                                  ArveVM, October.2022
# Hotwater Temperature

<br />

## Intro:
### Why Hotwater Temperature??  
Splitting hotwater-control in several packages,, and this particular looks at the setting for hotwater boiler


### Credits/inspiration/appraisal:
From me:

To me:
- If you find this Solution/info just the slightest bit of usefull, if you copy it or learn something from it, please give me "a pat on the back" in the form of adding to my Github-scoring, by pressin the STAR in the top right corner of my Github-repo (top right on this page)
  - and if the solution is built on other peoples ideas (see above) - they are most likely wort a STAR as well :=) )



### Requirements/install tips/troubleshooting:
<details>
  <summary> Click to unfold list of booring requirements, tips etc </summary>
  
  #### Functionality required (other than what is builtin in my version of HA):
  - HACS: browser mod - for popup-functionality (now updated to browser_mod v2)
  - HACS: custom:button-card
  - HACS: custom:auto-entities
  - HACS: custom:fold-entity-row
  - HACS: custom:multiple-entity-row
  Optional
  - Dashboard:
    * yaml-dashboard (but you can copy dashboard-code to UI-dashboard/card 

  <br />
 
  #### To install you should:
  - first set up packages/solutions as specified elsewhere in my brilliant documentation. 
  - then copy the 'solutions.yaml'-file specified below into a folder where it will be loaded as part of packages at next restart
  - copy and insert code for card whereever suitable for your installation
  - redo/change to your naming standards  :)

  <br />
  
  #### template-editor test-code:
  nah,,
 
  <br />
  <br />
  
  #### Other info:
  Mix- screw temp:
  
  <img width="482" alt="image" src="https://user-images.githubusercontent.com/96014323/205517869-71947bc4-9ae0-4f60-859d-e8aca934ac24.png">

  <br />
  <br />
  
  Pipe-out temp:
  
  <img width="851" alt="image" src="https://user-images.githubusercontent.com/96014323/205517898-eb2a5ed1-af07-470b-94c5-203b66527f60.png">

  <br />
  <br />
  
  Bottom temp:
  
  <img width="288" alt="image" src="https://user-images.githubusercontent.com/96014323/205518063-edaefe4b-dc82-4f98-871b-f48d11100cfc.png">

  
  
</details>

<br />
<br />

## How it works (for me):
Created dashboard-chip:
-

<br />
<br />

### Solution-Yaml:


<br />
<br />

### Solution-Dashboard(s):
[Hotwater SoC chip](https://github.com/ArveVM/HomeAssistantConfig4/blob/master/avm_yaml/dashboard/cards/hotwater_soc_chip.yaml)

<img width="88" alt="image" src="https://user-images.githubusercontent.com/96014323/193773226-887a50c5-87e2-4641-93d8-b29f8be2b8e9.png">

click on the chip - and you will get pop-up-card with more details:

[Hotwater SoC card](https://github.com/ArveVM/HomeAssistantConfig4/blob/master/avm_yaml/dashboard/cards/hotwater_soc_card.yaml)

<br />

<img width="237" alt="image" src="https://user-images.githubusercontent.com/96014323/194163431-6e819073-f961-4de4-abe7-53352f2ce04c.png">

<br />

with all lines expanded:

<img width="235" alt="image" src="https://user-images.githubusercontent.com/96014323/195613384-1c3a8885-a3bc-406f-8072-02e1f058e487.png">


<br />
<br />


## improvements planned/project queue:
- better dashboard
- add acceptable quality on history graph to popup,,,
- must also create legionella warning
