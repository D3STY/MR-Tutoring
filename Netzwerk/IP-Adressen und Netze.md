
IP-Adressen stellen ein Adressierungssystem zur Verwaltung von Netzwerkidentitäten bereit. Das Internetprotokoll Version 4 wurde 1981 definiert. Die Adressen bestehen aus 32 Bits, was etwa 4,3 Milliarden Adressen ermöglicht. Menschen arbeiten normalerweise mit IP-Adressen in Dezimalform, wie z. B. 192.168.2.200, während Netzwerkgeräte die Adresse in binärer Form verwenden.

IPv4-Adressen sind mindestens in zwei Teile unterteilt: einen Netzwerkidentifikator und einen Hostidentifikator. Der Netzwerkidentifikator bestimmt zu welchem Netzwerksegment der Host gehört, und der Hostidentifikator identifiziert diesen Host eindeutig innerhalb des Segments. Da die Netzwerk-ID unterschiedliche Bits innerhalb der Adresse verwenden kann, wird ein zweiter numerischer Wert verwendet, um anzuzeigen, welcher Teil der IP-Adresse die Netzwerk-ID und welcher Teil die Host-ID ist. Dieser Wert wird als Subnetzmaske bezeichnet. Es ist wichtig, die Rolle der Subnetzmaske zu verstehen. Sie zeigt an, wo in der IP-Adresse die Trennung zwischen der Netzwerk-ID und der Host-ID liegt.

## IPv4-Adressklassen

Die etwa 4,3 Milliarden IPv4-Adressen sind in fünf Klassen unterteilt. Diese Klassen bieten einen Rahmen für die mögliche Segmentierung von Netzwerken. Jede Klasse gibt eine bestimmte Anzahl von Netzwerken an, sowie eine Anzahl von Hosts, die in jedem Netzwerk verfügbar sind. Bei den ersten drei Klassen erfolgt die Trennung zwischen der Netzwerk-ID und der Host-ID an einem der Punkte. Netzwerkprofis müssen in der Lage sein, alle fünf Klassen anhand des Werts des ersten Oktetts zu erkennen und die Standard-Subnetzmaske für jede Klasse zu kennen.

Die etwa 4,3 Milliarden IPv4-Adressen sind in folgende fünf Klassen unterteilt:

| Klasse    | Startadresse   | Endadresse     | Startadresse Reserviert | Endadresse Reserviert | Standard-Subnetzmaske | Anzahl von Netzwerken | Hosts pro Netzwerk |
| --------- | -------------- | -------------- | ----------------------- | ---------------------- | --------------------- | --------------------- | ------------------- |
| Klasse A  | 0.0.0.0        | 127.0.0.0      | 10.0.0.0                | 10.255.255.255         | 255.0.0.0 oder /8     | 126                   | 16,777,214          |
| Klasse B  | 128.0.0.0      | 191.255.0.0    | 172.16.0.0              | 172.31.255.255         | 255.255.0.0 oder /16  | 16,384                | 65,534              |
| Klasse C  | 192.0.0.0      | 223.255.255.0  | 192.168.0.0             | 192.168.255.255        | 255.255.255.0 oder /24 | 2,097,152             | 254                |
| Klasse D  | 224.0.0.0      | 239.255.255.255|                         |                        | n/v                   | n/v                   | n/v                |
| Klasse E  | 240.0.0.0      | 255.255.255.255|                         |                        | n/v                   | n/v                   | n/v                |


## Reservierte Bereiche

Um im Internet zu kommunizieren, muss ein Host mit einer eindeutigen öffentlichen IP-Adresse konfiguriert sein. Öffentliche Adressen werden von Internetdienstanbietern (ISPs) an Kunden-Netzwerke vergeben. Nur wenige Unternehmen können jedoch ausreichend öffentliche IPv4-Adressen erhalten, um all ihre Computer für die Kommunikation über das Internet zu nutzen. Es gibt verschiedene Mechanismen, um den Mangel an verfügbaren öffentlichen Adressen zu bewältigen.

