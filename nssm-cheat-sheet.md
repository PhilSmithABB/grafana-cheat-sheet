# NSSM Cheat Sheet for Grafana

Below are the nssm cli commands that are used for installing, removing, and troubleshooting using nssm
to install Grafana as a service on windows.

## Installation
To install a service use, this will open the NSSM service installer GUI with the service name already populated
`nssm install <servicename>` 

![alt text](https://raw.githubusercontent.com/PhilSmithABB/grafana-cheat-sheet/dev/nssm-gui.png 'image shows the nssm gui application tab')

_Notes_ 
 - For setting a service parameter you can either use set or reset. The commands below have them as set/reset to demonstrate that either can be used
 - The Service name in the images is Grafana, it may have a different name in production. To get the service name open services.msc, find the Grafana service you want details on, right click on it and select properties, the properties dialog will tell you the Service name

### Application cli commands


Set or get the application path
```
nssm set/reset Grafana Application <path_to_exe>
nssm get Grafana Application 
```
Set or get the startup directory

```
nssm set/reset Grafana AppDirectory <path_to_directory>
nssm get Grafana AppDirectory
```

Set or get the Grafana paramerts (if any)
```
nssm set/reset Grafana AppParameters <params>
nssm get Grafana AppParameters
```

### Details cli commands

![alt text](https://raw.githubusercontent.com/PhilSmithABB/grafana-cheat-sheet/dev/nssm-gui-details.png 'image shows the nssm gui details tab')

Get or set the display name
```
nssm set/reset Grafana DisplayName display_name_text
nssm get Grafana DisplayName
```

Get or set the Description _Note - don't use quotation marks_
```
nssm set/reset Grafana Description <description_text>
nssm get Grafana Description
```

Get or set the startup type where `<start_type>` is one of the following:
 - _SERVICE_AUTO_START_: Automatic start at boot
 - _SERVICE_DELAYED_START_: Delayed start at boot
 - _SERVICE_DEMAND_START_: Manual start
 - _SERVICE_DISABLED_: Service is disabled
```
nssm set/reset Grafana start <start_type>
nssm get Grafana start
```

### Start, Stop, Restart, Remove 

To start
```
nssm start Grafana 
```

To stop
```
nssm stop Grafana
```

To restart 
```
nssm restart Grafana
```

The following commands will open the nssm gui 'Remove a Service' dialog.

To remove any service via the dialog. 
_Notes_: 
 - Stop the service before doing this
 - This only works with nssm created services afaik
```
nssm remove
```

To remove Grafana via the dialog
```
nssm remove Grafana
```

To remove Grafana without the dialog 
```
nssm remove Grafana confirm
```


##### Additional reading
A more comprehensive guide can be found https://nssm.cc/usage. 