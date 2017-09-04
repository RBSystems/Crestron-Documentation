# Best Practices with Crestron #

----------

### Device Firmware and Upgrading ###
*Fundamental Rule: You have to find the right balance for your clients and your business.*

 - There is probably a 50/50 split about upgrading firmware and as such, the best practice is unclear. Some Crestron employees will tell you very plainly, if you aren't experiencing problems, or you don't require new features, firmware should not be upgraded for the sake of upgrading. They say, "if it ain't broke, don't fix it" which is a euphemistic way of saying, if it isn't broken, don't break it. 
 - Others argue that upgraded firmware, as a rule, contains bug fixes and you should always upgrade.
 - At the same time, one must recognize that upgraded firmware may introduce new bugs and problems that you haven't seen previously. 
 - **Always read the release notes associated with the update.** They probably do not contain a complete change history but they are always worth reading. 
 - **Upgrading on release day is not a best practice unless you are working directly with Crestron on resolving a particular bug.**
 - My personal recommendations are:
  - Upgrade all devices on a new job to the current firmware revision.
  - On older jobs, if the firmware has been out for 12 months or more, I upgrade without concern on non-proc devices. If the device is a proc and the system has been stable for 6 months, and I am not uploading and updated program, I do not upgrade the firmware - with the caveat that if the proc exhibits the same instability every 3-6 months, I upgrade the firmware. 
  - If I am making program changes and uploading them to the proc, I update the proc firmware. 
 - **Avoid using the PUF tool unless the device you are upgrading requires it.** If you must use the PUF tool verify that you have a solid connection and a stable network before proceeding. Pinging the device for a while to make sure there are no lost packets would be one way of testing the network stability: "ping [ip] -t" and then CTRL-c to stop the ping when you are satisified. 
 - **Best practice is to FTP the file onto the device and issue the PUF command, on devices where the PUF command is supported.**

----------
### Cresnet Best Practices ###
 - Crestron recommends that you keep the total number of devices on one segment or leg of a Cresnet run to a maximum of 20 devices. Some people put over 100 devices on a Cresnet segment. There are two issues with this: the RS-485 stack communicates in a round-robin fashion. By the time it cycles back around to the devices that have traffic, latency can become an issue.  Larger Cresnet networks can also introduce intermittent problems that are hard to troubleshoot. The new Crestron bridge devices explicitly limit the number of devices you can put on a run to less than 30.

----------
### Networking Best Practices ###
 - Isolate the controls network from other networks to the extent possible.
 - Develop a network standards document to segregate device types on the subnet(s) involved. For example: routing devices, network switches, processors, touchpanels with a DHCP range at the bottom of the subnet etc... This makes device location, troubleshooting and maintenance much easier.


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
