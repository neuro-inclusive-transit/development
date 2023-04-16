# [ADR](./README.md) › {Auswahl eine Routen-API}

<table>
<tr>
<th>status</th>
<td>proposed</td><!-- {proposed / rejected / accepted / deprecated / … / superseded by ADR-0005 <0005-example.md>} -->
</tr>
<tr>
<th>date</th>
<td>2023-04.16</td><!-- YYYY-MM-DD, when the decision was last updated -->
</tr>
<tr>
<th>deciders</th>
<td>Leonard Pelzer</td><!-- list everyone involved in the decision -->
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

EIn zentrales Element des Sytsem ist die Planung und Begleitung von ÜPNV-Reisen. Hierfür muss das System eine Routenplanung und Navigation anbieten. Hierzu ist eine API zum Abfragen möglicher Routen nötig. Zusätzlich muss eine Karte in das System integriert werden.

<!-- Dies ist ein optionales Element. Sie können es gerne entfernen. -->
## Entscheidungstreiber

* Funktionale und nichtfunktionale Anforderungen aus Konzeptphase.
* Kosten

## In Betracht gezogene Optionen

* [Google Maps Platform](https://developers.google.com/maps?hl=de)
* [Here Maps](https://developer.here.com)
* [Map Box](https://www.mapbox.com/)
* [Bing Maps Platform](https://www.microsoft.com/en-us/maps)

## Ergebnis der Entscheidung

Gewählte Option: "[Here Maps](https://developer.here.com)", weil
Here Maps eine extra API für die Berechnung von ÖPNV-Routen ([HERE Public Transit API](https://developer.here.com/documentation/public-transit/dev_guide/index.html)) anbietet, die viele Einstellungsmöglichkeiten bei der Berechnung eine Route bietet. Zusätzlich kann das Here SDK verwendet werden, um die Karte in das System zu integrieren.

<!-- Dies ist ein optionales Element. Sie können es gerne entfernen. -->
### Consequences

* Gut, weil {positive Folge, z.B. Verbesserung einer oder mehrerer gewünschter Eigenschaften, ...}
* Schlecht, weil {negative Konsequenz, z.B. Beeinträchtigung einer oder mehrerer gewünschter Eigenschaften, ...}
* ... <!-- Anzahl der Konsequenzen kann variieren -->

<!-- Dies ist ein optionales Element. Fühlen Sie sich frei, es zu entfernen. -->

## Pro und Kontra der Optionen

### {Titel der Option 1}

<!-- Dies ist ein optionales Element. Sie können es gerne entfernen. -->
{Beispiel / Beschreibung / Verweis auf weitere Informationen / ...}

* Gut, denn {Argument a}
* Gut, weil {Argument b}
<!-- Verwende "neutral", wenn das angegebene Argument weder für gut noch für schlecht gewichtet ist -->
* Neutral, weil {Argument c}
* Schlecht, weil {Argument d}
* ... <!-- Anzahl der Vor- und Nachteile kann variieren -->

### {Titel der anderen Option}

{Beispiel / Beschreibung / Verweis auf weitere Informationen / ...}

* Gut, weil {Argument a}
* Gut, weil {Argument b}
* Neutral, weil {Argument c}
* Schlecht, weil {Argument d}
* ...

<!-- Dies ist ein optionales Element. Sie können es gerne entfernen. -->
## Weitere Informationen

Alle gesamelten Informationen sind im [FigJam-Board](https://www.figma.com/file/YXBqSf42uMzAjgqV4KJmEO/P2-%E2%80%93-Projekt-Board?node-id=41-74&t=Xkjrxdm5OXuYMJks-4) dokumentiert.