                                                  ArveVM, September.2022
# my Home Assistant statistics


## Why Home Assistant Statistics??  
- I'm actually rather fond of numbers and looking at development through history of a journey from an number perspective
- So I googled a bit, and found something I found useful, and created a 'solution' for hastats.

Focus so far have been on 
- development in entities (by domain),, simple overview with pop-up for stats/details
- and # of YAML-lines in my code


## Solution-Yaml:
[hastats.yaml](hastats.yaml)
- a bunch of sensors created to track sum of entities pr domain, and some checksums
- and some to count YAML-lines,, just because we can. Please note that YAML-count includes empty lines and comments,,, but I'll further invest in using .md and not yaml for comments,, so it will get realistic sometime in the future.


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
- might want to move the system_monitor.yaml sensors here (as there is no config of the integration)
- get some way to add yaml-sensors to statistics-graph (like the template-sensors with class measurement


# Credits/inspiration:
- https://community.home-assistant.io/t/lazy-mans-entity-count-something-screwy/174886
- Erlend Sellie's notions of "+10' lines config" - trigger "how big is mine?" 


# template-editor test-code:
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


