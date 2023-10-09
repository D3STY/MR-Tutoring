
RAID 5 und RAID 10 haben Leistungs-, Datenträgernutzungs- und Fehlertoleranzmerkmale, die sie zu besseren Optionen als grundlegende Spiegelung machen können.

## **RAID 5 (Striping mit verteilter Parität)**

**RAID 5** verwendet Striping (wie RAID 0), jedoch mit verteilter Parität. Verteilte Parität bedeutet, dass Fehlerkorrekturinformationen über alle Festplatten im Array verteilt werden. Die Daten und Paritätsinformationen werden so verwaltet, dass sie immer auf verschiedenen Festplatten liegen. Wenn eine Festplatte ausfällt, ist genügend Information auf den verbleibenden Festplatten verteilt, um die Daten rekonstruieren zu können. Streifen-Sets mit Parität bieten die beste Leistung für Lesevorgänge. Wenn jedoch eine Festplatte ausgefallen ist, wird die Leseleistung durch die Notwendigkeit, die Daten mithilfe der Paritätsinformationen wiederherzustellen, beeinträchtigt. Auch alle normalen Schreibvorgänge leiden unter reduzierter Leistung aufgrund der Paritätsberechnung.

![https://s3.amazonaws.com/wmx-api-production/courses/34991/images/3738-1635434458026-raid5.png](https://s3.amazonaws.com/wmx-api-production/courses/34991/images/3738-1635434458026-raid5.png)

_RAID 5 (Striping mit Parität)._

RAID 5 erfordert mindestens drei Laufwerke, kann jedoch mit mehreren konfiguriert werden. Dies ermöglicht eine größere Flexibilität bei der Bestimmung der Gesamtkapazität des Arrays als bei RAID 1. Eine "harte" maximale Anzahl von Geräten wird vom Controller oder der Betriebssystemunterstützung festgelegt, aber die Anzahl der verwendeten Laufwerke wird eher durch praktische Überlegungen wie Kosten und Risiken bestimmt. Das Hinzufügen von Laufwerken erhöht die Ausfallwahrscheinlichkeit. Wenn mehr als eine Festplatte ausfällt, ist das Volume nicht verfügbar.

Das Maß an Fehlertoleranz und verfügbarer Festplattenspeicher ist umgekehrt proportional. Wenn Sie Laufwerke zum Satz hinzufügen, nimmt die Fehlertoleranz ab, aber der nutzbare Festplattenspeicher nimmt zu. Wenn Sie einen RAID 5-Satz mit drei Laufwerken konfigurieren, wird ein Drittel jedes Laufwerks für die Parität reserviert. Wenn Sie vier verwenden, wird ein Viertel auf jedem Laufwerk reserviert. Mit einer Konfiguration von drei 80-GB-Laufwerken hätten Sie ein nutzbares Volumen von 160 GB.

## **RAID 10 (Streifen von Spiegeln)**

Eine verschachtelte RAID-Konfiguration kombiniert Funktionen von zwei grundlegenden RAID-Levels. **RAID 10** ist ein logisches gestreiftes Volume (RAID 0), das mit zwei gespiegelten Arrays (RAID 1) konfiguriert ist. Diese Konfiguration bietet eine ausgezeichnete Fehlertoleranz, da eine Festplatte in jedem Spiegel ausfallen kann und das Volume dennoch verfügbar ist.

![https://s3.amazonaws.com/wmx-api-production/courses/34991/images/41-1635434499577-raid10.png](https://s3.amazonaws.com/wmx-api-production/courses/34991/images/41-1635434499577-raid10.png)

_RAID 10 - Jede Festplatte in jedem der Teilmengen kann ausfallen, ohne das Hauptvolume herunterzufahren._

Diese Konfiguration erfordert mindestens vier Laufwerke, und es muss eine gerade Anzahl von Laufwerken vorhanden sein. Es hat die gleichen 50% Festplatten-Overhead wie Spiegelung.