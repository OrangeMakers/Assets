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

- Backend: Azure Static Web Apps til at hoste applikationen og håndtere API-adgang
- Database: Azure Cosmos DB med NoSQL-interface
- Frontend: Next.js med React
- API: Azure Functions baseret på Node.js til alle API-kald
- Dokumentation: Markdown-filer gemt på GitHub

## Projektstruktur

- `/src`: Kildekode for frontend og backend
  - `/frontend`: Next.js applikation
  - `/api`: Azure Functions for API-endpoints
- `/docs`: Projektdokumentation og brugermanualer
- `/scripts`: Hjælpescripts og værktøjer
- `/tests`: Testfiler for både frontend og backend

## Kom i gang

1. Klon dette repository
2. Installer de nødvendige afhængigheder:
   ```
   npm install
   ```
3. Konfigurer Azure-tjenester (Static Web Apps, Cosmos DB, Functions)
4. Start udviklings-serveren:
   ```
   npm run dev
   ```
5. Åbn `http://localhost:3000` i din browser

For mere detaljerede instruktioner, se vores [Udviklerdokumentation](docs/developer-guide.md).

## Bidrag

Vi værdsætter bidrag fra vores community! Hvis du ønsker at bidrage til projektet, følg venligst disse trin:

1. Fork dette repository
2. Opret en ny branch for din feature eller fejlrettelse
3. Lav dine ændringer og commit dem
4. Push dine ændringer til din fork
5. Opret en pull request med en beskrivelse af dine ændringer

For mere information, se vores [Bidragsguide](CONTRIBUTING.md).

## Licens

Dette projekt er licenseret under MIT-licensen. Se [LICENSE](LICENSE) filen for detaljer.
