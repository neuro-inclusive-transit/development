# [ADR](./README.md) › NativeScript als Grundlagen-Technologie frontend-seitig

<table>
<tr>
<th>status</th>
<td>accepted</td><!-- {proposed / rejected / accepted / deprecated / … / superseded by ADR-0005 <0005-example.md>} -->
</tr>
<tr>
<th>date</th>
<td>2023-04-17</td><!-- YYYY-MM-DD, when the decision was last updated -->
</tr>
<tr>
<th>deciders</th>
<td>Patrick Lang</td><!-- list everyone involved in the decision -->
</tr>
<tr>
<th>consulted</th>
<td>Finn Gedrath</td><!-- list everyone whose opinions are sought (typically subject-matter experts); and with whom there is a two-way communication -->
</tr>
<tr>
<th>informed</th>
<td></td><!-- list everyone who is kept up-to-date on progress; and with whom there is a one-way communication -->
</tr>
</table>


## Kontext und Problemstellung

Im Rahmen der Konzeption der mobilen App Anwendung wurde durch die Anforderungen der verschiedenen Stakeholder deutlich, dass die Anwendung, in voller Ausführung, auf iOS und Android Geräten voll funktionsfähig sein muss. Daher wird in diesem ADR festgelegt mit welchen Technologien diese Anforderungen am effektivsten umgesetzt werden können.


## Entscheidungstreiber

* Ausführlichkeit der Dokumentation
*	Performance der Technologie
*	Skillset der Projektgruppe
*	Erweiterbarkeit
*	Verfügbarkeit von externen Tools, die die Entwicklung beschleunigen
*	Maturity (Geschichte, Popularität, Community)


## In Betracht gezogene Optionen

* Capacitor
* NativeScript
* Flutter

## Ergebnis der Entscheidung

Gewählte Option: "NativeScript", weil am besten ausfällt (siehe unten)}.

### Consequences

* Gut, weil guter Reifegrad der Dokumentation
* Gut, weil passend zur Architektur


## Pro und Kontra der Optionen

### Kotlin für Android und/oder Swift für iOS

Kotlin ist eine plattformübergreifende, statisch typisierte Programmiersprache, die in Bytecode für die Java Virtual Machine übersetzt wird, aber auch in JavaScript-Quellcode oder in Maschinencode umgewandelt werden kann.

Swift ist eine Programmiersprache von Apple Inc. für iOS, iPadOS, macOS, tvOS, watchOS, Linux, Windows


*	🔴 Schlecht, weil die Nutzung den Arbeitsprozess für die Erstellung einer nativen App für Android und iOS verlangsamt.
*	🔴 Schlecht, weil Swift am besten für die Entwicklung von iOS Anwendungen funktioniert und auch dafür ausgelegt wurde
*	🔴 Schlecht, weil Kotlin nur performant bei der Erstellung von Android Anwendungen ist und dabei trotzdem bei vielen Stellen Java verwendet




### Flutter

Flutter ist ein Open-Source-UI-Entwicklungs-Kit von Google. Mit Flutter können Cross-Platform Apps in der Programmiersprache Dart entwickelt werden. Ein Flutter-Programm soll ohne größere Anpassungen auf folgenden Zielplattformen lauffähig sein: Webanwendung, Android, iOS, Windows, Linux, macOS und Google Fuchsia.

* [Flutter Dokumentation](https://dart.dev/guides)
* [Flutter Playground](https://dartpad.dev/?)


*	🟢 Gut, denn Flutter hat einen App-Builder der eine einfache Erstellung von Prototypen ermöglicht
*	🟢 Gut, weil durch third-party Integrationen auf Native Funktionen zugegriffen werden kann
*	🟢 Gut, weil Veränderungen direkt in der App erscheinen
*	🟢 Gut, weil Flutter Apps eine gute Performance haben
*	🟢 Gut, weil single code base und dadurch schnelle und effiziente Entwicklung
*	🟡 Neutral, weil für das Erstellen der App Dart verwendet werden muss
*	🔴 Schlecht, weil Flutter Apps nicht von Browsern supported werden
*	🔴 Schlecht, weil Flutter noch relativ neu ist und keine große Unterstützung durch die Community liefert.
*	🔴 Schlecht, weil viel selbst erlernt werden muss und dadurch der Zeitaufwand signifikant ansteigt
*	🔴 Schlecht, weil Flutter von Google erstellt wurde und daher in Einzelfällen Probleme mit iOS Systemen aufweist



### Nativescript

NativeScript ist ein Open-Source-Framework von Telerik by Progress zum Entwickeln von Apps auf iOS und Android. Als plattformunabhängige Programmiersprachen werden JavaScript und TypeScript eingesetzt.

* [NativeScript Dokumentation](https://docs.nativescript.org/)
* [NativeScript Playground](https://preview.nativescript.org/)
* [NativeScript Client-Side Storage](https://blog.nativescript.org/client-side-storage-in-nativescript-applications/)

*	🟢 Gut, weil es das Aussehen und das Gefühl einer nativen App verleiht
*	🟢 Gut, weil sehr große Community
*	🟢 Gut, weil immer kompatibel mit den neuesten OS Versionen ist
*	🟢 Gut, weil es mit JavaScript und CSS geschrieben wird
*	🟢 Gut, weil clientseitige Haltung von Daten möglich ist
*	🟢 Gut, weil asymmetrische Kryptographie durch ein Plugin möglich ist
*	🔴 Schlecht, weil HTML und DOM nicht unterstützt werden (durch Plugin möglich)
*	🔴 Schlecht, weil für das DeBugging ein Emulator oder ein Gerät verwendet werden muss (Android Studio/XCode möglich)


### Capacitor

Capacitor ist eine native Open-Source-Framework zum Erstellen webnativer Apps. Es lassen sich plattformübergreifende iOS-, Android- und Progressive-Web-Apps mit JavaScript, HTML und CSS entwickeln.

* [Capacitor Dokumentation](https://capacitorjs.com/docs)

*	🟢 Gut, weil für die Erstellung der einer nativen App HTML, CSS und JavaScript verwendet wird
*	🟢 Gut, weil es gleichzeitig auch als PWA funktioniert
*	🟢 Gut, weil eine konstante API für ein 100% sharing des Codes sorgt
*	🟢 Gut weil, die Anwendung durch den WebView auf allen Geräten und Systemen gleich aussieht
*	🟢 Gut, weil auch Cordova plugins unterstützt werden
*	🟢 Gut, weil Capacitor mit jedem JavaScript Framework kompatibel ist
*	🟢 Gut weil, sehr lightweight
*	🟢 Gut weil, vollen Zugriff auf native SDK auf allen Plattformen 
*	🟢 Gut weil, vereinfachte App Store Distribution
*	🔴 Schlecht, weil Capacitor zum Speichern von Daten SQLite nutzt 
*	🔴 Schlecht, weil langsamer durch WebViews
*	🔴 Schlecht, weil ältere Geräte Probleme beim Laden mit Capacitor haben
*	🔴 Schlecht, weil nur eine kleine Menge an Daten ( wie z.B die User ID) lokal gespeichert werden kann. Außerdem werden Informationen von WebViews vom OS bei Platzmangel gelöscht.