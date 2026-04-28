# Asset Management · Repo-fähiges Moduldeck

Diese Version ist für GitHub Pages / ein Repo optimiert.

## Struktur

```text
asset-management/
├── index.html
├── assets/
│   ├── css/
│   │   └── deck.css
│   └── js/
│       └── deck.js
├── topics/
│   ├── manifest.js
│   ├── kapitel-2-traditionelle-assetklassen.html
│   ├── kapitel-3-alternative-assetklassen.html
│   └── kapitel-4-mathematische-statistische-grundlagen.html
    |__ kapitel 5
├── docs/
│   └── CODEX_PROMPT_ADD_TOPIC.md
└── single-file/
    └── asset-management-click.html
```

## Nutzung

Für GitHub Pages:
1. Den Ordner `asset-management/` in dein Repo hochladen.
2. `asset-management/index.html` öffnen bzw. über GitHub Pages aufrufen.
3. Die Topic-Dateien werden über `topics/manifest.js` nachgeladen.

Wichtig: Die modulare Version sollte über GitHub Pages oder einen lokalen Server geöffnet werden. Beim direkten Öffnen per Datei-App / `file://` kann der Browser das Nachladen der Topic-Dateien blockieren.

## Navigation

- Obere Themen-Navigation: springt zu Kapitel-/Topic-Startfolien.
- Dropdown: zeigt jede einzelne Folie.
- Pfeilbuttons: vor/zurück.
- Tastatur: Pfeil rechts/links, PageDown/PageUp, Space, Backspace.
- Suche: `Strg/Cmd + K`.
- Klick auf Folie:
  - linkes Drittel = zurück
  - rechtes Drittel = weiter
  - mittleres Drittel = neutral

## Neues Thema hinzufügen

1. Neue Topic-Datei in `topics/` ablegen, z. B.:

```text
topics/kapitel-5-portfoliotheorie.html
```

2. In dieser Datei nur Slide-Sections einfügen, kein vollständiges HTML-Dokument:

```html
<!-- MODULE_CHAPTER_START: kapitel-5 | Kapitel 5 · Portfoliotheorie | slides=12 -->

<section
  id="kapitel-5-slide-01"
  class="slide-title module-slide"
  data-module="asset-management"
  data-chapter-key="kapitel-5"
  data-chapter-title="Kapitel 5 · Portfoliotheorie"
  data-chapter-short="Kapitel 5"
  data-chapter-start="true"
  data-slide-index="1"
  data-slide-total="12">
  ...
</section>

<section
  id="kapitel-5-slide-02"
  class="module-slide"
  data-module="asset-management"
  data-chapter-key="kapitel-5"
  data-chapter-title="Kapitel 5 · Portfoliotheorie"
  data-chapter-short="Kapitel 5"
  data-slide-index="2"
  data-slide-total="12">
  ...
</section>

<!-- MODULE_CHAPTER_END: kapitel-5 -->
```

3. `topics/manifest.js` ergänzen:

```js
{
  id: "kapitel-5",
  short: "Kapitel 5",
  title: "Kapitel 5 · Portfoliotheorie",
  file: "topics/kapitel-5-portfoliotheorie.html",
  description: "Effiziente Portfolios, Markowitz und Diversifikation."
}
```

Danach erscheinen neue Themen automatisch in:
- Themen-Navigation
- Folien-Dropdown
- Suche
- Vor/Zurück-Flow

## Single-File-Fallback

Falls du alles ohne Nachladen und ohne Ordnerstruktur testen willst:
`single-file/asset-management-click.html`

Diese Datei enthält alles in einer HTML-Datei und hat ebenfalls Klicknavigation.
