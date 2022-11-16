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
  - https://www.home-assistant.io/integrations/adguard/
  - HACS: browser mod - for popup-functionality (now updated to browser_mod v2)
  - HACS: custom:button-card
  - HACS: custom:auto-entities
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

  <br />

  #### Other info:
  maybe someday I will document the docker-setup and adguard-config  ;),, just maybe,,,
  
  
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
[Chip AdGuard](https://github.com/ArveVM/HomeAssistantConfig4/blob/master/avm_yaml/dashboard/cards/chip_adguard.yaml)

<img width="52" alt="image" src="https://user-images.githubusercontent.com/96014323/202316060-4355f8e4-2415-4e9a-bd31-b2625bf7e1d2.png">
click - and you will get pop-up with more details:

<br />

with all lines expanded:

<img width="320" alt="image" src="https://user-images.githubusercontent.com/96014323/202316452-2ee10fb4-5bd9-46b1-aeb9-6b6dba271877.png">

<br />
<br />


## improvements planned/project queue:
- Better documentation of server/docker setup
- might do something with history/graphs  etc?
