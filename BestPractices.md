# Best Practices with Crestron #

----------

### Device Firmware and Upgrading ###
There is probably a 50/50 split about upgrading firmware and as such, the best practice is unclear. Some Crestron employees will tell you very plainly, if you aren't experiencing problems, or you don't require new features, firmware should not be upgraded for the sake of upgrading. 

Others argue that upgraded firmware fixes problems and you should upgrade. At the same time, one must recognize that upgraded firmware may introduce new bugs. 

*You have to find the right balance for your clients and your business.* 

Upgrading on release day is not a best practice unless you are working directly with Crestron on resolving a particular bug.

----------
### Cresnet Best Practices ###
 - Crestron recommends that you keep the total number of devices on one segment or leg of a Cresnet run to a maximum of 20 devices. Some people put over 100 devices on a Cresnet segment. There are two issues with this: the RS-485 stack is going to request information from each of the devices and by the time it cycles back around to the devices which it has traffic for, latency can become an issue.  Larger Cresnet networks can also introduce intermittent problems that are hard to troubleshoot. The new Crestron bridge devices explicitly limit the number of devices you can put on a run to less than 30.

----------

### SIMPL Windows Programming Best Practices ###

#### 1. Program Name ####
#### 2. Program Organization ####
#### 3. Signal Naming ####
#### 4. Comments ####
#### 5. Documenting Changes ####

----------
### VTPro-e Best Practices ###
#### 1. Project Name ####
#### 2. Project Organization ####
#### 3. Indicating State ####
Indicating state through color alone is not a best practice. Color blind users will not be able to operate the system.