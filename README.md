# FAST-Computing Brand CSS# FAST-Computing Brand CSS



Sistema di gestione CSS aziendale modulare basato su Bootstrap 5, con supporto per 3 brand separati:CSS aziendali basati su Bootstrap 5, personalizzati con SASS per il brand FAST-Computing.

- **Corporate** - CSS aziendale generico

- **Argos** - Portale web Argos## 📁 Struttura del progetto

- **Atlas** - Portale web Atlas

```

## 📁 Struttura del progettobrand/

├── src/

```│   └── scss/

brand/│       ├── brand.scss          # File principale SASS

├── src/│       ├── _variables.scss     # Variabili custom (colori, font, ecc.)

│   ├── scss/│       └── _custom.scss        # Stili custom aggiuntivi

│   │   ├── _common/                    # File condivisi tra tutti i brand├── dist/

│   │   │   ├── _fonts.scss             # Font comuni (Google Fonts)│   └── css/

│   │   │   ├── _variables-base.scss    # Variabili base comuni│       ├── brand.css           # CSS compilato

│   │   │   └── _mixins.scss            # Mixin e funzioni comuni│       └── brand.min.css       # CSS compilato e minificato

│   │   │├── .github/

│   │   ├── corporate/                  # Brand Corporate (aziendale generico)│   └── workflows/

│   │   │   ├── corporate.scss          # File principale Corporate│       └── build-css.yml       # GitHub Action per build automatico

│   │   │   ├── _variables.scss         # Variabili Corporate└── package.json

│   │   │   └── _custom.scss            # Stili custom Corporate```

│   │   │

│   │   ├── argos/                      # Brand Argos (portale)## 🚀 Installazione

│   │   │   ├── argos.scss              # File principale Argos

│   │   │   ├── _variables.scss         # Variabili Argos```bash

│   │   │   └── _custom.scss            # Stili custom Argosnpm install

│   │   │```

│   │   └── atlas/                      # Brand Atlas (portale)

│   │       ├── atlas.scss              # File principale Atlas## 🛠️ Comandi disponibili

│   │       ├── _variables.scss         # Variabili Atlas

│   │       └── _custom.scss            # Stili custom Atlas### Build CSS (produzione)

│   │```bash

│   └── fonts/                          # Font custom self-hosted (opzionali)npm run build

│```

├── dist/Compila i file SASS in CSS normale e minificato nella cartella `dist/css/`.

│   └── css/

│       ├── corporate.css               # CSS Corporate compilato### Watch mode (sviluppo)

│       ├── corporate.min.css           # CSS Corporate minificato```bash

│       ├── argos.css                   # CSS Argos compilatonpm run watch

│       ├── argos.min.css               # CSS Argos minificato```

│       ├── atlas.css                   # CSS Atlas compilatoMonitora le modifiche ai file SASS e ricompila automaticamente.

│       └── atlas.min.css               # CSS Atlas minificato

│### Pulizia

└── examples/                           # Esempi HTML per ogni brand```bash

```npm run clean

```

## 🚀 InstallazioneRimuove la cartella `dist/`.



```bash## 🎨 Personalizzazione

npm install

```### Modificare i colori del brand

Modifica il file `src/scss/_variables.scss`:

## 🛠️ Comandi disponibili

```scss

### Build tutti i brand$primary:   #0066cc;  // Colore principale

```bash$secondary: #6c757d;  // Colore secondario

npm run build// ... altri colori

# oppure```

npm run build:all

```### Aggiungere font custom



### Build singoli brand#### Opzione 1: Google Fonts (consigliato)

```bash1. Apri `src/scss/_fonts.scss`

npm run build:corporate    # Solo Corporate2. Modifica l'URL di import con i tuoi font da [Google Fonts](https://fonts.google.com)

npm run build:argos        # Solo Argos3. Aggiorna `src/scss/_variables.scss` con il nome del font

npm run build:atlas        # Solo Atlas

``````scss

// In _fonts.scss

### Watch mode (sviluppo)@import url('https://fonts.googleapis.com/css2?family=TuoFont:wght@400;700&display=swap');

```bash

npm run watch:corporate    # Monitora Corporate// In _variables.scss

npm run watch:argos        # Monitora Argos$font-family-sans-serif: 'TuoFont', sans-serif !default;

npm run watch:atlas        # Monitora Atlas```

```

#### Opzione 2: Font Self-Hosted (aziendali)

### Pulizia1. Metti i file font (.woff2, .woff) in `src/fonts/`

```bash2. Decommenta e personalizza le regole `@font-face` in `src/scss/_fonts.scss`

npm run clean              # Rimuove tutti i CSS compilati3. Aggiorna `$font-family-sans-serif` in `_variables.scss`

```

Consulta `src/fonts/README.md` per istruzioni dettagliate.

## 🎨 Personalizzazione

### Aggiungere stili custom

### Struttura dei brandAggiungi i tuoi stili in `src/scss/_custom.scss`:



Ogni brand ha 3 file principali:```scss

.mia-classe-custom {

1. **`{brand}.scss`** - File principale che importa tutto nell'ordine corretto  background-color: $primary;

2. **`_variables.scss`** - Variabili specifiche del brand (colori, font, ecc.)  padding: 1rem;

3. **`_custom.scss`** - Stili CSS custom del brand}

```

### Modificare i colori di un brand

### Modificare variabili Bootstrap

Esempio per modificare Argos:Tutte le variabili Bootstrap possono essere sovrascritte in `_variables.scss`. 

Consulta la [documentazione Bootstrap](https://getbootstrap.com/docs/5.3/customize/sass/) per l'elenco completo.

```scss

