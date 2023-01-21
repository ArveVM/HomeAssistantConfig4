                                                  ArveVM, September.2022
# my Home Assistant statistics

<br />

## Intro:
### Why Home Assistant Statistics??  
- I'm actually rather fond of numbers and looking at development through history of a journey from an number perspective
- So I googled a bit, and found something I found useful, and created a 'solution' for hastats. And then split it into a few sub-solutions just for structure.

## Table of contents:
|Config   | Description/purpose                 |View   |
| --------| ----------------------------------- |-------- |
|<br /> [HAstats-card](https://github.com/ArveVM/HomeAssistantConfig4/edit/master/avm_yaml/dashboard/solutions/hastats_card.yaml)      |Gather all sub-solutions in one card   <br /> Tabbed card with sub-solutions on each tab|<img width="271" alt="image" src="https://user-images.githubusercontent.com/96014323/213887465-0f3017bd-b416-4d0b-be92-376090cc0039.png">|
|
|[2. Presentation](#2-presentation)     | YAML-dashboard, Mushroom and Popup's |


Requirements (other than standard HA):
custom:mushroom-entity-card
custom:history-explorer-card
Hacs-int; browser_mod

### Requirements/install tips:
<details>
  <summary> Click to unfold list of booring requirements, tips etc </summary>
  
  #### Functionality required (other than what is builtin in my version of HA):
  - HACS: browser mod - for popup-functionality (now updated to browser_mod v2)
  - HACS: custom:button-card
  - HACS: custom:auto-entities
  - HACS: history-explorer-card
  - HACS: tabbed-card
    
  #### Optional:
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
  
  <br />

  #### Other info:
  nah,,
  
  
</details>

<br />
<br />

## How it works (for me)

### Solution-Yaml:
[hastats.yaml](hastats.yaml)
- a bunch of sensors created to track sum of entities pr domain, and some checksums
- and some to count YAML-lines,, just because we can. Please note that YAML-count includes empty lines and comments,,, but I'll further invest in using .md and not yaml for comments,, so it will get realistic sometime in the future.

<br />
<br />

### Solution-Dashboard(s):

[HA stats](https://github.com/ArveVM/HomeAssistantConfig4/blob/master/avm_yaml/dashboard/cards/hastats_card.yaml)

<img width="290" alt="image" src="https://user-images.githubusercontent.com/96014323/212763037-65024e79-de02-4fc2-a211-772464c05a5c.png">

_click on 'tab: EbD', and you will get the next stats-area

<img width="287" alt="image" src="https://user-images.githubusercontent.com/96014323/212763211-892299bb-b552-477e-a017-4f099764615b.png">

_click on 'sensors', and you will get pop-up with development-graph and details_

<img width="225" alt="image" src="https://user-images.githubusercontent.com/96014323/212763444-7ce08199-a52e-45c5-afd2-dd3c30e331af.png">

_click on other domains and you will get history/details_

<br />


_click on 'tab: YAML', and you will get the next stats-area

<img width="284" alt="image" src="https://user-images.githubusercontent.com/96014323/212763792-a8e898a8-2b7e-48e4-a377-168798827c8c.png">

<br />
<img width="290" alt="image" src="https://user-images.githubusercontent.com/96014323/212763881-7dc45256-7139-4f4c-8bcd-8947768b2139.png">

<br />
<br />

### Credits/inspiration:
- https://community.home-assistant.io/t/lazy-mans-entity-count-something-screwy/174886
- Erlend Sellie's notions of "+10' lines config" - trigger "how big is mine?" - and if I end up with +400 automations - I can look back and see when it happened ;)


## improvements planned/project queue:
- might want to move the system_monitor.yaml sensors here (as there is no config of the integration)
- get some way to add yaml-sensors to statistics-graph (like the template-sensors with class measurement
- change 'float(default=0)'  to 'float(0)'    - no reason to keep the default ?
- change to monthly graphs when I get several months of data   (or just keep floating line?? )
