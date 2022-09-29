###############################################################################
#   @author       :   ArveVM 
#   @date         :   15.march.2022
#   @integration  :   Homeasssitant :)
#   @description  :   customize entities
#   @basic concept: 
#      renaming entities and change type/device class
#
#   Guess I will prefer to re-classify within each solution - but you never know
#
#   Tip stolen directly from https://github.com/frenck/home-assistant-config
#      "Sets up Home Assistant.
#       Basically, everything that doesn't have to be in the
#       main configuration.yaml"  - frenck
# 
#   further info: https://www.home-assistant.io/docs/configuration/customizing-devices/
#
###############################################################################


# Customize individual entities:
homeassistant:
  customize: !include ../../entities/customize.yaml
  
