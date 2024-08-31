# Makerspace Asset Management System

Dette projekt er et centraliseret system til at administrere og dele information om vores makerspace's udstyr, rum og materialer.

## Formål

Formålet med dette system er at:
1. Centralisere information om alt vores udstyr
2. Dele data med vores hjemmeside via et eksternt API
3. Implementere en digital log for brug af udstyr
4. Strukturere og organisere dokumentation, manualer og instruktioner for vores udstyr
5. Tilbyde en offentlig visning af vores udstyr og faciliteter
6. Muliggøre effektiv administration og vedligeholdelse af vores assets

## Funktioner og Struktur

Systemet består af flere hovedkomponenter:

### 1. Lukket Administrationssystem
- **Asset Management**: Et omfattende system til at oprette og administrere assets med al relevant data, herunder:
  - Guides og manualer
  - Billeder
  - Placering i makerspace
  - Ansvarlige personer
  - Vedligeholdelseshistorik
  - Tilknyttede instruktioner og dokumenter

### 2. Offentlig Visning
- **Tile-baseret Forside**: En offentligt tilgængelig side uden krav om autentifikation
  - Viser og filtrerer alt udstyr
  - Præsenterer relevante oplysninger til offentlig brug
  - Fungerer som applikationens "forside"

### 3. Mobil-venlig Asset Side
- **Unik URL for hvert Asset**: En "skjult" side med en lang, unik URL for hvert asset
  - Mobil-optimeret visning
  - Mulighed for at rapportere problemer med udstyret
  - Check-in funktion for brugere

### 4. API Integration
- **Ekstern API**: Eksponerer relevante informationer om maskinerne
  - Kan integreres direkte i vores hjemmeside
  - Tillader deling af data med andre systemer

## Teknologier

Dette projekt udvikles ved hjælp af følgende teknologier:

- **Backend**: Azure Static Web Apps til at hoste applikationen og håndtere API-adgang
- **Database**: Azure Cosmos DB med NoSQL-interface (planlagt, ikke implementeret endnu)
- **Frontend**: React med TypeScript
- **API**: Azure Functions baseret på Node.js og TypeScript til alle API-kald
- **Byggeværktøj**: Vite for hurtig udvikling og optimeret produktion
- **Dokumentation**: Markdown-filer gemt på GitHub
- **Styling**: CSS modules for komponent-specifik styling
- **Linting og Formattering**: ESLint og TypeScript ESLint for kodestandard og -kvalitet
- **Versionsstyring**: Git og GitHub for kildekode og samarbejde

## Projektstruktur

- `/src`: Kildekode for frontend
  - `/assets`: Statiske filer som billeder og ikoner
  - `/components`: React-komponenter
  - `/styles`: CSS-filer og stilark
  - `/pages`: Komponenter for hovedsider (Admin, Public View, Asset Page)
  - `/services`: API-integrationer og databehandling
- `/api`: Azure Functions for API-endpoints
- `/public`: Offentligt tilgængelige filer
- `/docs`: Projektdokumentation og brugermanualer
- `/tests`: Testfiler for både frontend og backend

## Kom i gang

1. Klon dette repository
2. Installer de nødvendige afhængigheder:
   ```
   npm install
   ```
3. Start udviklings-serveren:
   ```
   npm run dev
   ```
4. Åbn `http://localhost:5173` i din browser

For at bygge projektet til produktion:
```
npm run build
```

For at køre linting:
```
npm run lint
```

## API Endpoints

Projektet inkluderer flere Azure Functions for at håndtere forskellige aspekter af systemet:
- Asset oprettelse og redigering
- Offentlig data hentning
- Problemrapportering
- Check-in/ud funktionalitet

Detaljeret API-dokumentation vil blive tilføjet i `/docs/api.md`.

## Bidrag

Vi værdsætter bidrag fra vores community! Hvis du ønsker at bidrage til projektet, følg venligst disse trin:

1. Fork dette repository
2. Opret en ny branch for din feature eller fejlrettelse
3. Lav dine ændringer og commit dem
4. Push dine ændringer til din fork
5. Opret en pull request med en beskrivelse af dine ændringer

Sørg for at følge vores kodestandarder og kør tests før du indsender en pull request.

## Fremtidige Planer

- Implementere Azure Cosmos DB integration
- Tilføje flere Azure Functions for CRUD-operationer
- Udvikle en mere omfattende frontend med flere komponenter
- Implementere autentifikation og autorisation for admin-sektionen
- Tilføje avancerede søge- og filtreringsfunktioner i den offentlige visning
- Implementere et booking-system for udvalgt udstyr
- Tilføje statistik og brugsanalyse for assets
- Udvikle en mobilapp for nem adgang til asset-information og check-in

## Udvidelse af ESLint-konfiguration

For at forbedre linting i produktionsapplikationer anbefales følgende opdateringer til ESLint-konfigurationen:

1. Konfigurer `parserOptions` i `eslint.config.js`:

```js
export default tseslint.config({
  languageOptions: {
    // andre indstillinger...
    parserOptions: {
      project: ['./tsconfig.node.json', './tsconfig.app.json'],
      tsconfigRootDir: import.meta.dirname,
    },
  },
})
```

2. Erstat `tseslint.configs.recommended` med `tseslint.configs.recommendedTypeChecked` eller `tseslint.configs.strictTypeChecked`
3. Tilføj eventuelt `...tseslint.configs.stylisticTypeChecked`
4. Installer [eslint-plugin-react](https://github.com/jsx-eslint/eslint-plugin-react) og opdater konfigurationen:

```js
// eslint.config.js
import react from 'eslint-plugin-react'

export default tseslint.config({
  settings: { react: { version: '18.3' } },
  plugins: {
    react,
  },
  rules: {
    // andre regler...
    ...react.configs.recommended.rules,
    ...react.configs['jsx-runtime'].rules,
  },
})
```

## Licens

Dette projekt er licenseret under MIT-licensen. Se [LICENSE](LICENSE) filen for detaljer.

Copyright (c) 2024 Makerspace Asset Management System
