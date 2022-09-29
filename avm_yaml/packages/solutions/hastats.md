                                                  ArveVM, September.2022
# my Home Assistant statistics


## Why Home Assistant Statistics??  
- I'm actually rather fond of numbers and looking at development through history of a journey from an number perspective
- So I googled a bit, and found something I found useful, and created a 'solution' for hastats.

Focus so far have been on 
- development in entities (by domain
- and # of YAML-lines in my code

I've created the sensors in an solutions-yaml,, and will look into moving dashboards to separate -yaml-files for easy sharing (whenever something get updated,,,


.
.

# template-editor test-code:
(because HA-team is constantly adding new functionality/domains,, it is useful to get to check/verify that we actually got all configured with sensors,,,)
```ruby
__________________________________________________________________
Stats of how many entities pr domain are in my HA-instance, by ArveVM:

# check ONE specific domain:
   Automations =  {{ states.automation | count}}

# check ALL domain:
   {%- for domain in states | map(attribute='domain') | unique %}
   {{ domain ~ 's : ' ~ states[domain] | count }}
   {%- endfor %}
   {{ '  Total: ' ~ states | count }}     
```
