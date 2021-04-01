# Setting up a mobile wifi hotspot

From **Preferences -> Sharing**
Select your external connection e.g ethernet or USB/Bluetooth to mobile device.

![Screen_Shot_2018-10-24_at_12.20.42_PM](/uploads/cb3da2fc7d20d315c030db3092856b13/Screen_Shot_2018-10-24_at_12.20.42_PM.png)

Go to **Wifi options**, enter matching SSID to R-IoT device (**"riot"**) and set security to **none**
![Screen_Shot_2018-10-24_at_12.21.51_PM](/uploads/4a3e5999e14865548ffa736f113cf589/Screen_Shot_2018-10-24_at_12.21.51_PM.png)

Turn on the R-IoT and enable internet sharing. If connected, the on-board LED should go from green to blue

To receive the data on the computer, you'll need to change your IPv4 address to match the device configuration. Run the following command
````
sudo ifconfig en0 192.168.1.100 netmask 255.255.255.0
````

Use this processing sketch to monitor inputs directly
[OSCDataPlotter.zip](/uploads/1a2d9ec4d86e649aac9a0268e8c3ce8d/OSCDataPlotter.zip)

To use the WebSocket examples, run the main python script and open **ClientBIT.html**
```
$ python3 riot_serverBIT.py -ssid 'riot' --ip '192.168.1.100' --port 8888 --id 0
```
