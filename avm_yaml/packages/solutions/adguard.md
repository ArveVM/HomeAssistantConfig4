                                                  ArveVM, November.2022
# AdGuard

<br />

## Intro:
### Why AdGuard?  
Need a way for the wife to control AdGuard (read; disable ad-blocking), so integrated it to HA and made a chip/popup from which she can control

### Credits/inspiration:
- lots of assistance and guiding from ThomasH: so hjuge thanks ;)

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
  - Installed AdGuard docker
  - Installed HA Adguard-integration
  - add config to AdGuard-docker  
  - created chip/popup to view status
  - first set up packages/solutions as specified elsewhere in my brilliant documentation. 
  - copy and insert code for card whereever suitable for your installation
  - redo/change to your naming standards  :)

  <br />
  
  #### template-editor test-code:
  nah,,
  you can contact Asbjørn  :)

  <br />

  #### Other info:
  check this calculator; https://bloglocation.com/art/water-heating-calculator-for-time-energy-power
  
  
</details>

<br />
<br />

## How it works (for me):
- created chip/popup to view status from AdGuard-integration getting data from Adguard-docker


<br />
<br />

### Solution-Yaml:
n/a

<br />
<br />

### Solution-Dashboard(s):
[Chip Hotwater SoC](https://github.com/ArveVM/HomeAssistantConfig4/blob/master/avm_yaml/dashboard/cards/chip_hotwater_soc.yaml)

<img width="88" alt="image" src="https://user-images.githubusercontent.com/96014323/193773226-887a50c5-87e2-4641-93d8-b29f8be2b8e9.png">
click - and you will get pop-up with more details:

<br />

<img width="237" alt="image" src="https://user-images.githubusercontent.com/96014323/194163431-6e819073-f961-4de4-abe7-53352f2ce04c.png">

<br />

with all lines expanded:

<img width="235" alt="image" src="https://user-images.githubusercontent.com/96014323/195613384-1c3a8885-a3bc-406f-8072-02e1f058e487.png">


<br />
<br />


## improvements planned/project queue:
- Better documentation of server/docker setup
- might do something with history/graphs  etc?
