# Makerspace Asset Management System

Dette projekt er et centraliseret system til at administrere og dele information om vores makerspace's udstyr, rum og materialer.

## Formål

Formålet med dette system er at:
1. Centralisere information om alt vores udstyr
2. Dele data med vores hjemmeside via et eksternt API
3. Implementere en digital log for brug af udstyr
4. Strukturere og organisere dokumentation, manualer og instruktioner for vores udstyr

## Hovedfunktioner

- **Udstyrsregistrering**: En database over alle maskiner, værktøjer og andet udstyr
- **Rumoversigt**: Information om forskellige sektioner og rum i vores makerspace
- **Materialelager**: Oversigt over tilgængelige materialer
- **Digital Log**: Registrering af udstyrsanvendelse og vedligeholdelse
- **Dokumentationsbibliotek**: Struktureret opbevaring af manualer, instruktioner og anden dokumentation
- **API Integration**: Deling af relevante data med vores hjemmeside

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
- `/api`: Azure Functions for API-endpoints
- `/public`: Offentligt tilgængelige filer
- `/docs`: Projektdokumentation og brugermanualer (planlagt)
- `/tests`: Testfiler for både frontend og backend (planlagt)

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

Projektet inkluderer en simpel "Hello World" Azure Function, som kan findes i `api/src/functions/helloWorld.ts`. Denne funktion kan kaldes via HTTP GET eller POST og returnerer en hilsen.

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
- Implementere autentifikation og autorisation
- Tilføje unit tests og integrationstest

## Licens

Dette projekt er licenseret under MIT-licensen. Se [LICENSE](LICENSE) filen for detaljer.

Copyright (c) 2024 Makerspace Asset Management System
