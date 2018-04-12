# netctl_eduroam_hs-augsburg
How to connect to the HS-Augsburg Wifi with netctl

`/etc/netctl/eduroam`

```
Description='Eduroam-profile for HSß-Augsburg'
Interface=<dein-wlan-interface>
Connection=wireless
Security='wpa-configsection'
IP=dhcp
ESSID=eduroam
WPAConfigSection=(
    	  'ssid="eduroam"'
        'proto=WPA2'
        'key_mgmt=WPA-EAP'
        'eap=PEAP'
        'identity="<Z-ID>@hs-augsburg.de"'
        'password=<password>'
        'ca_cert="/etc/ssl/certs/Deutsche_Telekom_Root_CA_2.pem"'
        'phase2="auth=MSCHAPV2"'
)
```

instead of `password="<password>"'` you could run this command `tr -d '[:space:]' | iconv -t utf16le | openssl md4
` type your Password, press enter and then pess ctr-d which will copy the Key to you clipboard. Then change the Line to: `password="hash:<hash>"`
