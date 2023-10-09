Ein ordentlicher Workspace ist das A und O eines jeden ITlers. Daher zeige ich euch einmal meinen Workspace - um euch ein wenig zu inspirieren. Jeder hat andere vorlieben oder Arbeitsweisen und das ist auch fein. Irgendwo muss man jedoch anfangen.

Basis ist Kali in WSL mit VSCode und dem Windows Terminal.

tmux ist ein Open-Source-Terminal-Multiplexer für Unix-ähnliche Betriebssysteme. Er ermöglicht den gleichzeitigen Zugriff auf mehrere Terminal-Sitzungen in einem einzigen Fenster. Dies ist nützlich, um mehr als ein Kommandozeilenprogramm gleichzeitig auszuführen. Es kann auch verwendet werden, um Prozesse von ihren kontrollierenden Terminals zu trennen, wodurch Remote-Sitzungen aktiv bleiben können, ohne sichtbar zu sein.

Tmux verfolgt einen ähnlichen Ansatz wie vim. Man benötigt keine Maus und kann komplett über die Tastatur arbeiten. Inzwischen unterstüzt tmux aber auch die Eingabe per Maus.

## Installation VSCode und Windows Terminal

[XP9KHM4BK9FZ7Q](https://apps.microsoft.com/store/detail/XP9KHM4BK9FZ7Q?ocid=pdpshare) - VSCode
[9N0DX20HK701](https://www.microsoft.com/store/productid/9N0DX20HK701?ocid=pdpshare) - Windows Terminal

## Installation Tmux in Kali

Zusätzlich empfehle ich TMux in Kali zu verwenden.

```bash
sudo apt install tmux tmux-plugin-manager
```

Die Tmux Config ist am Anfang alles andere als Trivial. Zum Glück gibt es gute Configs im Netz. Ich empfehle hier .tmux (früher oh-my-tmux).

```bash
$ cd
$ git clone <https://github.com/gpakosz/.tmux.git>
$ ln -s -f .tmux/.tmux.conf
$ cp .tmux/.tmux.conf.local .
```

[gpakosz/.tmux: 🇫🇷 Oh my tmux! My self-contained, pretty & versatile tmux configuration made with ❤️ (github.com)](https://github.com/gpakosz/.tmux)

### Für Tmux kann ich diese THM Rooms empfehlen:

[TryHackMe | REmux The Tmux](https://tryhackme.com/room/tmuxremux) [TryHackMe | tmux](https://tryhackme.com/room/rptmux)

## THM VPN einrichten

Unter [TryHackMe | Network Access](https://tryhackme.com/access) stellen wir zunächst den VPN-Server auf EU-VIP-1 oder -2. Dort ist weniger los und wir haben in der Regel eine bessere Verbindung.

Danach generieren wir über den Button einen Config und laden diese runter. Wir bekommen einen .ovpn Datei mit unserem Benutzernamen. Diese können wir über Windows einfach in unser Homeverzeichnis Kopieren.

```bash
\\\\wsl.localhost\\kali-linux\\home\\
```

## Let hack some rooms

Kali sollte im Menu vom Windows Terminal bereits erscheinen. Genau wie alle anderen WSL Distris.

![Untitled](https://prod-files-secure.s3.us-west-2.amazonaws.com/519a7c62-28ec-47d3-8e4f-92e89273a0c7/26653ee7-7af1-4b9c-9c87-021ee52f3dec/Untitled.png)

Wir starten also unser Kali und landen in unserem Homeverzeichnis.

Ich habe mir für THM einen extra Ordner gemacht

```bash
mkdir THM 
```

Da kommt alles rein was mit THM zu tun hat. Also vor allem unseren OpenVPN Config.

```bash
cp *.ovpn ~/THM
```

WIr wechseln in den THM Ordner und starten eine neue TMux Session

```bash
cd THM
tmux new-session -s THM
```

Wir landen wieder im Shell und unten ist eine Statusbar. Diese können wir später noch unseren wünschen Anpassen. Infos dazu findet man hier: [Writing Your tmux Config: a Detailed Guide (thevaluable.dev)](https://thevaluable.dev/tmux-config-mouseless/)

Nun verbinden wir uns mit dem VPN von THM

```bash
sudo openvpn USERNAME.ovpn
```

![Untitled](https://prod-files-secure.s3.us-west-2.amazonaws.com/519a7c62-28ec-47d3-8e4f-92e89273a0c7/e45fd840-74af-4c43-b87a-e94164417c8b/Untitled.png)

Die Magie kommt jetzt. Wir drücken STRG+A und danach einfach C Ein neues Shell öffnet sich und unser OpenVPN ist im Hintergrund.

Ob das VPN funktioniert testen wir mit

```bash
sudo ping 10.10.10.10
```

Wenn es so ausschaut habt ihr alles richtig gemacht

![Untitled](https://prod-files-secure.s3.us-west-2.amazonaws.com/519a7c62-28ec-47d3-8e4f-92e89273a0c7/d1cab9bf-a842-400e-8625-11245d9fad42/Untitled.png)

Zurück in den anderen Shell-Tab kommt ihr mit STRG+A (oder auch STRG+B) und Tab.

Ab jetzt könnt ihr ganz normal mit THM arbeiten ohne die AttackBox verwenden zu müssen und übt gleichzeigt noch mit Kali.

Mit STRG+A und - bzw _ könnt ihr das aktuelle Shell splitten, also teilen. Ihr wollt scannen und nicht für jeden Scan den Tab wechseln.

Die einzelnen Tastenkürzel stehen auf der Git Seite. Ihr könnt diese aber auch anpassen wenn ihr das wünscht. Ich würde am Anfang erstmal mit der Config arbeiten und dann anpassen.

![Untitled](https://prod-files-secure.s3.us-west-2.amazonaws.com/519a7c62-28ec-47d3-8e4f-92e89273a0c7/639d4ffe-f81a-4f6d-9a1d-a924ce7ccf98/Untitled.png)

Panels schließen könnt ihr mit STRG+A X - es wird noch mal abgefragt ob ihr wirklich wollt.

Mit STRG+A D könnt ihr Tmux schließen. Es läuft aber weiter und alle Shells ebenfalls!

Ihr könnt die Session wieder öffnen oder auch eine neue erstellen.

```bash
tmux attach -t THM
```

Wenn ihr mit THM fertig seit sollte ihr immer in den OpenVPN Tab gehen und die VPN Verbindung mit STRG+C stoppen.

Für HackTheBox erstellt ihr euch dann einfach einen HTB Ordner, kopiert deren VPN Config da rein und startet eure HTB Session mit

```bash
cd ~/HTB
tmux new-session -s HTB
```

So könnt ihr einfach mehre Projekte getrennt von einander betreiben und kommt mit den Dateien nicht durcheinander. Wie gesagt wie man sich da organisiert bleibt jedem selbst überlassen. Ich möchte hier nur einen Anstoß geben.

## VSCode und WSL

Wir starten unser VSCode und können nun einen Remoteverbindung herstellen, mit WSL

![Untitled](https://prod-files-secure.s3.us-west-2.amazonaws.com/519a7c62-28ec-47d3-8e4f-92e89273a0c7/37f6292a-b1bc-45f7-ac18-a22432966fca/Untitled.png)

Danach können wir einen Ordner in WSL öffnen. Also in unserem Fall den THM Ordner

![Untitled](https://prod-files-secure.s3.us-west-2.amazonaws.com/519a7c62-28ec-47d3-8e4f-92e89273a0c7/e19056dd-5996-4b6f-bf94-7905f7d9dacd/Untitled.png)

Danach könnt ihr Textfiles ganz easy in VSCode bearbeiten, filtern, durchsuchen - was man halt so macht.

![Untitled](https://prod-files-secure.s3.us-west-2.amazonaws.com/519a7c62-28ec-47d3-8e4f-92e89273a0c7/9c11ebf7-a3be-44ff-9231-67ca2903fa88/Untitled.png)

Das erspart uns nerviges arbeiten in Nano oder gar Vim. Auch Probleme mit der Zwischenablage gehören der Vergangenheit an.

Für Tmux gibt es viele Plugins, daher haben wir den Plugin Manager (TPM) direkt installiert.