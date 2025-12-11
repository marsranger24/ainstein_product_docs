---
title: People Counting
excerpt: ''
deprecated: false
hidden: false
metadata:
  title: ''
  description: ''
  robots: noindex
next:
  description: ''
---
## Required Material

- Raspberry Pi 3B+
- 5V 2A Micro-USB Power Supply
- 32 GB Micro SD Card
- Raspberry Pi Case
- Ethernet Cable
- WAYV Air Package
  - WAYV Air
  - USB-C Cable
  - Mount w/ screws

## Facility Requirements

- 120V Power Plug
- WiFi network

## Initial Setup

1. Download and install the [Raspberry Pi Imager](https://www.raspberrypi.org/software/)
2. Download the [PeopleCount OS image](https://drive.google.com/file/d/1Rb7CEQmvnAPcOL2WQ_k_L2agm1jhO0kV/view?usp=sharing)
3. Open the Raspberry Pi Imager

![](https://files.readme.io/76b9380-rpi_imager_screenshot.png "rpi_imager_screenshot.png")

4. Select 'Choose OS' and select 'Use custom'

![](https://files.readme.io/c8c3895-rpi_splashpage.png "rpi_splashpage.png")

![](https://files.readme.io/47b5357-usecustom_screenshot.png "usecustom_screenshot.png")

5. Browse for the WA_PeopleCount.img file

![](https://files.readme.io/75b6672-img_ss.png "img_ss.png")

6. Select 'Choose Storage' and choose your Micro SD Card

![](https://files.readme.io/04a3ed4-storage_ss.png "storage_ss.png")

7. Select 'Write' and allow the imager to mount the operating system to the SD card

A "Write Successful" prompt will appear indicating the OS has successfully written to the SD card

## Connect your Raspberry Pi to WiFi

With the SD card inserted, and the Raspberry Pi powered on:

1. Insert the ethernet cable into the the ethernet port on the Raspberry Pi and insert the the other end of the cable into your personal computer.
2. Open a command terminal and enter:

```text
ssh pi@raspberrypi.local
```

3. The terminal will prompt for a password. Enter **ainstein**

![](https://files.readme.io/38e0f5f-pi_login_ss.png "pi_login_ss.png")

4. In the terminal enter:

```text
sudo raspi-config
```

5. Select 'System Options'

![](https://files.readme.io/ab352f4-raspi-config_ss.png "raspi-config_ss.png")

6. Select 'Wireless LAN' and enter your WiFi's SSID and Password

![](https://files.readme.io/bd15d9f-wireless_lan_ss.png "wireless_lan_ss.png")

> 📘 Helpful Hint:
> 
> Enter the command 'ping 8.8.8.8'  in the terminal to verify if your Raspberry Pi is successfully connected to the internet.

7. Upon successfully connecting the Raspberry Pi to WiFi. Enter the following in the terminal: 

```text
ifconfig
```

8. Record **inet address** under wlan0

![](https://files.readme.io/4bcbfdf-ifconfig_ss.png "ifconfig_ss.png")

> 📘 Jot the inet Address Down
> 
> You will need this address to ssh into the Raspberry Pi later

## WAYV Air Configuration

1. Mount the WAYV Air to the wall or ceiling using the screws and swivel mount provided

![](https://files.readme.io/aeb0c6f-IMG_1729.jpg "IMG_1729.jpg")

2. Select the network icon in the windows taskbar and connect to the WAYV Air via WiFi. The name of the SSID will match the WAYV Air's serial number. The default password is **12345678**

![](https://files.readme.io/2d8ac53-wifi_ss.png "wifi_ss.png")

3. Select the Windows Start Menu and search for 'View Network Connections'. 

![](https://files.readme.io/29d9f2f-view_network_ss.png "view_network_ss.png")

4. Right click on the WiFi adapter and select 'Properties'

![](https://files.readme.io/6b705e3-properties_ss.png "properties_ss.png")

5. Select 'Internet Protocol Version 4 (TCP/IPv4)'. Select 'Use the following IP address' and enter **192.168.4.65** for the IP Address and **255.255.255.0** for the Subnet Mask. Select 'OK'

![](https://files.readme.io/dd2131a-ipv4_properties_ss.png "ipv4_properties_ss.png")

6. Open the WAYV Air Visualizer and press the 'Connection Settings' button

![](https://files.readme.io/b29d83f-visualizer_ss.png "visualizer_ss.png")

7. Select 'WIFI' and press OK.

![](https://files.readme.io/a7a3109-wa_settings_ss.png "wa_settings_ss.png")

8. Press the 'Connect' button
9. Press the 'System Config' button, check the 'CFG CMD' box and select 'Query.' This will populate the configuration settings.

![](https://files.readme.io/3d2d692-system_config_ss.png "system_config_ss.png")

10. In the configuration, look for the **SceneryParam** line. Adjust the parameters to tune the radar to the environment the radar is installed in.

The best way to do this is to take a measuring tape, and measure horizontally from the radar to the edge of the desired area you want the radar to cover.

> 📘 SceneryParam Format
> 
> The Scenery Parameter is defined as -X +X -Y +Y -Z +Z.
> 
> Example: SceneryParam -3.0 3 -0.1 10 -2 2
> 
> The WAYV Air will only track targets up to 3 meters in the -X and +X directions. 10 meters in the +Y direction, and 2 meters in the -Z and +Z directions.

## PeopleCount Configuration

Connect to the Raspberry Pi remotely by entering the following

```text
ssh pi@<inet address>
```

> 📘 inet Address
> 
> This is the number you recorded previously

1. In the Raspberry Pi terminal:

```text
sudo systemctl stop radar_app.service

sudo pkill -f wayv -e
```

This will stop the current PeopleCount application from running

2. The PeopleCount application must be run offline to adjust several parameters. In the Raspberry Pi terminal enter:

```text
cd ~/wayv_air_in_out
python3 radar_threshold_app.py -vv -devicekey <value> -Dx <value> -Dz <value> -Din <value> -Dout <value>
```

Dx, Dz, Din, and Dout are defined by:

![](https://files.readme.io/67d888d-1.png "1.png")

> 📘 Helpful Hint
> 
> For more information about the PeopleCount application's arguments run **python3 radar_threshold_app.py -h**

To find Dx and Dz, have a person stand in the center of the doorway and record the Dx and Dz values seen on the terminal.

Din is the interior threshold and Dout is the exterior threshold. These are needed so the application can differentiate a person entering or leaving a space. These are defined by the user and are dependent on the location in which PeopleCount is installed.

> 📘 What are Din and Dout?
> 
> Din -> Dout = A person is entering the building  
> Dout -> Din = A person is leaving the building

3. Once Dx, Dz, Din, and Dout have been determined, save those values and add them to **run_wayv_air_door_count.sh**

In the Raspberry Pi Terminal:

```text
cd ..
nano run_wayv_air_door_count.sh
```

```text
#!/bin/bash

# Device 1
#to connect via WiFi use the -ip and -wifi_port options
python3 /home/pi/wayv_air_in_out/radar_threshold_app.py -logdir /home/pi/logs  -devicekey device1 -server production -Dx <x> -Dz <z> -Din <in> -Dout <out> &
```

> 📘 DeviceKey
> 
> Use the serial number of the WAYV Air as the devicekey. Be sure to record the devicekey for later

> 🚧 
> 
> Replace x, z, in, out with the values determined above

4. Enter command **ctrl+x** to exit and save run_wayv_air_door_count.sh

In the Raspberry Pi Terminal:

```text
sudo reboot
```

## PeopleCount Application Setup

1. Sign up or log in to your [PeopleCount](https://portal.peoplecount.live/login) account

![](https://files.readme.io/fe55d17-peoplecount_ss.png "peoplecount_ss.png")

2. On the dashboard select 'Live Counters'

![](https://files.readme.io/38b1582-live_counter_ss.png "live_counter_ss.png")

3. Press the '...' icon in the top right corner and select 'Add New Counter'

![](https://files.readme.io/6bea5e8-options_ss.png "options_ss.png")

4. Enter a Counter Name as well as other notes and capacity limits to your counter.

5. Under Device ID, be sure to use the **same Device ID that was used above. This should be the WAYV Air's serial number**. Press 'Save & Continue'

![](https://files.readme.io/a6cef0e-device_id_ss.png "device_id_ss.png")

6. The WAYV Air should now add and subtract people to the counter

![](https://files.readme.io/1c8911e-counter_ss.png "counter_ss.png")