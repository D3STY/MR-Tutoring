## WSL Updaten

Zunächst sollten wir das Windows-Subsystem for Linux auf den aktuellsten Stand bringen.

```powershell
wsl --update
```

## WSL Installation

Anschließend können wir Kali-Linux installieren:

```powershell
wsl --install kali-linux
```

# MS-Defender konfigurieren

Wenn die Installation abgeschlossen ist kommt Kali zunächst ohne alle Tools. Wir müssen zunächst den Installationspfad beim MS-Defender ausschließen.

Folgenden Ordner müssen wir dafür ausschließen:

```powershell
C:\\Users\\BENUTZERNAME\\AppData\\Local\\Packages\\KaliLinux.54290C8133FEE_ey8k8hqnwqnmg
```

Ihr müsst natürlich euren Benutzernamen anpassen. Eine ausführliche Anleitung zum ausschließen findet ihr hier:

[Hinzufügen eines Ausschlusses zu Windows-Sicherheit - Microsoft-Support](https://support.microsoft.com/de-de/windows/hinzuf%C3%BCgen-eines-ausschlusses-zu-windows-sicherheit-811816c0-4dfd-af4a-47e4-c301afe13b26)

## Kali starten

Nun kann Kali direkt über PowerShell gestartet werden.

```powershell
wsl -d kali-linux
```

Auch bei Kali müsst ihr zunächst einen Usernamen und Passwort wählen - Nein, wir arbeiten in Kali nicht als root!

Anschließend kann man die Kali-Tools installieren:

```bash
sudo apt install kali-linux-everything
```

Kali kann vollständig über das Windows-Terminal verwendet werden. Ihr könnt aber auch GUI-Anwendungen starten.

Man kann jedoch auch den XFCE Desktop von Kali unter WSL verwenden:

[Win-KeX | Kali Linux Documentation](https://www.kali.org/docs/wsl/win-kex/)

Weitere Informationen zu WSL findet ihr hier:

[Installieren von WSL | Microsoft Learn](https://learn.microsoft.com/de-de/windows/wsl/install)

Unter Windows 11 ist WSL2 standard.