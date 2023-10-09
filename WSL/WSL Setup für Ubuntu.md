## WSL Updaten

Zunächst sollten wir das Windows-Subsystem for Linux auf den aktuellsten Stand bringen.

```powershell
wsl --update
```

## WSL Installation

Anschließend können wir Ubuntu installieren:

```powershell
wsl --install
```

Wenn die Installation abgeschlossen ist wird Ubuntu vermutlich automatisch starten und euch nach einem Unix-Usernamen und Unix-Passwort fragen. Hier könnt ihr vergeben was ihr möchtet.

## WSL starten

Nun kann Ubuntu direkt über PowerShell gestartet werden.

```powershell
wsl
```

Weitere Informationen zu WSL findet ihr hier:

[Installieren von WSL | Microsoft Learn](https://learn.microsoft.com/de-de/windows/wsl/install)

Unter Windows 11 ist WSL2 standard.