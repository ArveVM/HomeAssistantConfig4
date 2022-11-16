                                                  ArveVM, September.2022
# my Home Assistant statistics

<br />

## Intro:
### Why Home Assistant Statistics??  
- I'm actually rather fond of numbers and looking at development through history of a journey from an number perspective
- So I googled a bit, and found something I found useful, and created a 'solution' for hastats.

Focus so far have been on 
- development in entities (by domain),, simple overview with pop-up for stats/details
- and # of YAML-lines in my code

### Credits/inspiration:
- https://community.home-assistant.io/t/lazy-mans-entity-count-something-screwy/174886
- Erlend Sellie's notions of "+10' lines config" - trigger "how big is mine?" - and if I end up with +400 automations - I can look back and see when it happened ;)

### Requirements/install tips:
<details>
  <summary> Click to unfold list of booring requirements, tips etc </summary>
  
  #### Functionality required (other than what is builtin in my version of HA):
  - HACS: browser mod - for popup-functionality (now updated to browser_mod v2)
  - HACS: custom:button-card
  - HACS: custom:auto-entities
    
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
[Entities by domain](https://github.com/ArveVM/HomeAssistantConfig4/blob/master/avm_yaml/dashboard/cards/hastats_entities_by_domain.yaml)

<img width="239" alt="image" src="https://user-images.githubusercontent.com/96014323/193137965-f7cf24ed-00c2-4362-a2ef-79efaee6e442.png">
_click on 'sensors', and you will get pop-up with development-graph and details_
<img width="196" alt="image" src="https://user-images.githubusercontent.com/96014323/193138169-866d38a5-88a1-4882-9c95-cc464f0ef478.png">
_click on other domains and you will get history/details_

<br />

[YAML lines](https://github.com/ArveVM/HomeAssistantConfig4/blob/master/avm_yaml/dashboard/cards/hastats_yaml_lines_count.yaml)

<img width="242" alt="image" src="https://user-images.githubusercontent.com/96014323/193139300-3259e7fe-1661-4acc-b3d6-ec6c7a55b10c.png">
_unfortunately no statistic available on sensor,,, is on toDo-list  :(_

<br />

[Integrations](https://github.com/ArveVM/HomeAssistantConfig4/blob/master/avm_yaml/dashboard/cards/hastats_integrations_count.yaml)

<img width="264" alt="image" src="https://user-images.githubusercontent.com/96014323/197417452-368af287-9082-4ed0-822e-e917f7dff499.png">
_click on 'total', and you will get pop-up with development-graph and details_
<img width="230" alt="image" src="https://user-images.githubusercontent.com/96014323/197417579-260b77ce-74cb-41c2-95b2-aba8b3dd0169.png">



<br />
<br />


## improvements planned/project queue:
- might want to move the system_monitor.yaml sensors here (as there is no config of the integration)
- get some way to add yaml-sensors to statistics-graph (like the template-sensors with class measurement
- change 'float(default=0)'  to 'float(0)'    - no reason to keep the default ?
- change to monthly graphs when I get several months of data
