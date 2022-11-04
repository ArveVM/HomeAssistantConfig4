                                                  ArveVM, November.2022
# my ToDo


## Why ToDo in HA? 
- Just to gather all the "chores" or active tasks one should do, I created the ToDo
- idea from app with chores, and from Remi's dashboard

Focus so far have been on: 
- Getting one place to see if there are tasks that should have been done
- possibility to check off tasks
- only show task-list when there are tasks


## How it works (for me):
- Set up template sensor counting all Input Boolean's with name that ends on _todo
- Card that filters on Input Boolean's with name that ends on _todo, showing only them
  - using entity filter - to show only those sensors that are ON
  - using conditional, so if count of tasks ON = 0,, then don't show icon at all



## Solution-Yaml:
[todo.yaml](todo.yaml)
- create template sensor with counter 



## Dashboard(s):
PS; the card has no UI,, so you have to configure in YAML (but good guides on the github)

<img width="237" alt="image" src="https://user-images.githubusercontent.com/96014323/199611333-dd8b233b-e725-45be-a5af-b119aa97d8f6.png">


---


---

## Functionality:







# improvements planned/project que:
- might want to add link to 
- battery-status on mi-sensors??


# Credits/inspiration:
- Remi, theawsomegarage


