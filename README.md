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
- **Styling**: Tailwind CSS for konsistent og skalerbar design på tværs af hele løsningen
- **Linting og Formattering**: ESLint og TypeScript ESLint for kodestandard og -kvalitet
- **Versionsstyring**: Git og GitHub for kildekode og samarbejde

## Design Framework

For at sikre en konsistent og skalerbar designløsning på tværs af hele projektet, bruger vi Tailwind CSS. Tailwind er et utility-first CSS framework, der giver os mulighed for at opbygge brugerdefinerede designs uden at forlade vores HTML.

### Implementering af Tailwind CSS

1. Installer Tailwind CSS og dets afhængigheder:
   ```
   npm install -D tailwindcss@latest postcss@latest autoprefixer@latest
   ```

2. Generer Tailwind konfigurationsfilen:
   ```
   npx tailwindcss init -p
   ```

3. Konfigurer dine template paths i `tailwind.config.js`:
   ```javascript
   module.exports = {
     content: [
       "./src/**/*.{js,ts,jsx,tsx}",
     ],
     theme: {
       extend: {},
     },
     plugins: [],
   }
   ```

4. Tilføj Tailwind directives til din hovedstylsheet fil (f.eks. `src/styles/globals.css`):
   ```css
   @tailwind base;
   @tailwind components;
   @tailwind utilities;
   ```

5. Importer din hovedstylsheet fil i `src/main.tsx`:
   ```typescript
   import './styles/globals.css'
   ```

6. Brug Tailwind klasser i dine komponenter:
   ```jsx
   <div className="bg-blue-500 text-white p-4 rounded-lg shadow-md">
     Dette er et eksempel på en Tailwind-stylet div
   </div>
   ```

Ved at bruge Tailwind CSS kan vi nemt opretholde en konsistent designsprog på tværs af hele applikationen, samtidig med at vi bevarer fleksibiliteten til at tilpasse designet efter behov.

## Projektstruktur

- `/`: Rodmappe med konfigurationsfiler
  - `.gitignore`: Git-ignorerede filer
  - `package.json` og `package-lock.json`: NPM-pakkeadministration
  - `tsconfig.json`, `tsconfig.app.json`, `tsconfig.node.json`: TypeScript-konfiguration
  - `vite.config.ts`: Vite byggeværktøj konfiguration
  - `eslint.config.js`: ESLint konfiguration
  - `swa-cli.config.json`: Azure Static Web Apps CLI konfiguration
- `/src`: Kildekode for frontend
  - `/assets`: Statiske filer som billeder og ikoner (f.eks. `react.svg`)
  - `/components`: React-komponenter (skal implementeres)
  - `/styles`: CSS-filer og stilark (f.eks. `App.css`, `index.css`)
  - `/pages`: Komponenter for hovedsider (Admin, Public View, Asset Page) (skal implementeres)
  - `/services`: API-integrationer og databehandling (skal implementeres)
  - `App.tsx`: Hoved React-komponent
  - `main.tsx`: Indgangspunkt for React-applikationen
  - `vite-env.d.ts`: TypeScript-deklarationsfil for Vite
- `/api`: Azure Functions for API-endpoints
  - `host.json`: Konfigurationsfil for Azure Functions
  - `package.json` og `package-lock.json`: NPM-pakkeadministration for API
  - `tsconfig.json`: TypeScript-konfiguration for API
  - `.funcignore` og `.gitignore`: Ignorerede filer for Azure Functions og Git
  - `/src/functions`: Azure Functions-kode (f.eks. `helloWorld.ts`)
- `/public`: Offentligt tilgængelige filer (f.eks. `vite.svg`)
- `/docs`: Projektdokumentation og brugermanualer (skal implementeres)
- `/tests`: Testfiler for både frontend og backend (skal implementeres)

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
