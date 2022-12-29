# Tapo-P110-Domoticz
Energy monitoring Tapo P110 smart plug for Domoticz TP-Link Tapo P110 plugin for Domoticz.  
Include on/off switch and energy monitor.  
Fork form https://github.com/593304/Domoticz-Tapo

## Prerequisites
### PyP100 library
This module is using Toby Johnson's PyP100 library.  
Install this module by running this command: `pip3 install PyP100`  
You will also need the IP address of your Tapo device(s).

## Installation
Connect to your Domoticz server via SSH and go to Domoticz's plugins directory. Clone this repository into the plugins directory:  
`git clone https://github.com/Ravenheld/Tapo-P110-Domoticz.git`  
If necessary modify the access permissions for the plugin. For example:  
`chmod -R 777 Domoticz-Tapo/`

Then restart Domoticz service to add the Tapo plugin to the hardware list in Domoticz.
```
sudo service domoticz.sh stop
sudo service domoticz.sh start
```
or
```
sudo service domoticz.sh restart
```

## Configuration
If Domoticz started, then go to the Hardware page on your Domoticz website and add a new one.  
You should find the TP-Link Tapo P110 Plugin in the Type list.  
Select it and set the following values:  
* Username (the email address of your Tapo account)  
* Password (the password for your Tapo account)  
* IP address (the local IP address of your Tapo device)  
* Debug (you can turn on or off debug messages)

Then in Devices, you should see 2 new devices :
* A Light/Sitch - Selector Switch
* A General - kWh

Add the wanted devices and, for the General-kWh, go to edit and select "Computed" on the Energy read line.  
(the TP110 doesn't give total energy use, so Domoticz will add all individual data to create the missing data)
