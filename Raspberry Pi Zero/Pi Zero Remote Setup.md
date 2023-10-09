
Hier bekommt man die Software um das OS Image direkt auf die SD-Karte zu laden:

[https://www.raspberrypi.com/software/](https://www.raspberrypi.com/software/)

Als OS sollten wir Raspberry Pi OS Lite 32-Bit wählen. Es kommt ohne Desktop Environment

Wenn das Zahnrad am unteren rechten Rand nicht erscheint drücken wir einfach

_STRG+Shift+X_

Hier können wir nun alle Einstellungen vornehmen um den Raspberry vollkommen ohne Tastatur, Maus und Monitor zu betreiben (headless)

- SSH sollte aktiviert werden.
- Für SSH ist es erforderlich einen Benutzernamen und Passwort zu wählen
- Unter WiFi Einrichten können wir unser WLAN und Passwort setzen. (Land sollte auf DE stehen)
- Zuletzt können und sollten wir noch die Spracheinstellungen festlegen. Europe/Berlin dürfte für die meisten passen. Als Tastatur Layout empfehle ich _de_

Als nächstes stecken wir die SD-Karte in den Computer. In den meisten Fällen muss dafür der Adapter verwendet werden.

Auf _Schreiben_ klicken und etwas warten bis der Vorgang abgeschlossen ist.

Danach kann die SD-Karte in den Raspi eingesteckt und gebootet werden.

Er braucht, gerade beim ersten Start etwas - aber nach einigen Minuten sollten wir unseren Raspberry Pi im WLAN finden können.

Verbinden können wir uns dann mit:

`ssh [username@raspberry.local]

`ssh username@IP_des_Raspi`

Wir können auch ein anderes Betriebssystem wählen, wie z.b. Kali.

Dann funktionieren die Headless-Einstellungen im Imager jedoch nicht.