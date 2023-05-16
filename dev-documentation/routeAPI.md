### Senden eines Requests an die API

Um eine Route brechnen zu können, muss ein **GET-Request** an die API gesendet werden. Über den Header des Requests können die Variablen für die Routenberechnung übergeben werden. Die Resonse der API beinhaltet ein JSON-Objekt mit der berechneten Route.

- **Adresse** der API: localhost:3002
- Mögliche **Header**: *origin* und *destination* (Müssen als Koordinate angegeben werden), *arrivalTime*, *departureTime*, ...
- Über den Parameter *return* kann die Response um weitere Daten erweitert werden.
- Eine genaue Dokumentation der Parameter der HERE Transit-API ist [hier](https://developer.here.com/documentation/public-transit/api-reference-swagger.html) zu finden.
- Das aktuelle Schema für die Response ist [hier](https://www.figma.com/file/YXBqSf42uMzAjgqV4KJmEO/P2-%E2%80%93-Projekt-Board?type=whiteboard&node-id=492-1568&t=YyKORHCxX52Qc8wH-4) zu finden.