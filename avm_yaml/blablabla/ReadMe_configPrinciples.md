# My Config principles; 'Functionality and Solutions'
(under construction, so this is the march-version,,)
1. My world of HA is split into two domains;
   - Solutions are the usage of Functionality to create automagicallity  :)
   - Functionality is the enabler of Solutions 
2. All Home Assistant Functionality comes from either an Integration or an Add-on
   - this includes the HA itself, which I see as 'documented and configurable' as an Integration (maybe a simplification, but it works for this principle)
3. Functionality configuration options:
   - GUI configuration   (preferred by me)
   - .yaml configuration: 
     - yaml-file must be named according to the actual integration/addon to which the functionality is actually loaded
     - as configuration goes,, it can also be like adding sensors or templates to the integration to enable what could/should have been logically incuded
     - all 'manual .yaml-configuration' should (if possible) be separated from installed integrations/addons 
     - by creating /config/avm_yaml/packages/integrations/ I've made a placeholder for this principle
   - Add-ons can also require an manual configuration. If so; add prefix addon to file and add to the other manual functionality config in the /integrations-folder 
4. How do HA enable Functionality?:
   - Addons installed/configured   -> addon-startup (manually or automatically at HA-startup)
   - Integrations installed/configured  -> enabled at HA startup if not disabled. Some can also be re-loaded from integration GUI?
   - configuration.yaml   -> is loaded at startup (using 'packages-functionality' and is in my configuration adding further functionality in Integrations-folder
     - integrations-folder added functionality:
       - default_config.yaml -> is adding loads of 'base functionality'
       - etc etc - see files in folder  
   - and that's it - > through that principle ALL functionality can be controlled; either it's 
     - an Addon
     - installed Integration
     - something .yaml added to the Integrations-folder!
5. All solutions should be kept separate from Functionality
   - One .yaml-file pr solution -> all files in the /config/avm_yaml/packages/solutions/ - folder  (or structure of sub-folders if required)
   - You must decide/create your own structure/namin for your Solutions, based upon your requirements and preferences
     - be prepared to use/change naming-standards according to solution-structure, to be able to find sensors in need for reconfig 
   - Since configuration.yaml is including functionality in solutions-folder,, all files will be loaded at startup
   - all .yaml-files in solutions must have intendation and spaces as if code was written directly in configuration.yaml,, se examples
 6. Combinations (no rule without exeptions)
    - Groups of functionality can be added in Entities-folder (sensors, templates and utilitymeters using !include - principles) 
    - still some cleanup for me there,, but will I get rid of this


## Why the need for "My config principles"?:
I've worked quite a few hours trying to get my head around all different types/styles of config's and have concluded that I have to take a slightly different approach.
My background is from financial/management and not that of code, so it is possible that I'm a bit slow on that department - but I for sure have a need for control and overview. I need to know that the sum of the parts =  the total,, so I need to see how stuff work - and how things cascades

As a newbie to HA it was frustrating to see functionality not defined and not understanding where configuration should go,,, but I loved the actual "everyting works if you tinker a bit"

In my head it will also enable sharing solutions simpler

And overview of small integrations that need a sensor added to their config is now much much easier to explain and to share