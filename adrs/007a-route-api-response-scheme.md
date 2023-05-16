# [ADR](./README.md) › RouteAPI Response Scheme

<table>
<tr>
<th>status</th>
<td>accepted</td><!-- {proposed / rejected / accepted / deprecated / … / superseded by ADR-0005 <0005-example.md>} -->
</tr>
<tr>
<th>date</th>
<td>2023-05-16</td><!-- YYYY-MM-DD, when the decision was last updated -->
</tr>
<tr>
<th>deciders</th>
<td>Leonard Pelzer</td><!-- list everyone involved in the decision -->
</tr>
<tr>
<th>consulted</th>
<td>Lining Bao</td><!-- list everyone whose opinions are sought (typically subject-matter experts); and with whom there is a two-way communication -->
</tr>
<tr>
<th>informed</th>
<td></td><!-- list everyone who is kept up-to-date on progress; and with whom there is a one-way communication -->
</tr>
</table>


## Kontext und Problemstellung

Für die Response der Route-API muss ein Schema definiert werden, welches die Datenstruktur der Response beschreibt. In dieses Schema müssen die Routen-Daten der Here Transit-API und evtl. Probleme/Herausforderungen (welche die Disturbance-API liefert) integriert werden.

<!-- Dies ist ein optionales Element. Sie können es gerne entfernen. -->
## Entscheidungstreiber

* Alle Informationen müssen in einem Schema zusammengefasst werden.
* Das Schema muss erweitert werden können

## In Betracht gezogene Optionen

* Eigenes Schema aufbauen
* Das bestehende Schema der Here Transit-API verwenden und erweitern

## Ergebnis der Entscheidung

Gewählte Option: "Das bestehende Schema der Here Transit-API verwenden und erweitern", weil dieses Schema eine bereits sehr gute Struktur aufweist und eine Vielzahl an Daten in einem Schema zusammenfasst.
Die Here-Transit-API unterteilt eine Route in feste Abschnitte (Sections). Zu diesen Sections sind nun alle weiteren wichtigen Informationen zugeordnet. 

<!-- Dies ist ein optionales Element. Sie können es gerne entfernen. -->
### Consequences

* 🟢 Gut, weil das Schema nicht aufwendig neu definiert werden muss.
* 🟢 Gut, weil das Schema beliebig erweitert werden kann.
<!-- Anzahl der Konsequenzen kann variieren -->

<!-- Dies ist ein optionales Element. Fühlen Sie sich frei, es zu entfernen. -->

## Weitere Informationen

- Eine Darstellung des Schemas der Here-Transit-API befindet sich [hier](https://www.figma.com/file/YXBqSf42uMzAjgqV4KJmEO/P2-%E2%80%93-Projekt-Board?type=whiteboard&node-id=492-1568&t=YyKORHCxX52Qc8wH-4).