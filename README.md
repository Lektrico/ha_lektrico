[![hacs_badge](https://img.shields.io/badge/HACS-Custom-41BDF5.svg?style=for-the-badge)](https://github.com/hacs/integration)

Custom Component for [Home Assistant](http://www.home-assistant.io).

# Lektrico Charging Station
This custom integration allows you to manage your [Lektrico EV Charger](https://lektri.co/charging-solutions/1p7k/) and your EM Load balancing device.

## Installation ##
Configuration can be done on UI, you need to enter the IP of your charger.
Lektrico devices are also discoverable with Zeroconf.

## Supported entities for EV Charger##
- Charge Start
- Charge Stop
- Reboot
- State
- Charging time
- Current
- Installation current
- Power
- Energy
- Temperature
- Lifetime energy
- Voltage
- Limit reason
- Led brightness
- Dynamic limit
- User limit
- Errors
- Lock
- Authentication

## Supported entities for Load Balancer device##
- LB mode
- Current
- Voltage
- Power
- Breaker current
- PF
- Reboot

## Device Info ##
- Name
- Serial Number
- Revision
- Producer
- Firmware
