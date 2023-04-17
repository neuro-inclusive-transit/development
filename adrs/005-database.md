# [ADR](./README.md) › MongoDB als Datenbank

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

Wir müssen eine Datenbanktechnologie auswählen, um halbstrukturierte Daten aus den Microservices zu speichern.

## In Betracht gezogene Optionen

* MongoDB
* CouchDB
* PostgreSQL

## Ergebnis der Entscheidung

Gewählte Option: "MongoDB", weil es eine offene dokumentenbasierte DB ist.

<!-- Dies ist ein optionales Element. Sie können es gerne entfernen. -->
### Consequences

* Gut, weil Open-Source
* Gut, weil Dokumente es ermöglichen nicht-relationale Daten in einer halb-strukturierten Art zu speichern
* Gut, weil Dokumentation für Driver und Schema gut ist
* ... <!-- Anzahl der Konsequenzen kann variieren -->

<!-- Dies ist ein optionales Element. Sie können es gerne entfernen. -->
## Weitere Informationen

- Mongo DB Driver: https://www.npmjs.com/package/mongodb