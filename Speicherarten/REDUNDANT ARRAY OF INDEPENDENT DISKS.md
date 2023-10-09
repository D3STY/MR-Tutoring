
Ob es sich um die Systemdateien handelt, die zum Ausführen des Betriebssystems benötigt werden, oder um von Benutzern generierte Daten, eine HDD oder SSD speichert wichtige Daten. Wenn ein Startlaufwerk ausfällt, stürzt das System ab. Wenn ein Datenträger ausfällt, verlieren Benutzer den Zugriff auf Dateien, und es kann zu dauerhaftem Datenverlust kommen, wenn diese Dateien nicht gesichert wurden. Um diese Risiken zu minimieren, können die Disks, die dem Massenspeichersystem zugrunde liegen, als redundantes Array unabhängiger Festplatten (RAID) bereitgestellt werden. Redundanz opfert einige Festplattenkapazität, bietet jedoch eine Fehlertoleranz. Für das Betriebssystem erscheint das RAID-Array als einzelne Speicherressource oder Volume und kann wie jeder andere Laufwerk partitioniert und formatiert werden.

> RAID kann auch als "Redundant Array of Inexpensive Disks" bezeichnet werden, und das "D" kann auch für "Devices" stehen.

Ein RAID-Level stellt eine Laufwerkskonfiguration mit einer bestimmten Art von Fehlertoleranz dar. Grundlegende RAID-Levels sind von 0 bis 6 durchnummeriert. Es gibt auch geschachtelte RAID-Lösungen wie RAID 10 (RAID 1 + RAID 0).

RAID kann unter Verwendung von Funktionen des Betriebssystems implementiert werden, die als Software-RAID bezeichnet werden. Hardware-RAID verwendet einen dedizierten Controller, der als Adapterkarte installiert ist. Die RAID-Festplatten sind an SATA-Ports auf der RAID-Controller-Adapterkarte angeschlossen, anstatt an das Motherboard.

> Als weitere Option implementieren einige Motherboards integrierte RAID-Funktionalität als Teil des Chipsatzes.

Hardwarelösungen unterscheiden sich hauptsächlich durch ihre Unterstützung für eine Reihe von RAID-Levels. Einstiegscontroller unterstützen möglicherweise nur RAID 0 oder RAID 1, während mittelständische Controller Unterstützung für RAID 5 und RAID 10 hinzufügen können. Darüber hinaus kann Hardware-RAID oft eine beschädigte Festplatte im laufenden Betrieb auswechseln. Hot Swap bedeutet, dass das fehlerhafte Gerät ersetzt werden kann, ohne das Betriebssystem herunterzufahren.

_Configuring a volume using RAID controller firmware._