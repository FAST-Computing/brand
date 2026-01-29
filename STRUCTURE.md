# Struttura CSS Multi-Brand - FAST-Computing

## ✅ Completato!

La struttura è stata riorganizzata con successo per gestire 3 brand separati:

### 📂 Struttura Creata

```
src/scss/
├── _common/                    ← File condivisi tra tutti i brand
│   ├── _fonts.scss            ← Font Google (Inter + Roboto Mono)
│   ├── _variables-base.scss   ← Variabili base comuni
│   └── _mixins.scss           ← Mixin riutilizzabili
│
├── corporate/                  ← Brand Corporate (generico aziendale)
│   ├── corporate.scss         ← File principale
│   ├── _variables.scss        ← Colori: Blu corporate (#0066cc)
│   └── _custom.scss           ← Header gradient, footer, cards
│
├── argos/                      ← Brand Argos (portale dashboard)
│   ├── argos.scss             ← File principale
│   ├── _variables.scss        ← Colori: Blu scuro (#2c3e50)
│   └── _custom.scss           ← Sidebar, navbar, stat cards, tabelle
│
└── atlas/                      ← Brand Atlas (portale moderno)
    ├── atlas.scss             ← File principale
    ├── _variables.scss        ← Colori: Viola (#6f42c1) + gradienti
    └── _custom.scss           ← Hero gradient, cards elevate, modern design
```

### 🎯 CSS Generati

```
dist/css/
├── corporate.css       (218 KB) ← CSS Corporate completo
├── corporate.min.css   (177 KB) ← CSS Corporate minificato
├── argos.css           (221 KB) ← CSS Argos completo
├── argos.min.css       (179 KB) ← CSS Argos minificato
├── atlas.css           (219 KB) ← CSS Atlas completo
└── atlas.min.css       (178 KB) ← CSS Atlas minificato
```

### 🚀 Comandi NPM

```bash
# Build tutto
npm run build                 # Compila tutti e 3 i brand

# Build singoli
npm run build:corporate       # Solo Corporate
npm run build:argos          # Solo Argos
npm run build:atlas          # Solo Atlas

# Watch mode (sviluppo)
npm run watch:corporate      # Monitora Corporate
npm run watch:argos         # Monitora Argos
npm run watch:atlas         # Monitora Atlas

# Pulizia
npm run clean               # Rimuove tutti i CSS compilati
```

### 🎨 Caratteristiche Brand

#### 1. **Corporate** (Aziendale Generico)
- **Colori**: Blu corporate #0066cc, Blu scuro #003366
- **Stile**: Professionale, elegante, con gradienti
- **Componenti**:
  - `.corporate-header` - Header con gradient
  - `.corporate-footer` - Footer scuro
  - `.corporate-card` - Card con hover effect
  - `.btn-corporate` - Bottone brand
  - `.corporate-hero` - Sezione hero
- **Uso**: Sito corporate principale

#### 2. **Argos** (Portale Dashboard)
- **Colori**: Blu scuro #2c3e50, Grigio #95a5a6, Accent #3498db
- **Stile**: Dashboard professionale, layout applicativo
- **Componenti**:
  - `.argos-wrapper` - Layout wrapper con sidebar
  - `.argos-sidebar` - Sidebar fissa laterale
  - `.argos-navbar` - Top navbar
  - `.argos-card` - Dashboard card
  - `.argos-stat-card` - Statistiche
  - `.argos-table` - Tabelle con hover
  - `.btn-argos` - Bottoni
- **Uso**: Applicazioni web, dashboard, pannelli amministrativi

#### 3. **Atlas** (Portale Moderno)
- **Colori**: Viola #6f42c1, Purple #8b5cf6, Pink #ec4899
- **Stile**: Moderno, colorato, con gradienti e animazioni
- **Componenti**:
  - `.atlas-hero` - Hero con gradient e pattern
  - `.atlas-navbar` - Navbar moderna con gradient text
  - `.atlas-card` - Card elevate con shadow
  - `.atlas-card-gradient` - Card con gradient background
  - `.atlas-feature` - Feature cards con icone
  - `.atlas-footer` - Footer scuro moderno
  - `.btn-atlas` - Bottoni con gradient
  - `.badge-atlas` - Badge rounded
- **Uso**: Portali web moderni, landing pages, app consumer

### 🔧 Come Personalizzare

#### Modificare i colori di un brand:
```scss
// Esempio: src/scss/argos/_variables.scss
$primary: #2c3e50;        // Cambia il colore principale
$argos-accent: #3498db;   // Cambia l'accent color
```

#### Aggiungere nuovi stili:
```scss
// Esempio: src/scss/atlas/_custom.scss
.mio-componente-atlas {
  background: $atlas-gradient-primary;
  padding: 2rem;
  border-radius: 1rem;
}
```

#### Condividere codice tra brand:
Modifica i file in `src/scss/_common/` per cambiamenti che valgono per tutti i brand.

### 📦 Utilizzo nei Progetti

```html
<!-- Sito Corporate -->
<link rel="stylesheet" href="dist/css/corporate.min.css">

<!-- Portale Argos -->
<link rel="stylesheet" href="dist/css/argos.min.css">

<!-- Portale Atlas -->
<link rel="stylesheet" href="dist/css/atlas.min.css">
```

### 🤖 GitHub Action

La GitHub Action è già configurata per compilare automaticamente tutti e 3 i brand ad ogni push.

### 📝 Prossimi Passi

1. **Personalizza i colori** in ciascun `_variables.scss`
2. **Aggiungi componenti custom** in ciascun `_custom.scss`
3. **Crea esempi HTML** nella cartella `examples/`
4. **Test** - Apri gli esempi HTML nel browser
5. **Commit & Push** - La GitHub Action builderà automaticamente

### 🎓 Best Practices

- ✅ Modifica solo i file SCSS, mai i CSS compilati
- ✅ Usa `_common/` per codice condiviso
- ✅ Usa `_variables.scss` per configurazione
- ✅ Usa `_custom.scss` per stili specifici
- ✅ Test su tutti i brand dopo modifiche a `_common/`
- ✅ Un brand = un progetto web

### 📚 Documentazione

- [README.md](./README.md) - Documentazione completa
- [FONTS_GUIDE.md](./FONTS_GUIDE.md) - Guida ai font custom

---

**Buon lavoro! 🚀**
