# [ADR](./README.md) › Mixed-Synchrone-Asynchrone Kommunikation

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

Es muss ein Kommunikations-Paradigma für die Komunikation zw. Client und der Micro-Services gewählt werden werden.

<!-- Dies ist ein optionales Element. Sie können es gerne entfernen.
## Entscheidungstreiber

* {Entscheidungstreiber 1, z.B. eine Kraft, ein Anliegen, ...}
* {Entscheidungstreiber 2, z.B. eine Kraft, die Bedenken hat, ...}

-->

## In Betracht gezogene Optionen

* sycnhron
* asynchron
* mixed-synchron-asynchron


## Ergebnis der Entscheidung

Gewählte Option: "mixed-asynchron-synchron", weil das Use Case Argument überwiegt. Die asynchrone Kommunikation soll über Events geschehen. Ein **Fallback** ist eine synchrone Kommunikation mit Polling der Veränderungen im System. 

![System Architecture](./001-system-architecture.jpg)

<!-- Dies ist ein optionales Element. Sie können es gerne entfernen. -->
### Consequences

* 🟢 Gut, weil für bestimmte Use Cases Echtzeit-Kommunikation für eine Reaktion auf Events vorhanden sein muss. Mit einem mixed-Ansatz kann beides abgedeckt werden.
* 🔴 Schlecht, weil die Komplexität des Systems erhöht wird, da beide Paradigmen vom Team umgesetzt werden müssen.

<!-- Dies ist ein optionales Element. Fühlen Sie sich frei, es zu entfernen. -->
## Validierung

Die Architektur soll zeitnah im Projekt-Verlauf für einen exemplarischen Use Case umgesetzt werden, um deren Auswirkungen messen zu können und das Wissen im Team zu verteilen.