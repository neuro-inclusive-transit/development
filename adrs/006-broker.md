# [ADR](./README.md) › Mosquitto als Broker

<table>
<tr>
<th>status</th>
<td></td><!-- {proposed / rejected / accepted / deprecated / … / superseded by ADR-0005 <0005-example.md>} -->
</tr>
<tr>
<th>date</th>
<td></td><!-- YYYY-MM-DD, when the decision was last updated -->
</tr>
<tr>
<th>deciders</th>
<td>Finn Gedrath</td><!-- list everyone involved in the decision -->
</tr>
<tr>
<th>consulted</th>
<td></td><!-- list everyone whose opinions are sought (typically subject-matter experts); and with whom there is a two-way communication -->
</tr>
<tr>
<th>informed</th>
<td></td><!-- list everyone who is kept up-to-date on progress; and with whom there is a one-way communication -->
</tr>
</table>


## Kontext und Problemstellung

Jeder Microservice benötigt eine Möglichkeit, Nachrichten zu versenden und zu empfangen, um mit den mobilen Endgeräten asynchon kommunizieren zu können. Dafür wird ein Message Broker benötigt. Dieser muss MQTT[^mqtt] unterstützen, um die Kommunikation so leicht (kleine Pakete) und konzeptionell-simpel zu halten.

<!-- Dies ist ein optionales Element. Sie können es gerne entfernen. -->
## Entscheidungstreiber

* Ausführlichkeit der Dokumentation
* Protokoll-Unterstützung

## In Betracht gezogene Optionen

* Mosquitto
* RabbitMQ
* HiveMQ

## Ergebnis der Entscheidung

Gewählte Option: "Mosquitto", weil
von natur aus MQTT unterstützt und vollständig Open-Source ist (Genauer s.u.)

<!-- Dies ist ein optionales Element. Sie können es gerne entfernen. -->
### Consequences

* Gut, weil geringer Einrichtungsaufwand
* Netrual, weil nur MQTT unterstützt wird und ein Wechsel des Protokolls auch ein Wechsel des Brokers bedeutet &rarr; Wechsel des Brokers ist geringer Aufwand, da für Services der spezfische Broker egal ist.

<!-- Dies ist ein optionales Element. Sie können es gerne entfernen. -->
## Pro und Kontra der Optionen

### Mosquitto

- [Projektseite](https://mosquitto.org/)
- [Docker Image](https://hub.docker.com/_/eclipse-mosquitto)


* 🟢 Gut, weil es simpel gehalten ist und für einen Use Case ausgelegt ist
* 🟢 Gut, weil komplett Open Source ist
* 🟡 Neutral, weil nur MQTT unterstützt wird (nur Topic-Pattern)

### RabbitMQ

- [Projektseite](https://www.rabbitmq.com/)
- [Docker Image](https://hub.docker.com/_/rabbitmq)


* 🟢 Gut, weil Broker mehrere Protokolle (darunter: AMQP) gleichzeitig unterstützt (Topic + RPC-Pattern)
* 🟡 Neutral, weil viele Einstellungsmöglichkeiten existieren (&rarr; Komplexität)

### HiveMQ

- [Projektseite](https://www.hivemq.com/)
- [Docker Image](https://hub.docker.com/r/hivemq/hivemq4)


* 🟢 Gut, weil es simpel gehalten ist und für einen Use Case ausgelegt ist
* 🔴 Schlecht, weil viele Funktionen nur gegen Bezahlung verfügbar sind

<!-- Dies ist ein optionales Element. Sie können es gerne entfernen. -->
## Weitere Informationen


[^mqtt]: <https://mqtt.org/>
