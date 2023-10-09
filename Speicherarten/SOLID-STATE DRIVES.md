
Eine **Solid-State-Drive (SSD)** verwendet die Flash-Speichertechnologie zur Implementierung eines dauerhaften Massenspeichers. Flash-Speicher ist im Vergleich zu den mechanischen Komponenten, die in Festplattenlaufwerken verwendet werden, insbesondere in Bezug auf die Leseleistung, wesentlich schneller. Das Risiko eines vollständigen Ausfalls aufgrund mechanischer Schocks und Abnutzung ist im Allgemeinen geringer. Die Kosten pro Gigabyte sind in den letzten Jahren rapide gesunken.

![https://s3.amazonaws.com/wmx-api-production/courses/34991/images/7952-1635432883380-solid_state_drive.png](https://s3.amazonaws.com/wmx-api-production/courses/34991/images/7952-1635432883380-solid_state_drive.png)

_Eine Solid-State-Drive im Formfaktor 2,5 Zoll mit SATA-Schnittstelle. (Bild [©123RF.com](http://xn--123rf-bha.com/))_

> SSDs übertreffen in der Regel HDDs, aber es gibt Situationen, in denen sie schlechter abschneiden können als HDDs (beispielsweise bei der Verwendung von mehrere Gigabyte großen Dateigrößen).

Flash-Chips sind auch anfällig für eine Art von Degradation im Laufe vieler Schreibvorgänge. Die Treiber-Firmware und das Betriebssystem verwenden Verschleißnivellierungsroutinen, die das Schreiben auf alle Blöcke einer SSD gleichmäßig verteilen, um die Lebensdauer des Geräts zu optimieren.

> Der NAND-Flash-Speicher (NOT AND), der in SSDs verwendet wird, wird in verschiedenen Typen geliefert. Einzelschichtzellen (SLC) sind zuverlässiger und teurer als Mehrschichtzellentypen.

Bei einem typischen modernen Desktop-PC kann eine SSD entweder als einzige interne Festplatte des Computers oder als Boot-Laufwerk für die Verwendung mit einer zusätzlichen Festplatte installiert werden. Im zweiten Szenario würde die SSD für die Installation des Betriebssystems und der Softwareanwendungen verwendet werden, während die HDD für Benutzerdatendateien verwendet würde.

In Bezug auf die **Kommunikationsschnittstelle** kann eine SSD in einem 2,5-Zoll-Gehäuse verpackt und an einen **SATA**-Anschluss angeschlossen werden, wobei die normalen SATA-Daten- und Stromanschlüsse verwendet werden. Alternativ ermöglicht der **mSATA**-Formfaktor, dass eine SSD als Adapterkarte verpackt wird, die in einen kombinierten Daten- und Stromanschluss auf dem Motherboard eingesteckt wird. Bei beiden Formfaktoren ist der Hauptnachteil, dass die 600 MBps SATA-Schnittstelle zu einem Engpass für die leistungsstärksten SSDs werden kann, die Übertragungsraten von bis zu 6,7 GB/s erreichen können.

![https://s3.amazonaws.com/wmx-api-production/courses/34991/images/8849-1637339413580-msata_ssd.png](https://s3.amazonaws.com/wmx-api-production/courses/34991/images/8849-1637339413580-msata_ssd.png)

_mSATA SSD-Formfaktor._

Moderne SSDs verwenden daher oft direkt den **PCI Express (PCIe)**-Bus. Während SATA die logische Schnittstelle Advanced Host Controller Interface (AHCI) zur Kommunikation mit dem Bus verwendet, verwenden PCIe-basierte SSDs die Non-Volatile Memory Host Controller Interface Specification (NVMHCI) oder **NVM Express (NVMe)**.

Eine NVMe-SSD kann entweder als Erweiterungskarte in einen PCIe-Steckplatz verpackt oder an einen **M.2**-Steckplatz angeschlossen werden. Der M.2-Adapterkartenformfaktor ist wesentlich kleiner als ein PCIe-Adapter und horizontal ausgerichtet, so dass die Schnittstelle auch auf Laptops sowie PC-Motherboards verwendet wird. M.2 liefert Strom über den Bus, so dass kein separater Stromkabel erforderlich ist. M.2-Adapter können unterschiedliche Breiten und Längen haben, so dass Sie prüfen sollten, ob ein bestimmter Adapter auf Ihrem Motherboard passt. Aufkleber geben die unterstützten Adaptergrößen an. Ein M.2-2280-Adapter ist beispielsweise 22 mm breit und 80 mm lang.

> M.2 ist ein physischer Formfaktor. Sie können M.2-SSDs erwerben, die den SATA/AHCI-Bus verwenden. Diese werden in der Regel nicht so gut wie NVMe-basierte M.2-SSDs funktionieren. Auf dem Motherboard kann ein M.2-Sockel beide Laufwerkstypen oder nur einen unterstützen; überprüfen Sie die Dokumentation. SATA-Schnittstellen-SSDs sind in der Regel B-tasten, 2-Lane-PCIe-SSDs sind in der Regel B/M-tasten und 4-Lane-SSDs sind in der Regel M-tasten.

_SSDs sind anfällig für elektrostatische Entladungen (ESD). Beachten Sie immer die Anti-ESD-Vorsichtsmaßnahmen beim Umgang und der Lagerung dieser Geräte._