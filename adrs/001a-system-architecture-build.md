# [ADR](./README.md) › Verteilter Systemaufbau
<table>
<tr>
<th>status</th>
<td>proposed</td><!-- {proposed / rejected / accepted / deprecated / … / superseded by ADR-0005 <0005-example.md>} -->
</tr>
<tr>
<th>date</th>
<td>2023-04-XX</td><!-- YYYY-MM-DD, when the decision was last updated -->
</tr>
<tr>
<th>deciders</th>
<td>Finn Gedrath, Leonard Pelzer</td><!-- list everyone involved in the decision -->
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

Wir müssen uns für eine Architektur entscheiden, um unser neues System zu implementieren. Wir stehen vor der Entscheidung, ob wir eine monolithische Architektur oder eine verteilte Architektur verwenden sollen.


<!-- Dies ist ein optionales Element. Sie können es gerne entfernen.
## Entscheidungstreiber

* {Entscheidungstreiber 1, z.B. eine Kraft, ein Anliegen, ...}
* {Entscheidungstreiber 2, z.B. eine Kraft, die Bedenken hat, ...}

-->

## In Betracht gezogene Optionen

* monolythisch
* verteilt


## Ergebnis der Entscheidung

Gewählte Option: "verteilte", weil \
hierdurch System-Komponenten unabhängig voneinander im Team entwickelt werden können.

![System Architecture](./001-system-architecture.jpg)

<!-- Dies ist ein optionales Element. Sie können es gerne entfernen. -->
### Consequences

* 🟢 Gut, weil parallelisiert im Team gearbeitet werden kann. 
* 🔴 Schlecht, weil Komplexität der System-Architektur in ihren Kommunikationswegen steigt. 

<!-- Dies ist ein optionales Element. Sie können es gerne entfernen. -->
## Pro und Kontra der Optionen

### monolytisch

* 🟢 Gut, denn Komplexität der allgemeinen Infrastuktur wird reduiziert.
* 🔴 Schlecht, weil die Komplexität des Codes steigen kann.
* 🔴 Schlecht, weil keine Last-Verteilung auf einzelne Komponenten stattfinden kann.


### verteilt

* 🟢 Gut, denn System lässt sich besser verteilen, da einzelne System-Komponenten dubliziert werden können.
* 🟢 Gut, weil die einzelnen Komponenten in sich geschlossener und parallel entwickelt werden können.
* 🟡 Neutral, weil Technologie-Entscheidungen spezifisch auf den Anwendungsfall pro Microservice einzeln getroffen werden können.
* 🔴 Schlecht, weil ein höherer Wartungsaufwand entsteht.
* 🔴 Schlecht, weil Redundanter Code entstehen kann.