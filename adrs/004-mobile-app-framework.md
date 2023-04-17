# [ADR](./README.md) › {Kurztitel des gelösten Problems und der Lösung}

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
<td>Finn Gedrath</td><!-- list everyone involved in the decision -->
</tr>
<tr>
<th>consulted</th>
<td>Patrick Lang</td><!-- list everyone whose opinions are sought (typically subject-matter experts); and with whom there is a two-way communication -->
</tr>
<tr>
<th>informed</th>
<td></td><!-- list everyone who is kept up-to-date on progress; and with whom there is a one-way communication -->
</tr>
</table>


## Kontext und Problemstellung

In [ADR-003](./003-mobile-app-ground-technology.md) wurde entschieden, dass eine native App für Android und iOS mit Hilfe einer Cross-Platform-Lösung entwickelt werden soll. Dieses ist Framework unabhängig. In diesem ADR wird nun das Web-Framework für die Entwicklung der App festgelegt.

<!-- Dies ist ein optionales Element. Sie können es gerne entfernen. -->
## Entscheidungstreiber

Teilweise wurde Dimensionen aus Vargas et. al. (2020) übernommen[^vargas-2020]:

* bestehendes Wissen in der Gruppe, um eine zu erwartende Lernkurve zu minimieren (&rarr; Ökonomie)
* Performance der Technologie
* Dokumentation und Community
* Bestehende Plugins und Libraries, die zusammen mit der Grundtechnologie (siehe [ADR-003](./003-mobile-app-ground-technology.md)) verwendet werden können.
* Usability (Ease-of-Use, Lernkurve, ...)


## In Betracht gezogene Optionen

* Svelte
* React
* Vue

## Ergebnis der Entscheidung

Gewählte Option: "{Titel der Option 1}", weil
{Begründung. z.B., einzige Option, die das K.O.-Kriterium Entscheidungstreiber erfüllt | die Kraft {Kraft} auflöst | ... | am besten ausfällt (siehe unten)}.

<!-- Dies ist ein optionales Element. Sie können es gerne entfernen. -->
### Consequences

* Gut, weil {positive Folge, z.B. Verbesserung einer oder mehrerer gewünschter Eigenschaften, ...}
* Schlecht, weil {negative Konsequenz, z.B. Beeinträchtigung einer oder mehrerer gewünschter Eigenschaften, ...}
* ... <!-- Anzahl der Konsequenzen kann variieren -->

<!-- Dies ist ein optionales Element. Fühlen Sie sich frei, es zu entfernen. -->
## Validierung

{beschreibt, wie die Umsetzung/Einhaltung des ADR validiert wird. Z.B. durch eine Überprüfung oder einen ArchUnit-Test}

<!-- Dies ist ein optionales Element. Sie können es gerne entfernen. -->
## Pro und Kontra der Optionen

### Svelte

Svelte ist ein junges Framework (bekannt seit: 2019[^js-state-2019]) entwickelt von Rich Harris. Es basiert syntaktisch auf HTML und JavaScript. Als Compiler, ist teilweise eigene Svelte Syntax möglich. Teilweise bestehen Ähnlichkeiten zu Mustache.

- [Svelte Dokumentation](https://svelte.dev/docs)
- [Svelte Playground](https://svelte.dev/repl/)
- [NativeScript + Svelte](https://docs.nativescript.org/tutorial/svelte.html)
- [Capacitor + Svelte](https://capacitorjs.com/solution/svelte) 

Beispiel-Syntax einer Komponente:

```svelte
<script>
let count = 1;
$: doubled = count * 2;

function handleClick() { count += 1; }
</script>

<button on:click={handleClick}> {count} </button>

<p>{count} * 2 = {doubled}</p>
```

* 🟢 Gut, weil geringer Boilerplate-Code, da Reaktivität und State-Verwaltung direkt in der Komponente möglich ist.
* 🟢 Gut, denn hohe technische Reaktivität bei State-Veränderung innerhalb einer Komponente und über mehrere Komponenten hinweg.

* 🟢 Gut, da Svelte-Playground vorhanden ist, um Svelte-Code direkt auszuprobieren, und die Svelte-Syntax erlernt werden kann.
* 🟢 Gut, da Svelte-Syntax ähnlich zu bekannten Templating-Engines wie Mustache ist.
* 🟡 Neutral, weil Wissen innerhalb der Gruppe über Svelte teilweise vorhanden ist.

* 🟡 Neutral, weil Svelte aktiv weiterentwickelt wird und die Major-Releases in kurzen Abständen erscheinen.
* 🔴 Schlecht, weil Svelte noch relativ neu ist und es noch nicht viele Plugins gibt.

### React

React ist ein von Facebook entwickeltes Framework. Templates werden in JSX geschrieben (Erweiterung von JS um HTML-Elemente).

- [React Dokumentation](https://reactjs.org/docs/getting-started.html)
- [React Playground](https://codesandbox.io/s/new)
- [NativeScript + React](https://docs.nativescript.org/tutorial/react.html)
- [Capacitor + React](https://capacitorjs.com/solution/react) 

Beispiel-Syntax einer Komponente:

```jsx
import React, { useState } from 'react';

export default function Counter() {
  const [count, setCount] = useState(0);

  return (
    <div>
      <button onClick={() => setCount(count + 1)}>
        {count}
      </button>
      <p>{count} * 2 = {count * 2}</p>
    </div>
  );
}

```

* 🟢 Gut, weil große Community und viele Plugins vorhanden sind.
* 🔴 Schlecht, weil hoher Boilerplate-Code, da Reaktivität und State-Verwaltung nicht direkt in der Komponente möglich ist. Stattdessen muss ein zusätzlicher State-Manager verwendet werden.
* 🔴 Schlecht, weil Browser-APIs wegabstrahiert und konzeptioniert werden (z.B. `fetch`, `DOM`, etc.)

### Vue

Vue.js ist ein Framework von Evan You. Vue Projekte können als eigenständige Single-File-Componenten entwickelt werden. Templates werden in HTML mit einer Mustach-ähnlichen Syntax geschrieben.

- [Vue Dokumentation](https://vuejs.org/v2/guide/)
- [Vue Playground](https://play.vuejs.org/)
- [NativeScript + Vue](https://docs.nativescript.org/tutorial/vue.html)
- [Capacitor + Vue](https://capacitorjs.com/solution/vue)

Beispiel-Syntax einer Komponente:

```vue
<template>
  <button @click="count++">You clicked me {{ count }} times.</button>

  <p> {{ count }} * 2 = {{ double }} </p>
</template>

<script>
export default {
  data() {
    return {
      count: 0,
    };
  },
  computed: {
    double() {
      return this.count * 2;
    },
  },
};
</script>
```

* 🟢 Gut, weil große Community und viele Plugins vorhanden sind.
* 🟢 Gut, weil von kleinen bis zu großen Projekten verwendet wird.


[^vargas-2020]: Larios Vargas, Enrique, Maurício Aniche, Christoph Treude et al. (2020). „Selecting Third-Party Libraries: The Practitioners’ Perspective“. In: ESEC/FSE 2020. Virtual Event, USA: Association for Computing Machinery, S. 245–256. ISBN: 9781450370431. DOI: [10.1145/3368089.3409711](https://doi.org/10.1145/3368089.3409711)

[^js-state-2019]: Greif, Sacha und Raphaël Benitte (2020). State of JavaScript Trend Report. Technologies: Front-end Frameworks. Letzter Zugriff: 10. August 2021. URL: <https://2020.stateofjs.com/en-US/technologies/front-end-frameworks/>.