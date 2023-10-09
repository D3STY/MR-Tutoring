
Beim Implementieren von RAID ist es wichtig, die geeignete RAID-Stufe auszuwählen. Die Faktoren, die diese Entscheidung beeinflussen, umfassen das erforderliche Maß an Fehlertoleranz, Lese-/Schreibleistungseigenschaften, erforderliche Kapazität und Kosten.

> Wenn Sie ein RAID-Array erstellen, sollten alle Festplatten normalerweise in Bezug auf Kapazität identisch und idealerweise in Bezug auf Typ und Leistung identisch sein. Wenn die Festplatten unterschiedliche Größen haben, bestimmt die Größe der kleinsten Festplatte im Array die maximale Menge an Speicherplatz, die auf den größeren Laufwerken verwendet werden kann.

## RAID 0 (Striping ohne Parität)

Die Plattenstreifen teilen Daten in Blöcke auf und verteilen die Blöcke in fester Reihenfolge auf allen Festplatten im Array. Dies verbessert die Leistung, da mehrere Festplatten parallel Anfragen bearbeiten können. RAID 0 erfordert mindestens zwei Laufwerke. Die logische Volumengröße ist das Produkt aus den Laufwerken und der kleinsten Kapazität der physischen Festplatte im Array.

RAID 0 bietet jedoch überhaupt keine Redundanz. Wenn eine physische Festplatte im Array ausfällt, wird das gesamte logische Volumen ausfallen, was dazu führt, dass der Computer abstürzt und Daten aus der Sicherung wiederhergestellt werden müssen. Folglich hat RAID 0 nur Spezialanwendungen - in der Regel als eine Art nicht kritischer Cache-Speicher.

![https://s3.amazonaws.com/wmx-api-production/courses/34991/images/1107-1635434338126-raid0.png](https://s3.amazonaws.com/wmx-api-production/courses/34991/images/1107-1635434338126-raid0.png)

_RAID 0 (Striping) - Daten sind über das Array verteilt. (Bild [©123RF.com](http://xn--123rf-bha.com/))_

## RAID 1 (Spiegelung)

RAID 1 ist eine gespiegelte Laufwerkkonfiguration mit zwei Festplatten. Jeder Schreibvorgang wird auf der zweiten Festplatte im Satz dupliziert, was zu einer geringfügigen Leistungseinbuße führt. Ein Lesevorgang kann entweder auf der einen oder der anderen Festplatte erfolgen, was die Leistung etwas verbessert. Diese Strategie ist der einfachste Weg, um eine einzelne Festplatte gegen Ausfälle abzusichern. Wenn eine Festplatte ausfällt, übernimmt die andere. Währenddessen gibt es nur geringe Auswirkungen auf die Leistung, sodass die Verfügbarkeit gut bleibt, aber die ausgefallene Festplatte sollte so schnell wie möglich ersetzt werden, da keine Redundanz mehr vorhanden ist. Wenn die Festplatte ersetzt wird, muss sie mit Daten von der anderen Festplatte befüllt werden. Die Leistung während des Wiederaufbaus ist reduziert, obwohl RAID 1 in dieser Hinsicht besser als andere Stufen ist und der Wiederaufbauprozess im Allgemeinen kürzer ist als bei der auf Parität basierenden RAID.

![https://s3.amazonaws.com/wmx-api-production/courses/34991/images/478-1635434402022-raid1.png](https://s3.amazonaws.com/wmx-api-production/courses/34991/images/478-1635434402022-raid1.png)

_RAID 1 (Spiegelung) - Daten werden gleichzeitig auf beide Festplatten geschrieben._

In Bezug auf die Kosten pro Gigabyte ist die Festplattenspiegelung teurer als andere Formen der Fehlertoleranz, da die Ausnutzung des Festplattenspeichers nur 50% beträgt.