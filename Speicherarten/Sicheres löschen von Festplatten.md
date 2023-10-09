
Es kann sein, dass Sie aus irgendeinem Grund Ihre Festplatte (HDD) oder Solid-State-Laufwerk (SSD) vollständig löschen möchten, um sicherzustellen, dass Ihre Daten nicht in die falschen Hände geraten.

![https://darknetlive.com/images/SSD-HDD-739f6db8.jpeg](https://darknetlive.com/images/SSD-HDD-739f6db8.jpeg)

Das Formatieren Ihres Laufwerks löscht alle Dateien, hinterlässt jedoch Spuren der gelöschten Daten. Die gelöschten Daten können daher leicht wiederhergestellt werden.

## **Sicheres löschen Ihrer HDD**

Bei einer HDD wird die Daten auf einer magnetischen Scheibe geschrieben, und das Betriebssystem kann genau erkennen, wo sich die Daten befinden. Das sichere Löschen auf einer HDD kann daher leicht durchgeführt werden, da das Betriebssystem weiß, wo die Daten gelöscht werden sollen.

![https://darknetlive.com/images/HDD-f9943871.jpeg](https://darknetlive.com/images/HDD-f9943871.jpeg)

Der einfachste Weg, um Ihre Daten sicher von einer HDD zu löschen, besteht darin, sie mehrmals zu überschreiben, bis keine Spuren Ihrer Daten mehr vorhanden sind. Hierfür können Sie Tools wie Darik's Boot and Nuke (DBAN) oder ShredOS verwenden.

Da DBAN nicht mehr gepflegt wird, werden wir uns anschauen, wie Sie ShredOS verwenden können.

- Gehen Sie [hier](https://github.com/PartialVolume/shredos.x86_64#shredos-version-v2021082_23_x86-64_034-latest-release), um die ShredOS-Image-Datei herunterzuladen.
- Windows-Benutzer verwenden entweder [Rufus](https://rufus.ie/en/) oder [Etcher](https://etcher.balena.io/), um ShredOS auf Ihren USB-Stick zu schreiben.
- Starten Sie Ihr Gerät neu und booten Sie von Ihrem USB-Stick.
- Befolgen Sie die Bildschirmanweisungen, um Ihr Laufwerk dauerhaft zu löschen.

## **Sicheres löschen Ihrer SSD**

Eine SSD ist in Blöcke unterteilt, die wiederum in Seiten unterteilt sind. Wenn eine Datei gespeichert wird, wird sie auf mehreren Seiten in einem Block geschrieben.

![https://darknetlive.com/images/SDD-adc49bc9.jpeg](https://darknetlive.com/images/SDD-adc49bc9.jpeg)

Das Löschen und Neu Schreiben verschleißt die Blöcke. SSD-Blöcke können nur eine begrenzte Anzahl von Malen gelöscht und neu geschrieben werden, bevor sie verschleißen. Um ihre Lebensdauer zu verlängern, verwenden SSDs eine Technik namens **Wear Leveling** (Verschleißausgleich). Sie stellt sicher, dass jeder Block die gleiche Anzahl von Malen gelöscht und neu geschrieben wird.

Wenn Sie eine Datei von einer SSD löschen, werden die Seiten und der Block, in dem sie gespeichert waren, als ungültig markiert, und das Laufwerk schreibt neue Daten in einen neuen Block. Dies macht es schwierig, Dateien auf einer SSD sicher zu löschen, da nicht garantiert ist, dass das Laufwerk denselben Block überschreiben wird, in dem sich die gelöschte Datei befand.

Alle modernen Betriebssysteme unterstützen standardmäßig einen Befehl namens **Trim Operation**. Der Trim-Befehl informiert den SSD-Controller darüber, dass es Seiten innerhalb von Blöcken gibt, die zur Löschung bereit sind.

Wenn Sie eine Datei löschen, sendet Ihr Betriebssystem einen Trim-Befehl an den SSD-Controller, um ihm mitzuteilen, dass die Seiten, auf denen sich die Datei befindet, zur Löschung bereit sind. Trim macht die Daten auch unlesbar.

Nachdem der SSD-Controller über das Vorhandensein von Daten informiert wurde, die zur Löschung bereit sind, führt er einen Prozess namens **Garbage Collection** (Müllsammlung) durch. Die Müllsammlung durchläuft das Laufwerk und identifiziert den Block mit Seiten, die Trim als zur Löschung markiert hat. Sie kopiert die gültigen Seiten in verschiedene Seiten in einem freien Block und löscht dann den gesamten Quellblock.

Die Müllsammlung löscht Daten von Ihrer SSD dauerhaft.

Die Kombination aus Löschung und Trim macht die gelöschten Dateien sehr schwer wiederherstellbar.

Folgende Methoden werden verwendet, um Daten von SSDs zu löschen:

## Secure Erase

- Es löscht nur die Zuordnungstabelle, die die Daten auf den Speicherblöcken verfolgt. Es löscht die Blöcke nicht.

## Säubern (Sanitize)

- Es löscht die Zuordnungstabelle und löscht alle Blöcke, die beschrieben wurden.

Sie können Ihre SSD auf verschiedene Arten säubern:

- Crypto Scrabble: Führt die Löschung durch, indem der Verschlüsselungsschlüssel von selbstverschlüsselnden SSDs geändert wird. Dadurch werden die Daten unlesbar.
- Blocklöschung: Führt die Löschung von Speicherblöcken durch, um die Daten zu zerstören.
- Überschreiben: Führt die Löschung von Speicherblöcken gefolgt von einer Überschreibung der Blöcke durch.

Die Verwendung von Secure Erase oder Sanitize zerstört Ihre Daten dauerhaft und macht sie nicht wiederherstellbar.

Um Ihre gesamte SSD sicher mit einer der oben genannten Methoden zu löschen, können Sie eines der folgenden Tools verwenden.

## Verwenden Sie Ihr BIOS/UEFI

- Gehen Sie zu den BIOS- oder UEFI-Einstellungen Ihres Geräts und wählen Sie Ihr Laufwerk aus.
- Wenn es die Tools gibt, wählen Sie entweder Secure Erase oder Sanitize aus.
- Befolgen Sie die Anweisungen, um Ihre SSD sicher zu löschen.

## Verwenden Sie Hersteller-Tools

Die meisten seriösen Hersteller bieten Software zum sicheren Löschen ihrer SSDs an.

Die Tools umfassen:

- Intel [Solid-State Drive](https://downloadcenter.intel.com/download/29205/Intel-Solid-State-Drive-Toolbox) Toolbox
- Samsung [Magician](https://semiconductor.samsung.com/consumer-storage/magician/) SSD Tool
- Crucial [SSD Storage](https://www.crucial.com/support/storage-executive) Executive
- Western [Digital SSD Dashboard](https://support-en.wd.com/app/answers/detailweb/a_id/10346)

## **Verwendung von kommerziellen Tools**

Es gibt Drittanbieter-Tools, die Sie verwenden können, um Ihre SSD sicher zu löschen. Diese umfassen:

- PartedMagic. Es kostet $15.
- GParted.

Diese Tools verfügen über eine Benutzeroberfläche, die Sie durch den gesamten Prozess führen wird.

## **Verwendung von hdparm-Dienstprogrammen**

hdparm bietet Linux-Befehle, die Sie verwenden können, um Ihre SSD sicher zu löschen. Führen Sie den folgenden Befehl aus, um zu überprüfen, ob Ihr SATA-Laufwerk die Säuberung unterstützt:

`hdparm --sanitize-status /dev/sdx`

Um die Säuberung mit Crypto Scramble auf einer selbstverschlüsselnden SSD durchzuführen, verwenden Sie:

`hdparm --yes-i-know-what-i-am-doing --sanitize-crypto-scramble /dev/sdX`

Um die Säuberung mit Blocklöschung auf einer nicht selbstverschlüsselnden SATA-SSD durchzuführen, verwenden Sie:

`hdparm --yes-i-know-what-i-am-doing --sanitize-block-erase /dev/sdX`

Für maximale Sicherheit, abhängig von Ihrem Bedrohungsmodell, können Sie das Laufwerk nach dem sicheren Löschen Ihrer Daten zerstören und seine Teile an verschiedenen Orten entsorgen.