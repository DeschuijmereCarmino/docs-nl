# Bijdragen aan de Nederlandse versie van vuejs.org

Dit project is een fork van vuejs/docs met als doel de inspanningen voor de vertaling in het Nederlands te centraliseren.

Wil je bijdragen aan dit project? Geweldig! Graag verwijzen we je door naar het gedeelte [Bijdragen](#Bijdragen). Zo weet je precies hoe je een pull request aanmaakt.

Voordat je begint, neem even de tijd om de [richtlijnen voor het vertalen van de documentatie](https://github.com/vuejs-translations/guidelines) door te nemen.

# vuejs.org

## Bijdragen

Deze site is gebouwd met [VitePress](https://github.com/vuejs/vitepress) en is afhankelijk van [@vue/theme](https://github.com/vuejs/vue-theme). De inhoud van de site is geschreven in Markdown-formaat en bevindt zich in `src`. Voor eenvoudige bewerkingen kunt u het bestand rechtstreeks op GitHub bewerken en een Pull Request aanmaken.

Voor lokale ontwikkeling wordt [pnpm](https://pnpm.io/) aanbevolen als package manager:

```bash
pnpm i
pnpm run dev
```

Dit project vereist dat Node.js `v18` of hoger is. En het wordt aanbevolen om corepack te gebruiken:

```bash
corepack enable
```

## Werken aan de inhoud

-Zie de VitePress-documentatie over ondersteunde [Markdown-extensies](https://vitepress.dev/guide/markdown) en de mogelijkheid om [Vue-syntax binnen markdown te gebruiken](https://vitepress.dev/guide/using-vue).

-Zie de [Schrijfgids](https://github.com/vuejs/docs/blob/main/.github/contributing/writing-guide.md) voor onze regels en aanbevelingen voor het schrijven en onderhouden van documentatie-inhoud.

## Werken aan het thema

Als er wijzigingen moeten worden aangebracht voor het thema, bekijk dan de [instructies voor het ontwikkelen van het thema naast de documentatie](https://github.com/vuejs/vue-theme#developing-with-real-content).
