###############################################################################
#   @author       :   ArveVM 
#   @date         :   09.march.2022
#   @solution     :   Logitech Harmonny Hub
#   @description  :   how to use IR-function on LHH from HA.  
#   @basic concept: 
#      Logitec Harmony Hub - integration, install, add IP of Harmony Hub
#      teach Harmony Hub all functions you want to mimic
#         NB; can add "non standard" devices and add/teach functions from 
#             remotes
###############################################################################

no config in this file,, just explenation on how to setup/reconfigure:

1. First setup Harmony Hub and connect with the Harmony App

2. Then add devices to harmony Hub,
   or teach Harmony Hub the codes/functions you want

3. Adding Harmony Hub integration in HA
   look for new config-file "/config/harmony_12427489.conf"
     in that file you will find the devices/commands you can use

4. Then add service-calls to activate the codes/functions you want

  action: call-service
  service: remote.send_command
  service_data:
    entity_id: remote.hubby
    command: PowerOn
    device: Vie Selected