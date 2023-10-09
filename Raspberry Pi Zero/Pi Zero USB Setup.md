
Wenn wir ein Image auf die SD-Karte gespielt haben können wir auch direkt die USB-Verbindung aktivieren. So können wir den Raspberry nur über den USB-Anschluss am Laptop betrieben.

Da die Boot-Partion FAT32 formatiert ist können wir einfach in Windows darauf zugreifen.

Wir suchen und öffnen die **config.txt** und fügen ganz am ende ein: _dtoverlay=dwc2_

Als nächste öffnen wir **cmdline.txt** und suchen *`rootwait*` und fügen dahinter _modules-`load=dwc2,g_ether`_ ein. Leerzeichen nicht vergessen nach *`rootwait*` bzw. vor _modules-`load=dwc2,g_ether`_

Damit wir unseren Hostname für die Verbindung nehmen können ist mDNS erforderlich. Die Software dafür gibt es von Apple und wird auch oft von Geräten wie Druckern verwendet.

[https://support.apple.com/kb/DL999?locale=en_US](https://support.apple.com/kb/DL999?locale=en_US)

Wenn der Raspi jetzt am USB Port angeschlossen werden sollte nach 2-3 Minuten Windows ein neues USB-Gerät erkennen - eine Netzwerverbindung.

Es muss der zweite USB-Mikro Port gewählt werden. Der erste liefert nur Power, der zweite USB Funktionalität und Power. Das Netzteil brauchen wir nicht - der USB3 Anschluss liefert genug Power.

Windows hat bei mir direkt `192.168.137.1` als Subnetz für den Adapter vergeben. Da der Raspberry nicht immer die selbe IP bekommt muss man diese manchmal suchen.

Hier kann uns nmap helfen:

**`nmap -sn 192.168.137.0/24`**