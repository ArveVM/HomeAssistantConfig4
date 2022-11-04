                                                  ArveVM, November.2022
# my ToDo


## Why ToDo in HA? 
- Just to gather all the "chores" or active tasks one should do, I created the ToDo
- idea from app with chores, and from Remi's dashboard
- so now i can automate things to do, or schedules,, and makes sure that they are done  ;)

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
[chip_todo.yaml](https://github.com/ArveVM/HomeAssistantConfig4/blob/master/avm_yaml/dashboard/cards/chip_todo.yaml)

First a little "chip",, it is conditional, so not showing if not

<img width="34" alt="image" src="https://user-images.githubusercontent.com/96014323/200069238-fc690ec6-0906-4e30-97ac-4ed030c75cba.png">

---
on click:

<img width="224" alt="image" src="https://user-images.githubusercontent.com/96014323/200069443-af889bbc-06ce-4e61-b2ad-f76de935487d.png">

and if you click one of the entities,, the task is completed and it disapears,,








# improvements planned/project queue:
- might want to add link to 
- battery-status on mi-sensors??
- enable conditional chip to be anywhere on the swipe card?  must currently be at the end, because if conditions are not met - the rest of the cards are also filtered :(


# Credits/inspiration:
- Remi, [theawsomegarage](https://theawesomegarage.com/)


