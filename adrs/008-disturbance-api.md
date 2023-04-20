# [ADR](./README.md) › Disturbance API

<table>
<tr>
<th>status</th>
<td>proposed</td><!-- {proposed / rejected / accepted / deprecated / … / superseded by ADR-0005 <0005-example.md>} -->
</tr>
<tr>
<th>date</th>
<td>18.04.2023</td><!-- YYYY-MM-DD, when the decision was last updated -->
</tr>
<tr>
<th>deciders</th>
<td>Katrin Hartz</td><!-- list everyone involved in the decision -->
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

Ein zentrales Element des Systems ist die Planung und Begleitung von ÖPNV-Reisen. Hierfür muss das System die Strecken, Verbindungen, Abfahrts- und Ankunftszeiten unterschiedlicher Verkehrsmittel abrufen können, um eventuelle Hindernisse während einer Reise feststellen und vermitteln zu können. Dabei müssen geplante Daten, als auch aktuelle Fahrplanänderungen angezeigt und verarbeitet werden. Hierzu ist eine API zum Abfragen der Fahrpläne nötig.

<!-- Dies ist ein optionales Element. Sie können es gerne entfernen. -->
## Entscheidungstreiber

* Anforderungen
* Lizenz und Kosten
* Aktualität der Daten
* requests/min

## In Betracht gezogene Optionen

* [DB Timetables](https://developers.deutschebahn.com/db-api-marketplace/apis/product/timetables/api/26494#/Timetables_10213/overview)
* [Open Data ÖPNV](https://www.opendata-oepnv.de/ht/de/api)
* [KVB Daten]()


## Ergebnis der Entscheidung

Für das Projekt sollten sowohl [DB Timetables](https://developers.deutschebahn.com/db-api-marketplace/apis/product/timetables/api/26494#/Timetables_10213/overview) als auch [Open Data ÖPNV](https://www.opendata-oepnv.de/ht/de/api) eingebunden werden, da so Pläne und Änderungen der Deutsche Bahn und die Daten der unterschiedlichen Verkehrsunternehmen berücksichtigt werden können. Dadurch haben wir Informationen zu Zügen, Bussen, Bahnen, etc.

<!-- Dies ist ein optionales Element. Sie können es gerne entfernen. -->

<!-- Dies ist ein optionales Element. Fühlen Sie sich frei, es zu entfernen. -->

## Pro und Kontra der Optionen

### DB Timetable

<!-- Dies ist ein optionales Element. Sie können es gerne entfernen. -->
Über die Timetables-API können Informationen zur aktuellen Verkehrslage abgefragt werden. Hierbei stehen sowohl Endpunkte zur Verfügung, an denen der aktuell relevante Ausschnitt des Sollfahrplan abgefragt werden kann, als auch Endpunkte an denen die aktuellen Abweichungen zum Sollfahrplan abgefragt werden können. Details dazu finden Sie in der Beschreibung der API.

* 🟢 Gut, weil kostenfreie Nutzung, Betriebszeit 24/7
* 🟢 Gut, weil sie geplante Daten zu einer bestimmten Station/Bahnhof liefert
* 🟢 Gut, weil sie Daten Änderungen zu einer bestimmten Sation liefert (recent changes are updated every 30s) 
* 🟢 Gute Doku
<!-- Verwende "neutral", wenn das angegebene Argument weder für gut noch für schlecht gewichtet ist -->
* 🟡 Neutral, da nur Zug- und Bahnhofsdaten geliefert werden

### Open Data ÖPNV

OpenData ÖPNV ist eine Initiative deutscher Mobilitätsunternehmen. Hier finden Sie alle Partnerunternehmen und ihre veröffentlichten Daten, die Sie frei verwenden können. Ob Haltestellen-, Fahrplan- oder Echtzeitdaten. Über die OpenService Schnittstelle können die von den Verkehrsunternehmen gelieferten Echtzeitinformationen abgerufen werden.

* 🟢 Gut, OpenService Schnittstelle liefert Echtzeitinformationen von verschiedenen Verkehrsunternehmen
* 🟢 Gut, weil Informationen über weitere Funktionen (Betriebsstörung von Aufzügen/Rolltreppen,...)
* 🟢 Gut, Testserver (mit original Daten mit zugriff auf Echtzeitdaten, Störungen) der VRR steht zur Verfügung


<!-- Dies ist ein optionales Element. Sie können es gerne entfernen. -->
## Ergänzende APIs

Für zusätzliche Informationen bezüglich Haltestellen, Bahnsteig, Gleis, Aufzügen, Parkplätzen,... können folgende APIs der Deutschen Bahn liefern:
* [DB RIS::Stations](https://developers.deutschebahn.com/db-api-marketplace/apis/product/ris-stations) -> Informationen und Funktionen rund um Haltestellen, Bahnhöfe, Gleise, Umsteigezeiten
* [DB Railway-Station Pictures](https://developers.deutschebahn.com/db-api-marketplace/apis/product/49214) -> Unterstützung bei der Orientierung durch Fotos
* [DB Sta-Da](https://developers.deutschebahn.com/db-api-marketplace/apis/product/stada) -> Öffungszeiten, Barrierefreiheit

Diese können als Erweiterung für eine bessere Orientierung und den Umgang mit Herausforderungen genutzt werden.
