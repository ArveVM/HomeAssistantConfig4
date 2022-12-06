                                                  ArveVM, December.2022
# Camears

<br />

## Intro:
### Why Cameras?  
Need a way for record when people come visit (warnings), recording in case of theft and general surveilamce

### Credits/inspiration:
- Kenneth M, partial Frigate config ;)

### Requirements/install tips/troubleshooting:
<details>
  <summary> Click to unfold list of booring requirements, tips etc </summary>
  
  #### Functionality required (other than what is builtin in my version of HA):
  - Frigate (unRaid Docker)
  - HACS: frigate-integration
  - HACS: custom:frigate-card
  - HACS: custom:tabbed-card
  - HACS: custom:auto-entities
  Optional
  - Dashboard:
    * yaml-dashboard (but you can copy dashboard-code to UI-dashboard/card 

  <br />
 
  #### To install you should:
  - Installed Frigate docker
  - add config to Frigate-docker (config-file need to be created, verify in Frigate web-ui that you have connection to camera(s)) 
  - Installed HA frigate-integration (ensure you get in the frigate-cameras)

  - copy and insert code for card whereever suitable for your installation
  - redo/change to your naming standards  :)

  <br />
  
  #### template-editor test-code:
  nah,,

  <br />

  #### Other info:
  maybe someday I will document the docker-setup and -config  ;),, just maybe,,,
  
  
</details>

<br />
<br />

## How it works (for me):
- created chip/popup to view tabbed card with cameras from Frigate


<br />
<br />

### Solution-Yaml:
n/a

<br />
<br />

### Solution-Dashboard(s):
[Camera card](https://github.com/ArveVM/HomeAssistantConfig4/blob/master/avm_yaml/dashboard/cards/camera_card.yaml)

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
