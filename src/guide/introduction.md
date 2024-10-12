---
footer: false
---

# Introductie {#introduction}

:::info Je bent de documentatie voor Vue 3 aan het lezen!

- Vue 2 support is gestopt op **Dec 31, 2023**. Leer meer over [Vue 2 EOL](https://v2.vuejs.org/eol/).
- Aan het upgraden van Vue 2? Bekijk deze [Migreatiehandleiding](https://v3-migration.vuejs.org/).
  :::

<style src="@theme/styles/vue-mastery.css"></style>
<div class="vue-mastery-link">
  <a href="https://www.vuemastery.com/courses/" target="_blank">
    <div class="banner-wrapper">
      <img class="banner" alt="Vue Mastery banner" width="96px" height="56px" src="https://storage.googleapis.com/vue-mastery.appspot.com/flamelink/media/vuemastery-graphical-link-96x56.png" />
    </div>
    <p class="description">Leer Vue met video tutorials op <span>VueMastery.com</span></p>
    <div class="logo-wrapper">
        <img alt="Vue Mastery Logo" width="25px" src="https://storage.googleapis.com/vue-mastery.appspot.com/flamelink/media/vue-mastery-logo.png" />
    </div>
  </a>
</div>

## Wat is Vue? {#what-is-vue}

Vue (uitgesproken /vjuː/, zoals **view**) is een JavaScript framework voor het bouwen van gebruikersinterfaces. Het bouwt voort op standaard HTML, CSS en JavaScript en biedt een declaratief, component-gebaseerd programmeermodel dat je helpt efficiënt gebruikersinterfaces van elke complexiteit te ontwikkelen.

Hier is een simpel voorbeeld:

<div class="options-api">

```js
import { createApp } from 'vue'

createApp({
  data() {
    return {
      count: 0
    }
  }
}).mount('#app')
```

</div>
<div class="composition-api">

```js
import { createApp, ref } from 'vue'

createApp({
  setup() {
    return {
      count: ref(0)
    }
  }
}).mount('#app')
```

</div>

```vue-html
<div id="app">
  <button @click="count++">
    Het aantal is: {{ count }}
  </button>
</div>
```

**Resultaat**

<script setup>
import { ref } from 'vue'
const count = ref(0)
</script>

<div class="demo">
  <button @click="count++">
    Het aantal is: {{ count }}
  </button>
</div>

Het bovenstaande voorbeeld demonstreert de twee kernfuncties van Vue:

- **Declaratief Renderen**: Vue breidt standaard HTML uit met een templatesyntax die ons in staat stelt om HTML-output declaratief te beschrijven op basis van de JavaScript staat.

- **Reactiviteit**: Vue houdt de staat van de applicatie automatisch bij en zorgt ervoor dat de DOM efficiënt wordt bijgewerkt wanneer de staat verandert.

Je hebt misschien al vragen - geen zorgen. We zullen elk klein detail behandelen in de rest van de documentatie. Voor nu, lees gewoon verder zodat je een algemeen begrip krijgt van wat Vue aanbiedt.

:::tip Voorwaarden
De rest van de documentatie gaat er van uit dat je basiskennis hebt van HTML, CSS en JavaScript. Als je helemaal nieuw bent in frontend-ontwikkeling, is het misschien niet het beste idee om meteen in een framework te duiken als eerste stap - begrijp de basis en kom dan terug! Je kunt je kennisniveau controleren met deze overzichten voor [JavaScript](https://developer.mozilla.org/en-US/docs/Web/JavaScript/A_re-introduction_to_JavaScript), [HTML](https://developer.mozilla.org/en-US/docs/Learn/HTML/Introduction_to_HTML) en [CSS](https://developer.mozilla.org/en-US/docs/Learn/CSS/First_steps) indien nodig. Ervaring met andere frameworks helpt, maar is niet vereist.
:::

## Het Progressieve Framework {#the-progressive-framework}

Vue is een framework en ecosysteem  dat de meeste van de algemeene functies die nodig zijn in frontend-ontwikkeling omvat. Maar het web is extreem divers - de dingen die we op het web bouwen kunnen drastisch verschillen in vorm en schaal. Met dat in gedachten is Vue ontworpen om flexibel en incrementeel aanpasbaar te zijn. Afhankelijk van je gebruikssituatie kan Vue op verschillende manieren worden gebruikt:

- Verbetering van statische HTML zonder bouwstappen
- Integreren als Web Componenten op elke pagina
- Single-Page Application (SPA)
- Fullstack / Server-Side Rendering (SSR)
- Jamstack / Static Site Generation (SSG)
- Richten op desktop, mobiel, WebGL, en zelfs de terminal

Als je deze concepten intimiderend vindt, geen zorgen! De tutorial en handleiding vereisen alleen basiskennis van HTML en JavaScript, en je zou moeten kunnen volgen zonder een expert te zijn in een van deze.

Als je een ervaren ontwikkelaar bent die geïnteresseerd is in hoe je Vue het beste in je stack kunt integreren, of als je nieuwsgierig bent naar wat deze termen betekenen, bespreken we ze in meer detail in [Manieren om Vue te gebruiken](/guide/extras/ways-of-using-vue).

Ondanks de flexibiliteit, wordt de kernkennis over hoe Vue werkt gedeeld over al deze gebruikssituaties. Zelfs als je nu nog maar een beginner bent, zal de kennis die je onderweg opdoet nuttig blijven als je groeit om meer ambitieuze doelen in de toekomst aan te pakken. Als je een veteraan bent, kun je de optimale manier kiezen om Vue te benutten op basis van de problemen die je probeert op te lossen, terwijl je dezelfde productiviteit behoudt. Daarom noemen we Vue "Het Progressieve Framework": het is een framework dat met je kan meegroeien en zich kan aanpassen aan je behoeften.

## Single-File Components {#single-file-components}

In meeste Vue projecten die gebruik maken van build-tools, schrijven we Vue componenten in een HTML-achtig bestandsformaat genaamd **Single-File Component** (ook bekend als `*.vue` bestanden, afgekort als **SFC**). Een Vue SFC, zoals de naam al doet vermoeden, omvat de logica van het component (JavaScript), template (HTML) en stijlen (CSS) in één bestand. Hier is het vorige voorbeeld, geschreven in SFC-formaat:

<div class="options-api">

```vue
<script>
export default {
  data() {
    return {
      count: 0
    }
  }
}
</script>

<template>
  <button @click="count++">Het aantal is: {{ count }}</button>
</template>

<style scoped>
button {
  font-weight: bold;
}
</style>
```

</div>
<div class="composition-api">

```vue
<script setup>
import { ref } from 'vue'
const count = ref(0)
</script>

<template>
  <button @click="count++">Count is: {{ count }}</button>
</template>

<style scoped>
button {
  font-weight: bold;
}
</style>
```

</div>

SFC is een kenmerkend kenmerk van Vue en is de aanbevolen manier om Vue-componenten te schrijven **als** je gebruikssituatie een build-setup rechtvaardigt. Je kunt meer leren over de [hoe en waarom van SFC](/guide/scaling-up/sfc) in het toegewijde gedeelte - maar voor nu, weet gewoon dat Vue alle build-tools setup voor je zal afhandelen.

## API Stylen {#api-styles}

Vue componenten kunnen worden geschreven in twee verschillende API-stijlen: **Options API** en **Composition API**.

### Options API {#options-api}

Met Options API definiëren we de logica van een component met een object van opties zoals `data`, `methods`, en `mounted`. Eigenschappen gedefinieerd door opties worden blootgesteld op `this` binnen functies, die verwijst naar de componentinstantie:

```vue
<script>
export default {
  // Properties die worden geretourneerd door data() ontvangen een reactieve staat
  // en worden blootgesteld op `this`.
  data() {
    return {
      count: 0
    }
  },

  // Methods zijn functies die de staat muteren en updates triggeren.
  // Ze kunnen worden gebonden als event handlers in templates.
  methods: {
    increment() {
      this.count++
    }
  },

  // Lifecycle hooks worden opgeroepen op verschillende momenten
  // van de levenscyclus van een component.
  // Deze functie wordt opgeroepen wanneer de component word gemount.
  mounted() {
    console.log(`Het initiële aantal is ${this.count}.`)
  }
}
</script>

<template>
  <button @click="increment">Het aantal is: {{ count }}</button>
</template>
```

[Probeer het in de Playground](https://play.vuejs.org/#eNptkMFqxCAQhl9lkB522ZL0HNKlpa/Qo4e1ZpLIGhUdl5bgu9es2eSyIMio833zO7NP56pbRNawNkivHJ25wV9nPUGHvYiaYOYGoK7Bo5CkbgiBBOFy2AkSh2N5APmeojePCkDaaKiBt1KnZUuv3Ky0PppMsyYAjYJgigu0oEGYDsirYUAP0WULhqVrQhptF5qHQhnpcUJD+wyQaSpUd/Xp9NysVY/yT2qE0dprIS/vsds5Mg9mNVbaDofL94jZpUgJXUKBCvAy76ZUXY53CTd5tfX2k7kgnJzOCXIF0P5EImvgQ2olr++cbRE4O3+t6JxvXj0ptXVpye1tvbFY+ge/NJZt)

### Composition API {#composition-api}

Met Composition API, definiëren we de logica van een component met geïmporteerde API-functies. In SFC's wordt Composition API typisch gebruikt met [`<script setup>`](/api/sfc-script-setup). Het `setup` attribuut is een hint die Vue compile-time transformaties laat uitvoeren die ons in staat stellen om Composition API te gebruiken met minder boilerplate. Bijvoorbeeld, imports en top-level variabelen / functies gedeclareerd in `<script setup>` zijn direct bruikbaar in de template.

Hier is hetzelfde component, met exact hetzelfde template, maar met gebruik van Composition API en `<script setup>` in de plaats:

```vue
<script setup>
import { ref, onMounted } from 'vue'

// Reactieve staat
const count = ref(0)

// functies die de staat muteren en updates zullen triggeren
function increment() {
  count.value++
}

// lifecycle hooks
onMounted(() => {
  console.log(`Het initiële aantal is ${count.value}.`)
})
</script>

<template>
  <button @click="increment">Aantal is: {{ count }}</button>
</template>
```

[Probeer het in de Playground](https://play.vuejs.org/#eNpNkMFqwzAQRH9lMYU4pNg9Bye09NxbjzrEVda2iLwS0spQjP69a+yYHnRYad7MaOfiw/tqSliciybqYDxDRE7+qsiM3gWGGQJ2r+DoyyVivEOGLrgRDkIdFCmqa1G0ms2EELllVKQdRQa9AHBZ+PLtuEm7RCKVd+ChZRjTQqwctHQHDqbvMUDyd7mKip4AGNIBRyQujzArgtW/mlqb8HRSlLcEazrUv9oiDM49xGGvXgp5uT5his5iZV1f3r4HFHvDprVbaxPhZf4XkKub/CDLaep1T7IhGRhHb6WoTADNT2KWpu/aGv24qGKvrIrr5+Z7hnneQnJu6hURvKl3ryL/ARrVkuI=)

### Welke te kiezen? {#which-to-choose}

Beide API stylen zijn volledig in staat om de meest voorkomende use cases te dekken. Het zijn verschillende interfaces die worden aangedreven door hetzelfde onderliggende systeem. In feite is de Options API geïmplementeerd bovenop de Composition API! De fundamentele concepten en kennis over Vue worden gedeeld tussen de twee stylen.

De Options API is gecentreerd rond het concept van een "component instantie" (`this` zoals te zien in het voorbeeld), wat typisch beter aansluit bij een klassieke mentaliteit voor gebruikers die uit OOP-talen komen. Het is ook meer beginner-vriendelijk door de reactiviteit details te abstraheren en code-organisatie af te dwingen via optiegroepen.

De Composition API is gecentreerd rond het declareren van reactieve staatvariabelen direct in een functiescope en het samenstellen van staat uit meerdere functies om complexiteit te behandelen. Het is meer vrijvormig en vereist een begrip van hoe reactiviteit werkt in Vue om effectief te worden gebruikt. In ruil daarvoor maakt de flexibiliteit ervan krachtigere patronen mogelijk voor het organiseren en hergebruiken van logica.

Je kan meer leren over de vergelijking tussen de twee stylen en de potentiële voordelen van de Composition API in de [Composition API FAQ](/guide/extras/composition-api-faq).

Als je nieuw bent in Vue, is hier onze algemene aanbeveling:

- Voor leer doeleinden, ga met de stijl die er makkelijker uitziet om te begrijpen voor jou. De meeste van de kernconcepten worden gedeeld tussen de twee stylen. Je kan altijd de andere stijl later oppikken.

- Voor productie gebruik:

  - Ga met Options API als je geen build-tools gebruikt, of van plan bent om Vue voornamelijk te gebruiken in lage-complexiteit scenario's, bijvoorbeeld progressieve verbetering.

  - Ga met Compositie API en Single-File Componenten als je van plan bent om volledig applicaties met Vue te bouwen.

Je moet niet vasthouden aan slechts één stijl tijdens de leerfase. De rest van de documentatie zal codevoorbeelden in beide stylen bieden waar van toepassing, en je kan op elk moment tussen hen schakelen met de **API Voorkeurschakelaars** bovenaan de linker zijbalk.

## Heb je nog altijd vragen? {#still-got-questions}

Bekijk onze [FAQ](/about/faq).

## Kies jouw leerpad {#pick-your-learning-path}

Verschillende developers hebben verschillende leerstijlen. Kies gerust een leerpad dat bij je voorkeur past - hoewel we aanraden om alle inhoud door te nemen, indien mogelijk!

<div class="vt-box-container next-steps">
  <a class="vt-box" href="/tutorial/">
    <p class="next-steps-link">Probeer de volgende tutorial</p>
    <p class="next-steps-caption">Voor degene die verkiezen om hands-on te leren.</p>
  </a>
  <a class="vt-box" href="/guide/quick-start.html">
    <p class="next-steps-link">Lees de handleiding</p>
    <p class="next-steps-caption">De handleiding neemt je mee door elk aspect van het framework in volledige detail.</p>
  </a>
  <a class="vt-box" href="/examples/">
    <p class="next-steps-link">Bekijk de voorbeelden</p>
    <p class="next-steps-caption"> Verken voorbeelden van kernfuncties en veel voorkomende UI-taken.</p>
  </a>
</div>
