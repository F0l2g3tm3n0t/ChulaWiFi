# ChulaWiFi
How to automatically connect to ChulaWiFi in Linux

## wpa_supplicant Configuration File 
- Edit <i>wpa_supplicant.conf</i><br>
```
    nano /etc/wpa_supplicant/wpa_supplicant.conf
```
- Change <b><i>identity</i></b> and <b><i>password</b></i> to your student ID and password (same as reg.chula).
```
    network={
        ssid="ChulaWiFi"
        priority=1
        proto=RSN
        key_mgmt=WPA-EAP
        pairwise=CCMP
        auth_alg=OPEN
        eap=PEAP
        identity="student_id"
        password="password"
        phase1="peaplabel=0"
        phase2="auth=MSCHAPV2"
    }
```

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

## For Security
You can hash the password instead of using plain text in wpa_supplicant configuration file.
