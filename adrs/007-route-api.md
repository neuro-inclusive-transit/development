# [ADR](./README.md) › Auswahl einer Routen/Maps-API

<table>
<tr>
<th>status</th>
<td>proposed</td><!-- {proposed / rejected / accepted / deprecated / … / superseded by ADR-0005 <0005-example.md>} -->
</tr>
<tr>
<th>date</th>
<td>2023-04-16</td><!-- YYYY-MM-DD, when the decision was last updated -->
</tr>
<tr>
<th>deciders</th>
<td>Leonard Pelzer, Patrick Raul Lang</td><!-- list everyone involved in the decision -->
</tr>
<tr>
<th>consulted</th>
<td>-</td><!-- list everyone whose opinions are sought (typically subject-matter experts); and with whom there is a two-way communication -->
</tr>
<tr>
<th>informed</th>
<td>-</td><!-- list everyone who is kept up-to-date on progress; and with whom there is a one-way communication -->
</tr>
</table>


## Kontext und Problemstellung

Ein zentrales Element des Systems ist die Planung und Begleitung von ÖPNV-Reisen. Hierfür muss das System eine Routenplanung und Navigation anbieten. Hierzu ist eine API zum Abfragen möglicher Routen nötig. Zusätzlich muss eine Karte in das System integriert werden.

<!-- Dies ist ein optionales Element. Sie können es gerne entfernen. -->
## Entscheidungstreiber

* Funktionale und nicht-funktionale Anforderungen aus Konzeptphase
* Kosten

## In Betracht gezogene Optionen

* [Google Maps Platform](https://developers.google.com/maps?hl=de)
* [Here Maps](https://developer.here.com)
* [Map Box](https://www.mapbox.com/)
* [Bing Maps Platform](https://www.microsoft.com/en-us/maps)

## Ergebnis der Entscheidung

Gewählte Option: "[Here Maps](https://developer.here.com)", weil
Here Maps eine extra API für die Berechnung von ÖPNV-Routen ([HERE Public Transit API](https://developer.here.com/documentation/public-transit/dev_guide/index.html)) anbietet, die viele Einstellungsmöglichkeiten bei der Berechnung einer Route bietet. Zusätzlich kann das Here SDK verwendet werden, um die Karte in das System zu integrieren. Es gibt ein kostenloses Kontingent an API-Anfragen.

Mögliche Alternative/Fallback: "[Google Maps Platform](https://developers.google.com/maps?hl=de)", weil Google Maps eine ähnliche Grundlage wie Here Maps bietet. Es gibt keine extra API für den ÖPNV und kein Studio für die Anpassung der Karte. Das SDK unterstützt JS, Android, IOS und HTML.

<!-- Dies ist ein optionales Element. Sie können es gerne entfernen. -->

## Pro und Kontra der Optionen

### Google Maps Platform

* Gut, weil viele APIs zur Berechnung von Routen (Directions API, Distance Matrix, Routes API)
* Gut, weil Routen API folgende ÖPNV-Modi unterstützt: bus, subway, train, tram, rail
* Gut, weil maps SDK für JS, Android, IOS, HTML
* Gut, weil 200$ monatliches Guthaben für APIs kostenlos

### Here Maps

* Sehr gut, weil eigene Transit-API mit vielen Einstellungsmöglichkeiten (Eine Beispiel-Abfrage befindet sich im [FigJam-Board](https://www.figma.com/file/YXBqSf42uMzAjgqV4KJmEO/P2-%E2%80%93-Projekt-Board?node-id=54-485&t=Xkjrxdm5OXuYMJks-4))
  * Besteht aus folgenden TeilAPIs: Public Transit Routing API, Public Transit Next Departures API, Public Transit Station Search API
* Gut, weil Maps SDK für IOS, Android und Flutter
* Gut, weil freies moantliches Kontingent für Entwicklung
* Gut, weil zusätzliche WeatherAPI
* Gut, weil Here Studio für eine einfache Anpassung der Karte ohne Code

### Mapbox

* Gut, weil Maps SDK
* Gut, weil Mapbox Studio für eine einfache Anpassung der Karte ohne Code
* Gut, weil kostenloses Kontingent
* Schlecht, weil keine Unterstützung von ÖPNV (sondern nur driving-traffic, driving, cycling, walking)

### Bing Maps Platform

* Gut, weil Maps SDK
* Gut, weil Basic-Key mit kostenlosem Kontingent
* Gut, weil Routen-API mit [Dokumentation](https://learn.microsoft.com/en-us/bingmaps/coverage/transit-coverage/europe), welche ÖPNV-Unternehmen über die API abgefragt werden

<!-- Dies ist ein optionales Element. Sie können es gerne entfernen. -->

## Mögliche Probleme und Fallbacks

* **Keine Live-Daten**: 
  * Beschreibung: Es ist nicht erkennbar, wie aktuell die Daten der Here-API sind. Es ist aber davon auszugehen, dass diese Daten keine Verspätungen oder spontane Ausfälle beinhalten. Hierfür muss im besten Fall eine weitere API eingebunden werden, um die aktualität der Daten zu verifizieren.
  * Fallback: Eigene Daten mit eigens entwickelter API simulieren.

* **Unterstützte Programmiersprachen der Here Maps SDK passen nicht zu System-Architektur**:
  * Beschreibung: Die Integration der Karte in eine Web-Anwendung kann nur mit Flutter erfolgen.
  * Fallback: Verwendung der Google Maps Platform

## Weitere Informationen

Alle gesammelten Informationen und weitere Links sind im [FigJam-Board](https://www.figma.com/file/YXBqSf42uMzAjgqV4KJmEO/P2-%E2%80%93-Projekt-Board?node-id=41-74&t=Xkjrxdm5OXuYMJks-4) dokumentiert.