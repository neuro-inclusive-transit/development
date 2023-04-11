# [ADR](./README.md) › {Kurztitel des gelösten Problems und der Lösung}

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
* 
* ... <!-- Anzahl der Treiber kann variieren -->

## In Betracht gezogene Optionen

* Mosquitto
* RabbitMQ
* HiveMQ

## Ergebnis der Entscheidung

Gewählte Option: "{Titel der Option 1}", weil
{Begründung. z.B., einzige Option, die das K.O.-Kriterium Entscheidungstreiber erfüllt | die Kraft {Kraft} auflöst | ... | am besten ausfällt (siehe unten)}.

<!-- Dies ist ein optionales Element. Sie können es gerne entfernen. -->
### Consequences

* Gut, weil {positive Folge, z.B. Verbesserung einer oder mehrerer gewünschter Eigenschaften, ...}
* Schlecht, weil {negative Konsequenz, z.B. Beeinträchtigung einer oder mehrerer gewünschter Eigenschaften, ...}
* ... <!-- Anzahl der Konsequenzen kann variieren -->

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

{Vielleicht möchten Sie hier zusätzliche Beweise/Vertrauenswürdigkeit für das Entscheidungsergebnis angeben und/oder die Einigung des Teams auf die Entscheidung dokumentieren und/oder definieren, wann und wie diese Entscheidung umgesetzt werden sollte und ob/ wann sie erneut überprüft werden sollte und/oder wie die Entscheidung validiert wird. Hier können auch Links zu anderen Entscheidungen und Ressourcen erscheinen.}


[mqtt]: <https://mqtt.org/>