Neben dem Wissen über die fünf IP-Adressklassen gibt es mehrere andere IP-Adressen oder Adressbereiche, die wichtig sind. Aufgrund der Erschöpfung der IPv4-Adressen gibt es drei IP-Adressbereiche, die nur für die interne Verwendung reserviert sind. Diese werden fast immer in internen Geschäfts- und Heimnetzwerken verwendet.

Das IPv4-Adressschema definiert bestimmte Bereiche als reserviert für die private Adressierung, oft als "RFC 1918"-Adressen bezeichnet, nach dem Dokument, in dem sie veröffentlicht wurden. Hosts mit IP-Adressen aus diesen Bereichen dürfen den Datenverkehr nicht über das öffentliche Internet leiten. Die Verwendung dieser Adressen ist auf private LANs beschränkt. Es gibt drei private Adressbereiche:

- Klasse A **reserviert**: 10.0.0.0–10.255.255.255
- Klasse B **reserviert**: 172.16.0.0–172.31.255.255
- Klasse C **reserviert**: 192.168.0.0–192.168.255.255

## Adressklassen und Standard-Subnetzmasken

Die Adressklassen (A, B und C) leiten sich von der frühesten Form von IP ab. Als IP erstmals definiert wurde, enthielt es nicht das Konzept von Subnetzmasken. Hosts identifizierten die Netzwerk-ID nur anhand der Adressklasse. Die Subnetzmasken, die genau mit den Oktettgrenzen übereinstimmen, spiegeln diese Funktionalität wider. Sie werden oft als "Standardmasken" bezeichnet:

|Klasse|Gepunktete Dezimalmaske|Netzwerkpräfix|Binärmaske|
|---|---|---|---|
|A|255.0.0.0|/8|11111111 00000000 00000000 00000000|
|B|255.255.0.0|/16|11111111 11111111 00000000 00000000|
|C|255.255.255.0|/24|11111111 11111111 11111111 00000000|

## Internetzugang mit privater Adressierung

Da ein mit einer privaten Adresse konfigurierter Host nicht direkt auf das Internet zugreifen kann, muss ein Mechanismus verwendet werden, um das Weiterleiten von Paketen zu ermöglichen. Der Internetzugang für Hosts, die ein privates Adressierungsschema verwenden, kann auf zwei Arten erleichtert werden:

Über einen Router, der mit einer einzelnen oder einer Blockgruppe von gültigen öffentlichen Adressen konfiguriert ist. Der Router verwendet die Netzwerkadressübersetzung (NAT), um zwischen den privaten und öffentlichen Adressen zu konvertieren. Über einen Proxy-Server, der Anfragen nach Internetressourcen im Namen von Clients bearbeitet.

## Adresskonfiguration

Es gibt zwei Netzwerkdienste, die üblicherweise in die Konfiguration von TCP/IP-Netzwerken einbezogen werden.

Menschen haben Schwierigkeiten mit langen Zeichenketten von Zahlen wie IP-Adressen zu arbeiten. Der Domain Name System (DNS) Dienst bietet Namensauflösung, eine Möglichkeit, einen leicht zu merkenden Hostnamen mit einer schwer zu merkenden IP-Adresse in Beziehung zu setzen. DNS wird als eine Datenbank implementiert, die auf einem oder mehreren Servern gehostet wird. Die Datenbank kann nur die Namen und IPs von Knoten in Ihrem eigenen Netzwerk enthalten oder Teil der größeren Internet-DNS-Infrastruktur sein.

Alle Knoten im Netzwerk müssen mit einer eindeutigen IP-Adresse und anderen entsprechenden Informationen konfiguriert sein. Es gibt zwei Möglichkeiten, diese Konfiguration durchzuführen - statisch oder dynamisch. Statische Konfiguration ist normalerweise für Server und Netzwerkgeräte geeignet, während die dynamische Konfiguration in der Regel bei Endbenutzer-Arbeitsstationen verwendet wird. Der Dienst "Dynamic Host Configuration Protocol" (DHCP) bietet dynamische Konfiguration an.