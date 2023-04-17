# [ADR](./README.md) › Deno.js als Backend-Technologie

<table>
<tr>
<th>status</th>
<td>proposed</td><!-- {proposed / rejected / accepted / deprecated / … / superseded by ADR-0005 <0005-example.md>} -->
</tr>
<tr>
<th>date</th>
<td></td><!-- YYYY-MM-DD, when the decision was last updated -->
</tr>
<tr>
<th>deciders</th>
<td>Finn Gedrath, Patrick Lang</td><!-- list everyone involved in the decision -->
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

In der System-Architektur (siehe [ADR-001](001-system-architecture.md)) werden mehrere Backend-Services definiert, welche die Daten für die verschiedenen Clients bereitstellen. Diese müssen eine API zur Verfügung stellen, mit denen über HTTP kommuniziert werden kann. Des weiteren müssen diese Services eine Datenbank zur Persistierung der Daten bereitstellen können und untereinander asynchron kommunizieren können.

<!-- Dies ist ein optionales Element. Sie können es gerne entfernen. -->
## Entscheidungstreiber

* Bestehendes Wissen im Team
* Dokumentation
* Community

## In Betracht gezogene Optionen

* Kotlin
* Node.js
* Deno.js
* Firebase

## Ergebnis der Entscheidung

Gewählte Option: "Deno.js", weil standardisierte Browser-APIs unterstützt und TypeScript als Standard verwendet wird. Desweiteren hat es eine gute Wissensbasis im Team und kann (in großen Teilen) die gleichen Frameworks/Libraries wie Node.js verwenden.

<!-- Dies ist ein optionales Element. Sie können es gerne entfernen. -->
### Consequences

* 🟢 Gut, weil besser lesbarer Code durch die Verwendung von TypeScript
* 🟢 Gut, weil Wissen und Doku von Browser-APIs weiterverwendet werden kann
* 🔴 Risikohaft, weil nicht zwingend für alle Probleme eine Bibliothek existiert, die von Deno unterstützt wird
* 🟢 Gut, weil ein Wechsel zu Node.js im Nachhinein möglich ist und Code weiterverwendet werden kann

<!-- Dies ist ein optionales Element. Sie können es gerne entfernen. -->
## Pro und Kontra der Optionen

### Kotlin

<https://kotlinlang.org/docs/server-overview.html>

* 🟢 Gut, weil es eine typisierende und moderne Sprache ist, die auf Java basiert. Es besteht eine geringe Gefahrt Boilerplate-Code.
* 🟢 Gut, weil syntaktisches Wissen von Java (+Kotlin) im Team vorhanden ist
* 🟡 Neutral, weil es existieren Frameworks und Libraries, die auf Kotlin basieren. Das Wissen über diese ist nicht im Team vorhanden.
* 🔴 Schlecht, weil geringe bis keine bestehende Wissensgrundlage für eine Server-Seitige Entwicklung im Team vorhanden ist

### Node.js

<https://nodejs.org/en/about>

* 🟢 Gut, da es eine große Community und eine große Anzahl an entwickelten Packages und Frameworks gibt
* 🟢 Gut, weil es eine große Anzahl an bestehenden Projekten gibt, die auf Node.js basieren
* 🟡 Neutral, da Unterschiede zwischen Browser- und Server-Entwicklung bestehen
* 🟡 Neutral, da die Einrichtung von TypeScript manuell erfolgen muss
* 🔴 Schlecht, weil `node_modules`-Ordner mit vielen Abhängigkeiten und Dateien erstellt werden, die nicht benötigt werden

### Deno.js

<https://deno.land/>

* 🟢 Gut, weil eine Laufzeit-Umgebung für JavaScript/TypesScript ist, und das Wissen von JavaScript/TypeScript im Team vorhanden ist
* 🟢 Gut, weil Nutzung von Browser-APIs wodurch viele Funktionen bereits implementiert sind und nicht durch externe Abhängigkeiten gelöst werden müssen
* 🟢 Gut, weil es ausführliche Dokumentationen von Deno und vom MDN gibt
* 🟢 Gut, weil standarmäßig mit TypeScript entwickelt wird, welches die Lesbarkeit und Wartbarkeit des Codes erhöht
* 🟢 Gut, weil es eine native Möglichkeit gibt Tests zu schreiben
* 🟡 Neutral, weil es nicht viele explizite Deno-Abhängigkeiten existieren, aber auch Module über den Package-Manager NPM eingebunden werden können

### Firebase

<https://firebase.google.com/>

* 🟢 Gut, weil detaillierte Dokumentation vorhanden ist.
* 🟢 Gut, weil die Komplexität durch ein eifaches UI gering ist und keine Notwendigkeit von weiteren Programmiersprachen besteht.
* 🟡 Neutral, weil {Argument c}
* 🔴 Schlecht, weil es sich um eine Closed Source Platform handelt.
* 🔴 Schlecht, weil Nutzer auf der Plattform angemeldet sind und somit ein Umzug auf eine andere Plattform nicht möglich ist.
* 🔴 Schlecht, weil bei extra Funktionen teilweise hohe Kosten anfallen
* 🔴 Schlecht, weil die Plattform Android fokussiert ist und wenig support für iOS liefert
