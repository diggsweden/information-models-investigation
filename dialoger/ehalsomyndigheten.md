# Dialog med Grunddatadomän hälsa, vård och omsorg.
I huvudsak representerat av E-hälsomyndigheten.

## A. Hur jobbar ni med informationsmodeller idag.

### A1. Hur många är inblandade och i vilken omfattning?
Nyutveckling ca. 7-10 stycken i taget.
Förvaltning ca. 30 stycken som är inne lite då och då.

### A2. Pågår arbetet stötvis eller kontinuerligt?
Både och.

### A3. Är det ett jobb som görs i samband med framtagning av nya system i huvudsak?
Ja, men också i samband med konfigurering av system och tjänster.

### A4. Vilken modelleringsstil använder ni er av (t.ex. är det UML, i så fall vilka diagram)?
UML klassdiagram.

### A5. Har ni några interna regler kring hur verktyget ska användas (t.ex. modelleringsprinciper som ska följas, undvikas etc.)?
Ja, MDG teknologier som realiserar modelleringsprinciper. Verktygsstöd finns också. Aggregat och komposition används.

### A6. Separerar ni mellan olika nivåer av modellering? (T.ex. inom ramverket för grunddata talar man om begreppsmodeller, grunddatadomänmodeller och informationsutbytesmodeller.)
Ja, begreppsmodeller används.
Vidare finns NI från socialstyrelsen som är en slags grundläggande grunddatadomänmodel att utgå / förfina sin modell utifrån.

## B. Hur samarbetar ni kring informationsmodeller?

### B1. Är det grupparbete vid vita tavlan som sen uppdateras i verktyget av en person i efterhand?
Både och.

### B2. Hur delar / förvarar ni modellerna, delad folder på intranät?
Intern databas, olika repositorys för olika mognad, typ beslutat, arkiv, pågående.

### B3. Har ni versionshantering av modellerna?
Modeller får versionsnummer. Ny version skapas genom en kopia med en nytt versionsnummer. Export till XMI för olika projekt för manuell backup.

### B4. Hur refererar ni till delar av informationsmodellerna (gör ni det)?
Länkar till prolaborate internwebb. Leta fram utifrån namn och modell. Export till bild.

## C. Sker någon återanvändning av informationsmodeller?

### C1. Återanvänder ni andras informationsmodeller på något sätt?
Framförallt NI från Socialstyrelsen. Också grunddata person från Skatteverket med ytterligare attribut. Också företag från bolagsverket.

### C2. Gör ni era informationsmodeller synliga utanför den egna organisationen?
Ja. T.ex. Nationella LäkemedelsListan. Export i form av bild, pdf och html.

### C3. Känner ni till om någon vidareutnyttjar era informationsmodeller?
Oklart.

### C4. Har ni krav på er att återanvända eller uppmuntra återanvändning av informationsmodeller?
Ej i lag, föreskrift eller förordning.

## D. Vilka verktyg använder ni?
Sparx EA, Sparx Prolaborate
Socialstyrelsen: Visual Paradigm
Simplifier i samband med FHIR

### D1. Exporterar ni till andra format (t.ex. utöver .eap exportera till xmi eller rena bilder)?
HTML, pdf, bild i samband.

### D2. Använder ni några extra funktioner, t.ex. UML stereotyper eller liknande?
Eventuellt extra stöd för koppling till kodverk.  MDG teknologier.

### D3. Finns det behov som inte är tillgodosedda med verktygen ni jobbar med?
Mer intuitivt gränssnitt i Sparx.

### D4. Finns modellerna lättillgängliga utanför verktygen?
Ja i HTML, pdf och bild.

### D5. Är det viktigt att kunna bestämma exakt hur diagrammen ser ut? (Dvs. flyttar ni runt klasser och relationer, eller låter ni systemet göra layouten själv?)
Det är viktigt. Olika vyer för olika mottagare.

## E. Hur använder ni er av informationsmodeller?

### E1. För kommunikation inför framtagande av system?
Ja.

### E2. För dokumentation syfte och framtida underhåll av system?
Ja.

### E3. För kravställning av system?
Ja.

### E4. För roundtrip engineering?
Nej.

### E5. För kommunikation mellan olika grupperingar, t.ex. arkitekturgrupp och utvecklargrupp.
Ja.

### E6. För att stärka ett enhetligt språkbruk och förståelse inom organisationen?
Ja.

## F. Hur skulle ett nationellt systemstöd för informationsmodeller påverka er?

### F1. Skulle ni undersöka möjligheten att byta?
Ja.

### F2. Skulle ni sträva efter att hitta en möjlighet att automatisera så informationsmodellerna finns både lokalt och centralt?
Ja.

### F3. Är ni villiga att anpassa arbetssättet i era nuvarande verktyg för att öka interoperabiliteten med interoperabilitet med andra aktörer (och därmed också med det nationella systemstödet)?
Ja.

### F4. Skulle ni kunna tänka er att underhålla en delmängd av informationsmodellerna i båda systemen?
Ja, men motvilligt och kanske en mindre del av informationsmodellerna.

### F5. Föredrar ni en enklare lösning där ni kan lägga upp era informationsmodeller i ett bibliotek och undvika att använda ett nationellt systemstöd?
Bibliotek är ett första steg. Gemensamma verktyg kommer som steg 2.


## Övrigt
Relevanta länkar att titta på:
* [Arkitekturgemenskap anordnat av INERA](https://inera.atlassian.net/wiki/spaces/AR/pages/529695302/Modelltyp+-+F+rm+gekarta)
* [Socialstyrelsens informationsmodeller](https://informationsstruktur.socialstyrelsen.se/default)
* [Fhir Simplifier](https://simplifier.net/packages/hl7.fhir.r4.core/4.0.1/files/79955)
* [Clinical Knowledge Manager](https://ckm.openehr.org/ckm/archetypes/1013.1.631)