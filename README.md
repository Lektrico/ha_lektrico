[![hacs_badge](https://img.shields.io/badge/HACS-Custom-41BDF5.svg?style=for-the-badge)](https://github.com/hacs/integration)

Custom Component for [Home Assistant](http://www.home-assistant.io).

![LEKTRI.CO](https://lektri.co/wp-content/uploads/2023/06/logo-wbg.png)

# Lektrico Charging Station
This custom integration allows you to manage your [Lektrico EV Charger](https://lektri.co/charging-solutions/1p7k/) and your [Lektrico Load Balancer](https://lektri.co/charging-solutions/smart-load-balancing/) device that are in your wifi network.

## Installation ##
Configuration can be done on UI.

Lektrico devices are discoverable with Zeroconf.

You can also add manually the device if you know its IP.


### Installation steps: ###
1. You must have Home Assistant  and  HACS (Home Assistant Community Store) installed.
2. Download the "Lektrico Charging Station" integration from HACS.  (don't forget to restart Home Assistant after the download)
3. Go to _Settings_ -> _Devices & Services_ and you should see there all Lektrico devices that are currently online in your wifi network.


## Supported entities for EV Charger ##


|    **Entity name**   | **Entity type** | **Values' type** | **Accepted values** |                                                                                                              **Description**                                                                                                              |
|:--------------------:|:---------------:|:----------------:|:-------------------:|:-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------:|
|    Authentication    |      switch     |      boolean     |      true/false     |                                                                      Defines if the charger requires authentication or just plug in the connector and it will charge.                                                                     |
|     Charge start     |      button     |         -        |          -          |                                                                                                    Sends the command to start charging.                                                                                                   |
|      Charge stop     |      button     |         -        |          -          |                                                                                                    Sends the command to stop charging.                                                                                                    |
|     Charging time    |      sensor     |      integer     |          -          |                                                                                                     Current session charging time in s                                                                                                    |
|        Current       |      sensor     |      double      |          -          |                                                                                                               Current value.                                                                                                              |
|     Dynamic limit    |      number     |      integer     |         0-32        | Dynamic current value. 0: Pause charging process.  6 - 32: Resume charging process with current limited to value.                                                                                                                         |
|        Energy        |      sensor     |      double      |          -          |                                                                                                   Current session charged energy in Wh.                                                                                                   |
|        Errors        |  binary_sensor  |      boolean     |          -          | Flag to specify if the charger has active errors. Has attributes that shows: State e activated, Overtemp, Critical temp, Overcurrent, Meter fault, Undervoltage error, Overvoltage error, Rcd error, Cp diode failure, Contactor failure. |
| Installation current |      sensor     |      integer     |          -          |                                                                           Current value [A] to be limited by software. Set according to electrical installation.                                                                          |
|    Led brightness    |      number     |      integer     |       10 - 100      |                                                                                                        LED maximum brightness in %.                                                                                                       |
|    Lifetime energy   |      sensor     |      integer     |          -          |                                                                                                        Total charged energy [kWh].                                                                                                        |
|     Limit reason     |      sensor     |      string      |          -          |                                                          Current limit reason. Values: No limit, Installation current, User limit, Dynamic limit, Schedule, EM offline, EM, OCPP                                                          |
|         Lock         |      switch     |      boolean     |      true/false     |                                                                       Specify if the charger is locked or not. If set to true, no charging session will be started.                                                                       |
|         Power        |      sensor     |      double      |          -          |                                                                                                        Current instant power in W.                                                                                                        |
|        Reboot        |      button     |         -        |          -          |                                                                           Reset device. If a charging session is active, the device will wait for its end first.                                                                          |
|         State        |      sensor     |      string      |          -          |                                                                  Charger state. Values: Available, Connected, Authentication, Charging, Error, Updating, Locked, Paused.                                                                  |
|      Temperature     |      sensor     |      double      |          -          |                                                                                                             Board temperature.                                                                                                            |
|      User limit      |      number     |      integer     |         6-32        |                                                                                                               User current.                                                                                                               |
|        Voltage       |      sensor     |      double      |          -          |                                                                                                          Current voltage value.                                                                                                           |


## Supported entities for Load Balancer device ##


| **Entity name** | **Entity type** | **Values’ type** | **Accepted values** |                                     **Description**                                     |
|:---------------:|:---------------:|:-----------------:|:-------------------:|:---------------------------------------------------------------------------------------:|
| Breaker current |      sensor     |      integer      |          -          | Main breaker current. This will be the maximum current the household is allowed to use. |
|     Current     |      sensor     |       double      |          -          |                                     Measured current.                                   |
|     LB mode     |      select     |      integer      |        0 – 3        |             Load balancing mode. Values: 0-Off, 1-Power, 2-Hybrid, 3-Green.             |
|        PF       |      sensor     |       double      |          -          |                                      Power factor.                                      |
|      Power      |      sensor     |       double      |          -          |                                  Measured active power.                                 |
|      Reboot     |      button     |         -         |          -          |                                      Reset device.                                      |
|     Voltage     |      sensor     |       double      |          -          |                                    Measured voltage.                                    |


## Device Info ##
- Name
- Serial Number
- Revision
- Producer
- Firmware