// src/scss/argos/_variables.scss## 🤖 GitHub Actions

$primary:       #2c3e50;  // Blu scuro

$secondary:     #95a5a6;  // GrigioIl repository include una GitHub Action che:

$argos-accent:  #3498db;  // Blu accento- Compila automaticamente i CSS ad ogni push sul branch `master`/`main`

```- Genera artifacts scaricabili per ogni build

- Committa automaticamente i CSS compilati nel repository

### Aggiungere stili custom

### Configurazione necessaria

```scss

// src/scss/argos/_custom.scssPer permettere alla GitHub Action di committare i file compilati:

.mia-classe-argos {

  background-color: $argos-accent;1. Vai in **Settings** → **Actions** → **General**

  padding: 1rem;2. Sotto "Workflow permissions", seleziona **Read and write permissions**

}3. Salva le modifiche

```

## 📦 Utilizzo dei CSS

### Condividere codice tra brand

### In HTML

I file in `src/scss/_common/` sono condivisi da tutti i brand:```html

<link rel="stylesheet" href="dist/css/brand.min.css">

- **`_fonts.scss`** - Font comuni (Google Fonts o self-hosted)```

- **`_variables-base.scss`** - Variabili di base che ogni brand può sovrascrivere

- **`_mixins.scss`** - Mixin e funzioni riutilizzabili### Via CDN (dopo il rilascio)

```html

### Aggiungere font custom<!-- Sostituisci con il tuo CDN o GitHub Pages URL -->

<link rel="stylesheet" href="https://cdn.example.com/brand/brand.min.css">

Vedi la guida completa in [FONTS_GUIDE.md](./FONTS_GUIDE.md)```



Quick esempio per Google Fonts:### Import in SASS/SCSS

```scss```scss

// src/scss/_common/_fonts.scss@import 'path/to/brand';

@import url('https://fonts.googleapis.com/css2?family=TuoFont:wght@400;700&display=swap');```



// src/scss/corporate/_variables.scss## 📝 Note

$font-family-sans-serif: 'TuoFont', sans-serif !default;

```- I file CSS compilati sono generati automaticamente - non modificarli manualmente

- Tutte le modifiche devono essere fatte nei file `.scss` in `src/scss/`

## 📦 Utilizzo dei CSS- La GitHub Action aggiunge `[skip ci]` al messaggio di commit per evitare loop infiniti



### Corporate## 📄 Licenza

```html

<link rel="stylesheet" href="dist/css/corporate.min.css">MIT

```

### Argos
```html
<link rel="stylesheet" href="dist/css/argos.min.css">
```

### Atlas
```html
<link rel="stylesheet" href="dist/css/atlas.min.css">
```

## 🎯 Caratteristiche dei Brand

### Corporate (Aziendale Generico)
- **Colori**: Blu corporate professionale (#0066cc)
- **Stile**: Classico, pulito, professionale
- **Componenti**: Header gradient, footer scuro, card eleganti
- **Uso**: Sito corporate aziendale principale

### Argos (Portale Dashboard)
- **Colori**: Blu scuro (#2c3e50), grigio argento
- **Stile**: Dashboard professionale, layout sidebar
- **Componenti**: Sidebar fissa, navbar top, stat cards, tabelle
- **Uso**: Applicazioni web, dashboard, pannelli admin

### Atlas (Portale Moderno)
- **Colori**: Viola/Purple (#6f42c1), gradienti colorati
- **Stile**: Moderno, colorato, dinamico
- **Componenti**: Hero gradient, card elevate, bottoni rounded
- **Uso**: Portali web moderni, landing page, app consumer

## 🤖 GitHub Actions

Il repository include una GitHub Action che:
- Compila automaticamente **tutti e 3 i brand** ad ogni push
- Genera artifacts scaricabili per ogni build
- Committa automaticamente i CSS compilati (opzionale)

### Configurazione necessaria

Per il commit automatico:
1. Vai in **Settings** → **Actions** → **General**
2. Sotto "Workflow permissions", seleziona **Read and write permissions**

## 🆕 Aggiungere un nuovo brand

1. Crea una nuova cartella in `src/scss/nuovo-brand/`
2. Copia i 3 file da un brand esistente:
   - `nuovo-brand.scss`
   - `_variables.scss`
   - `_custom.scss`
3. Personalizza i colori e gli stili
4. Aggiungi gli script npm in `package.json`:
   ```json
   "build:nuovo-brand": "...",
   "build:nuovo-brand:expanded": "...",
   "build:nuovo-brand:minified": "..."
   ```
5. Aggiorna `build:all` per includere il nuovo brand

## 📝 Best Practices

1. **Non modificare Bootstrap direttamente** - Usa sempre le variabili
2. **Mantieni i file `_common/`** - Condividi codice tra brand
3. **Usa i mixin comuni** - Evita duplicazione del codice
4. **Test su tutti i brand** - Quando modifichi `_common/`
5. **Commit separati** - Per modifiche specifiche di un brand

## 🐛 Troubleshooting

### Build fallisce
```bash
npm run clean
npm install
npm run build
```

### Font non si caricano
Verifica il percorso in `_common/_fonts.scss` e controlla la console browser

### Modifiche non visibili
1. Ricompila: `npm run build:{brand}`
2. Svuota cache browser (Ctrl+Shift+R)
3. Verifica di usare il CSS corretto

## 📄 Licenza

MIT
