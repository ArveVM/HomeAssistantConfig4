                                                  ArveVM, November.2022
# Kid S - change linen


## Why Kid S change linen??  
Start of collecting repeatig tasks with warnings and alert. Kid S is a bit irregular in thimes of "now we need to change". 
So this Solution is 
- logging when last changed
- setting for how long between changes
- setting for creating todo or not   (prereq is the ToDo-Solution)
- setting for how far ahead of due-date todo-task should be created
- setting for creating alert if overdue
- calculation of time to change
- card which show how long time until next due-date


Todo-principle copied code from Remi theawsomegarage


## Solution-Yaml:
[kids_linen.yaml](kids_linen.yaml)
- input-booleans, -datetimes, -numbers and template sensor
- automation to turn on todo when limit is reached
- automation to reset date when todo is completed



## Dashboard(s):
[Card Kid S linen](https://github.com/ArveVM/HomeAssistantConfig4/blob/master/avm_yaml/dashboard/cards/chip_hotwater_soc.yaml)


---
---

---


# project queue - improvements planned:
- fix alert side of things
- node anchors and general prefix-text (hastely pulished as input to Remi :) )
- 


# Credits/inspiration:
- Remi theawsomegarage, Facebook-group; Home Assistant
 

# prereq:
- browser mod - for popup-functionality
- custom:multiple-entity-row - for multiple entities in one row in a card
- custom:fold-entity-row     - for fold-entity-rows
- UI minimalist - for templates (on chip),, should be easy to remove/adopt to your own themes

# template-editor test-code:
nah,,
