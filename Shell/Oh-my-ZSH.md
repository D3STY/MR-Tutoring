
Oh My Zsh ist ein Open-Source-Framework, das von der Community entwickelt wurde, um die Konfiguration von [zsh](https://www.zsh.org/) zu verwalten.

Man benötigt `zsh`, um Oh My Zsh zu installieren. Führt man `zsh --version` aus, kann man prüfen, ob man es hat:

```bash
$ zsh --version
zsh 5.8 (x86_64-ubuntu-linux-gnu)
```

Wenn man `command not found` sieht, hat man zsh nicht installiert. Siehe [Installing Zsh](https://github.com/ohmyzsh/ohmyzsh/wiki/Installing-ZSH) für Anweisungen. Sobald man zsh hat, kann man Oh My Zsh einfach durch Ausführen eines dieser Befehle installieren:

|Methode|Befehl|
|---|---|
|curl|sh -c "$(curl -fsSL [https://raw.githubusercontent.com/ohmyzsh/ohmyzsh/master/tools/install.sh](https://raw.githubusercontent.com/ohmyzsh/ohmyzsh/master/tools/install.sh))"|
|wget|sh -c "$(wget -O- [https://raw.githubusercontent.com/ohmyzsh/ohmyzsh/master/tools/install.sh](https://raw.githubusercontent.com/ohmyzsh/ohmyzsh/master/tools/install.sh))"|
|fetch|sh -c "$(fetch -o - [https://raw.githubusercontent.com/ohmyzsh/ohmyzsh/master/tools/install.sh](https://raw.githubusercontent.com/ohmyzsh/ohmyzsh/master/tools/install.sh))"|

**HINWEIS: Der Installer wird eine vorhandene `.zshrc`-Datei in `.zshrc.pre-oh-my-zsh` umbenennen.**

Sobald Oh My Zsh installiert ist, kann man eine kurze Zusammenfassung der integrierten Plugins unter [Plugins Overview](https://github.com/ohmyzsh/ohmyzsh/wiki/Plugins-Overview) finden. Man kann auch einen Blick auf Themen und Plugins unter [Themen](https://github.com/ohmyzsh/ohmyzsh/wiki/Themes) und [Plugins](https://github.com/ohmyzsh/ohmyzsh/wiki/Plugins) werfen (lesen Sie zuerst die READMEs!). Wenn man mehr benötigt, kann man sich [externe Themen](https://github.com/ohmyzsh/ohmyzsh/wiki/External-themes) und [externe Plugins](https://github.com/ohmyzsh/ohmyzsh/wiki/External-plugins) ansehen. **Seien Sie vorsichtig, wir überprüfen diese nicht.** Ein [Cheatsheet](https://github.com/ohmyzsh/ohmyzsh/wiki/Cheatsheet) für andere Oh My Zsh-Tricks steht auch zur Verfügung.

Wenn man Probleme hat, kann man die [FAQ](https://github.com/ohmyzsh/ohmyzsh/wiki/FAQ) für häufige Probleme oder die Seite [Troubleshooting](https://github.com/ohmyzsh/ohmyzsh/wiki/Troubleshooting) für Anweisungen zur Fehlerbehebung ansehen. Möchte man etwas an Oh My Zsh ändern, kann man mehr über die [Anpassung](https://github.com/ohmyzsh/ohmyzsh/wiki/Customization) erfahren. Wenn man mehr erfahren möchte, kann man auf der [Ressourcen](https://github.com/ohmyzsh/ohmyzsh/wiki/Resources)-Seite nach weiteren Informationen suchen.