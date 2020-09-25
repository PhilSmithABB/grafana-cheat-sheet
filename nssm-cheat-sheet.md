# NSSM Cheat Sheet for Grafana

Below are the nssm cli commands that are used for installing, removing, and troubleshooting using nssm
to install Grafana as a service on windows.

## Installation
To install a service use, this will open the NSSM service installer GUI with the service name already populated
`nssm install <servicename>` 

![alt text](https://nssm.cc/images/install_application.png 'NSSM Gui')

_Note_ - The app in the 
### Equivalent  cli commands


Set the application path
```
nssm set UT2003 Application <path_to_exe>
```
Set the startup directory

```
nssm set UT2003 AppDirectory <path_to_directory>
```

Set the arguments
```
nssm set UT2003 AppParameters <params>
```