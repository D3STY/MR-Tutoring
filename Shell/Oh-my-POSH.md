
Öffne dein PowerShell bzw. Windows-Terminal und führe den folgenden Befehl aus:

```powershell
winget install JanDeDobbeleer.OhMyPosh -s winget
```

Dies installiert ein paar Dinge:

- `oh-my-posh.exe` - Windows-Executable
- `themes` - Die neuesten Oh My Posh [Themes](https://ohmyposh.dev/docs/themes)

Um den `PATH` neu zu laden, wird ein Neustart deines Terminals empfohlen.

### ANTIVIRUS SOFTWARE

Aufgrund häufiger Updates von Oh My Posh kennzeichnen Antivirus-Software es gelegentlich als gefährlich (falsch positiv). Um sicherzustellen, dass Oh My Posh nicht blockiert wird, kannst du es entweder bei deiner bevorzugten Antivirus-Software als falsch positiv melden (z. B. [Report a false positive/negative to Microsoft for analysis](https://docs.microsoft.com/en-us/microsoft-365/security/defender/m365d-autoir-report-false-positives-negatives#report-a-false-positivenegative-to-microsoft-for-analysis)) oder eine Ausnahme dafür erstellen. Ausnahmen sollten mit dem vollständigen Pfad zur ausführbaren Datei hinzugefügt werden, den du mit dem folgenden Befehl aus einer PowerShell-Eingabeaufforderung erhalten kannst:

```powershell
(Get-Command oh-my-posh).Source
```

## Weiter

Jetzt, da Oh My Posh installiert ist, kannst du deine Terminal- und Shell-Konfiguration anpassen, um die Eingabeaufforderung genau so aussehen zu lassen, wie du es möchtest.

- Installiere eine [Schriftart](https://ohmyposh.dev/docs/installation/fonts)
- Konfiguriere dein Terminal/Editor, um die installierte Schriftart zu verwenden
- Konfiguriere deine Shell, um Oh My Posh zu verwenden ([https://ohmyposh.dev/docs/installation/prompt](https://ohmyposh.dev/docs/installation/prompt))
- (optional) Konfiguriere ein Theme oder eine angepasste Eingabeaufforderungskonfiguration ([https://ohmyposh.dev/docs/installation/customize](https://ohmyposh.dev/docs/installation/customize))

## Update

Öffne eine PowerShell-Eingabeaufforderung und führe den folgenden Befehl aus:

```powershell
winget upgrade JanDeDobbeleer.OhMyPosh -s winget
```

## Standard-Themes

Du findest die Themes im Ordner, der durch die Umgebungsvariable `POSH_THEMES_PATH` angegeben wird. Du kannst beispielsweise `oh-my-posh init pwsh --config "$env:POSH_THEMES_PATH\\\\\\\\jandedobbeleer.omp.json"` verwenden, um die Eingabeaufforderungsinitialisierung in PowerShell durchzuführen.

Oh My Posh wird mit vielen Themes out-of-the-box geliefert. Nachfolgend findet ihr einige häufigsten Themes. Die verfügbaren Themes findet ihr in der Dokumentation von oh-my-posh:

[Themes | Oh My Posh](https://ohmyposh.dev/docs/themes)

Ihr könnt die Themes jedoch auch direkt im Terminal angezeigt bekommen.

```powershell
Get-PoshThemes
```

Die Ansicht im Terminal ist jedoch etwas unübersichtlich.