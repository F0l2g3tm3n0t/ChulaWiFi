# ChulaWiFi
    How to connect to ChulaWiFi in Linux

## wpa_supplicant Configuration File 
- Download and edit <i>wpa_supplicant.conf</i> <br>
```
    nano /etc/wpa_supplicant/wpa_supplicant.conf
```
- Change <b><i>identity</i></b> and <b><i>password</b></i> to your student ID and password.

## Network Interface Configuration File 
- Edit network interface configuration file
```
    nano /etc/network/interfaces
```
- Add this line in network interface configuration file
```
    allow-hotplug wlan0                                     ### Change to your wireless interface 
    iface wlan0 inet dhcp                                   ### Request DHCP from dhcp server
        wpa-conf /etc/wpa_supplicant/wpa_supplicant.conf    ### Use the configuration in wpa_supplicant file
```
