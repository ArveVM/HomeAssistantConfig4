                                                  ArveVM, December.2022
# Camearas
### Why Cameras?  
- Need a way for record when people come visit (warnings), recording in case of theft and general surveilamce
- Record no audio
- Record only when movement
<br />

### Table of contents:
|Chapter   | Description/purpose                |
| --------| ----------------------------------- |
|[HAstats-main](#hastats-main)      |Gather all sub-solutions in one card   <br /> Tabbed card with sub-solutions on each tab <br /> One tab with reference to this GitHub-repo for documentation-purposes|
|[HAstats-Integrations](#hastats-integrations)      |Counter of integrations loaded  <br /> Graphed long term history <br /> PopUp with list of all current integrations, with load-times at startup/reload|

## How it works (for me):
- created chip/popup to view tabbed card with cameras from Frigate, birseye, cameras, frigate entities etc


<br />
<br />

### Solution-Yaml:
n/a

<br />
<br />

### Solution-Dashboard(s):
[Camera card](https://github.com/ArveVM/HomeAssistantConfig4/blob/master/avm_yaml/dashboard/cards/camera_card.yaml)

First tab (no action/triggers,, but they will show up):

![image](https://user-images.githubusercontent.com/96014323/205927784-703bac11-cab7-4fca-b54c-d06f74fd28b2.png)


<br />

Second tab:

![image](https://user-images.githubusercontent.com/96014323/205928128-76472a75-c081-41ec-bfa8-bf2198b1fd57.png)

<br />

Third tab:

![image](https://user-images.githubusercontent.com/96014323/205928299-1e5a1a95-8f80-4479-b779-5c9603584df4.png)

<br />

Last tab (collection of old camera(s) as picture glance:

![image](https://user-images.githubusercontent.com/96014323/205928498-4146efd8-2054-423f-8092-bcf8a8a08c3f.png)


<br />



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
  - Install Frigate docker
  - add config to Frigate-docker (config-file need to be created, verify in Frigate web-ui that you have connection to camera(s)) 
  - Installed HA frigate-integration (ensure you get in the frigate-cameras)

  - copy and insert code for card whereever suitable for your installation
  - redo/change to your naming standards/cameras/entities  :)

  <br />
  
  #### template-editor test-code:
  nah,,

  <br />

  #### Other info:
  maybe someday I will document the docker-setup and -config  ;),, just maybe,,,

  for birdseye-view:
  https://github.com/blakeblackshear/frigate/issues/2606
  look at comment from mattkasa commented on Jan 19  for an card-update within lovelace card-config!!
  
  
</details>

<br />
<br />



## improvements planned/project queue:
- Better documentation of server/docker setup
- might do something with history/graphs  etc?  counter on how often ?
- warning/popup when person detected (and a pause-function?)
