# Nulägesanalys

I denna leverabel kommer vi analysera hur existerande lösningar kan bemöta de fyra gradvis mer komplexa scenariorna A-D som etablerades i behovsanalysen. De fyra scenariorna kan brytas ned i följande 7 olika komponenter (se [separat dokument](scenarior-modeller.md) för en längre introduktion till komponenterna):

| Förkortning | Komponent                                         |
|-------------|---------------------------------------------------|
| 1. IM_NB    | Nationellt bibliotek av informationsmodeller      |
| 2. IM_SK    | Skördning av informationsmodeller                 |
| 3. IE_LD    | Hantera informationselement som länkade data      |
| 4. IE_NB    | Nationellt biblioteket med informationselement    |
| 5.  UML     | Extrahera informationselement ur UML klassdiagram |
| 6.  VER     | Nationellt verktyg för informationselement        |
| 7.  DIA     | Diagramstöd för informationsmodeller              |

De lösningar som beaktas är system som är i drift i Sverige, våra nordiska grannländer eller i Europa. En ytterligare begränsning är att enbart system som är tillgängliga som öppen källkod beaktas.

Följande fem lösningar har identifierats för en djupare analys:

1. Sveriges dataportal
2. Finska Tietomallit
3. Norska Felles datakatalog
4. EntryScape Models
5. Flamländska OSLO ramverket

I följande kapitel går vi igenom de fem lösningarna i mer detalj, både hur de förvaltas och vilka av de 7 komponenterna de tillhandahåller.

## Sveriges dataportal

Sveriges dataportal kan delas in i följande tre delar:

**dataportal.se** - En webbsite där man kan söka efter datamängder, begrepp och specifikationer.<br>
**admin.dataportal.se** - Ett gränssnitt där man kan administrera skördning av olika källor men även se status och statistik.<br>
**editera.dataportal.se** - Ett redaktionellt verktyg för att beskriva datamängder, begrepp och specifikationer.

Var och en av delarna ovan finns i två utföranden, en skarp miljö och en testmiljö. Testmiljön är öppen för alla och kan användas både för utbildningssyfte och av utvecklare som vill testa skördning.

Dataportalen är byggd på länkade data principer och strävar att i så stor utsträckning som möjligt lagra datamängder, begrepp, och specifikationer direkt i enlighet med etablerade standarder/specifikationer som DCAT-AP-SE, SKOS och PROF-SE.

### Utveckling och förvaltningsperspektiv
Dataportal.se är en öppen källkodsapplikation baserad på React som kommunicerar med det API som admin.dataportal.se tillhandahåller. Admin.dataportal.se och editera.dataportal.se är båda anpassningar av öppen källkod-plattformen EntryScape. Plattformen EntryScape används idag av ett 40-tal organisationer i Sverige och några ytterligare i Europa, bland annat Europeiska kommissionen. EntryScape etablerades som plattform 2011 och har sedan dess utvecklats kontinuerligt av företaget Metasolutions som också erbjuder kommersiell support. Utvecklargruppen består idag av cirka 8 personer.

### Komponenter som stöds
| Komponent | Stöds | Kommentar |
|-----------|-------|------|
| 1. IM_NB  | x     | På editera.dataportal.se kan man registrera specifikationer som består av flera specifikationsdelar. Det är lämpligt att lägga upp informationsmodeller som specifikationsdelar. |
| 2. IM_SK  | x     | Specifikationer skördas till dataportalen både från verktyget editera.dataportal.se och från andra källor. |
| 3. IE_LD  | -     | Informationsmodeller är bara resurser, dvs de kan vara bilder eller andra rikare format utan att dataportalen gör något med dem. Men, då dataportalen är byggd på ett generellt sätt utifrån länkade data principer ovanpå en triplestore finns inget som hindrar att man försöker extrahera informationselement ur dem framöver. |
| 4. IE_NB  | -     | Det är möjligt att komplettera dataportalen med ett sökgränssnitt för informationselement om de finns tillgängliga i API:et. |
| 5.  UML   | -     | Skördningsprocessen går att utvidga, t.ex. med stöd för att förstå XMI formatet förutsatt att informationselement har en egen representation. |
| 6.  VER   | -     | Verktyg för att jobba med informationselement kan läggas till på editera, se EntryScape Models nedan alternativt som ett helt separat verktyg som man skördar in informationselement från. |
| 7.  DIA   | -     | visualiseringsstöd bör finnas i redigeringsverktyget och därefter också visas i sökgränssnittet på dataportalen. |

## Finska Tietomallit

Tietomallit (interoperabilitetsplattformen) är en av tre närliggande plattformar utvecklade för att hantera informationsmodeller, begrepp och referensdata. Till skillnad från Sveriges dataportal gör Tietomallit ingen skillnad mellan en sökorienterad portal och ett redaktionellt verktyg. Verktyget är helt baserat på länkade data och tillåter användarna att skapa både klasser och egenskaper samt återanvända dem i olika applikationsprofiler. Vidare använder verktyget en kombination av SKOS, RDFS, Dublin Core Application Profiles, SHACL och egna properties för att realisera uttrycken.

### Utveckling och förvaltningsperspektiv
Ur ett implementationsperspektiv utvecklas Tietomallit av Myndigheten för digitalisering och befolkningsdata (DVV) och tillhandahålls som öppen källkod. Ytterligare några aktörer i Europa har visat intresse för plattformen, inklusive svenska Bolagsverket. Det finns signaler som tyder på att man är öppen för samarbete kring hur plattformen ska vidareutvecklas. Det finns idag ingen tydlig förvaltningsmodell som tar hänsyn till andra aktörers intressen, dock finns en utvecklargrupp om 3-5 personer som jobbar aktivt med plattformen. Det finns inte heller i dagsläget någon etablerad kommersiell support kring plattformen.

### Komponenter som stöds
| Komponent | Status | Kommentar |
|-----------|--------|------|
| 1. IM_NB  | x      | Informationsmodeller är samlade i ett bibliotek och kan utforskas antingen via kategorier eller via fritextsökning. |
| 2. IM_SK  | -      | Verktyget stöder inte skördning av. |
| 3. IE_LD  | x      | Informationselement sparas i en triplestore med hjälp av relevanta RDF vokabulärer som RDFS, SHACL och DCAP. |
| 4. IE_NB  | -      | Funktionaliteten som finns ger en översikt över modeller inte enskilda återanvändbara informationselement. Visst stöd finns för den som är inloggad och ska välja vad som ska anpassa en existerande informationselement. |
| 5. UML    | -      | Tietomallit stöder inte import från UML format som XMI och saknar tyvärr möjlighet att skörda in informationsmodeller även från andra format. Det innebär att man antingen får skapa allt manuellt i gränssnittet eller använda API:et för att maskinellt importera informationsmodeller (oklart hur komplicerat det är). |
| 6. VER    | x      | Då Tietomallit är ett verktyg för att jobba med informationsmodeller är detta själva kärnan i verktyget. |
| 7. DIA    | x      | Varje informationsmodell visualiseras i ett UML liknande diagram som kan justeras för optimal presentation. |

### Versionshantering och accesskontroll
Accesskontroll baseras på en kombination av organisationstillhörighet och roller. Versionshanteringen löses i huvudsak genom att man låser en modell och skapar en kopia av modellen där man kan jobba vidare. 

## Felles datakatalog
Den norska dataportalen, Felles datakatalog, är en öppen källkodsprodukt som hanterar datamängder, begrepp, informationsmodeller och nyligen lanserades också offentliga tjänster och händelser. Plattformen är byggd som ett antal microservices som realiserar standarder som DCAT-AP-NO för datamängder, SKOS för begrepp, användargränssnitt för registrering och sökgränssnitt i portalen. Lagringen sker i Mongodb samtidigt som en triplestore hålls uppdaterad för att exponera en SPARQL endpoint. Informationsmodeller upptäcks som API beskrivningar som pekas ut från datatjänster. Då informationsmodellerna baseras på OpenAPI och JSON Schema blir effekten att semantisk interoperabilitet saknas.  

### Utveckling och förvaltningsperspektiv
Felles datakatalog förvaltas av Digitaliseringsdirektoratet som är en relativt ny myndighet med drygt 300 anställda. Utvecklargruppen som jobbar med lösningen består av cirka ett 10-tal personer. Mycket av den tekniska dokumentationen kring lösningen är tillgänglig online, även målbild och de processer som används för att identifiera behov är dokumenterade. Flera saker tyder på att man i dagsläget inte förutser en bredare spridning av lösningen. T.ex. det faktum att mycket av dokumentationen är på norska och att man hårdkodat den norska versionen av standarder som DCAT-AP.

### Komponenter som stöds
| Komponent | Status | Kommentar |
|-----------|--------|-----------|
| 1. IM_NB  | x      | Informationsmodeller hämtas från JSON Scheman i openAPI specifikationer och görs sökbara. |
| 2. IM_SK  | x      | Skördningen sker via Datatjänster som pekar ut openAPI-dokument. Därmer är det i dagsläget inte möjligt att beskriva informationsmodeller för datamängder (som inte har API:er). |
| 3. IE_LD  | -      | Informationsmodellerna är tillgänliga i RDF men bör inte betraktas som länkade data. Detta beror på att det inte finns något sätt att semantiskt annotera openAPI med properties och klasser och då blir ett uttryck i RDF endast en syntaktiskt representation. |
| 4. IE_NB  | x      | Klasser och properties synliggörs enbart ses som en del av den informationsmodell där de definierats. Då representationen inte är baserad på länkade data är det inte heller rimligt att efterfråga sökgränssnitt och separata landningssidor (eftersom man inte kan uppmuntra till återanvändning på ett strukturerat sätt). |
| 5. UML    | -      | Det finns ingen koppling / översättning från UML modeller. |
| 6. VER    | -      | Verktyget för registrering av datamängder stöder inte informationsmodeller. |
| 7. DIA    | -      | Då redigeringsverktyget inte har stöd för informationsmodeller finns heller inte stöd för att skapa diagram. |

### Versionshantering och accesskontroll
Då hanteringen av informationsmodeller bygger på en skördning av openAPI specifikationer så uppdaterar man till senaste versionen. Då det inte finns någon semantisk interoperabilitet kan flera versioner av ett API samexistera utan problem. Accesskontroll löses i samband med att man registrerar datatjänster vilket sker antingen med den norska nationella authentiseringen "ID-porten/Altinn" alternativt att man får en egen användare.

## EntryScape Models
EntryScape Models är en modul i EntryScape-plattformen som syftar till att hantera klasser, properties och applikationsprofiler. En skillnad mot andra modelleringsverktyg är att det utöver översikt och validering också finns ett stort fokus på att kunna generera formulär för redigering och presentation av data. De huvudsakliga användarfallen i designen är att kunna stödja en förenklad hantering av olika applikationsprofiler som DCAT-AP, Core-vocabularies, PROF, SKOS osv.

I likhet med övriga delar av EntryScape-plattformen använder EntryScape Models länkade data, mera specifikt RDFS och delar av SHACL.

### Utveckling och förvaltningsperspektiv
EntryScape Models har utvecklats sedan hösten 2021 och har fokus på hantering av informationsmodeller och formulär. Den första mogna versionen av EntryScape Models färdigställdes under slutet av 2022 och inkluderades i EntryScape 3.7.0. EntryScape Models är öppen källkod precis som övriga delar av plattformen. Kommersiell support för modulen beräknas etableras under 2023. EntryScape Models utvecklas av företaget MetaSolutions som för närvarande har en utvecklargrupp innefattande 8 personer. Läs mer om förvaltning och utveckling av EntryScape som plattform i stycket under dataportalen tidigare i leverabeln.

### Komponenter som stöds
Utvärderingen nedan är fokuserad på EntryScape modules, fler komponenter stöds om man tar hänsyn till den större EntryScape plattformen (se kommentarer för detaljer om detta).

| Komponent | Status | Kommentar |
|-----------|--------|-----------|
| 1. IM_NB  | -      | Stöds av EntryScape Blocks och Workbench. |
| 2. IM_SK  | -      | Stöds av EntryScape Registry och Pipelines. |
| 3. IE_LD  | x      | Klasser och properties sparas i en triplestore med hjälp av relevanta RDF vokabulärer som RDFS, SHACL. |
| 4. IE_NB  | x      | Utforskning av klasser och properties finns inne i verktyget. Externts webbgränssnitt stöds enkelt med en konfiguration av EntryScape Blocks. |
| 5. UML    | -      | Import av UML i form av XMI utvärderas. Import från RDFS finns på plats, export planeras. Import och export av RDForms Templates finns på plats. Import och export av SHACL ligger i roadmap. |
| 6. VER    | x      | Man kan skapa/importera och sen hantera klasser och properties. Applikationsprofiler skapas genom en hantering av fält och formulär. Verktyget stödjer att en modell bygger vidare eller förfinar en annan modell som är definierat i verktyget. Stöd för att bygga vidare på eller förfina en modell som skördats in ligger i roadmap. |
| 7. DIA    | x      | Flera olika UML liknande diagram finns tillgängliga, fokuserande antingen på klasser och properties eller på applikationsprofiler. Manuell redigering av diagramen beräknas stödjas under våren. |

### Versionshantering och accesskontroll
Accesskontroll sker genom att man explicit släpper in de som man ska samarbeta med per modell. 
Versionshantering av modeller hanteras genom att man bygger en version av modellen som därmed blir låst. Den byggda versionen kan man därefter med fördel lägga till som en del av en specifikation.

## Flamländska OSLO-ramverket
OSLO står för "Open Standards for Linking Organisations" och är ett initiativ från den Flamländska myndigheten "Digital Flanders". Ambitionen är att ta fram specifikationer baserade på länkade data-principer i syfte att öka den semantiska interoperabiliteten inom den offentliga förvaltningen. En viktig del i OSLO-ramverket är hur framtagningen av informationsmodellen går till rent tekniskt. Centralt är att det finns en konverterare från [UML till länkade data](https://github.com/Informatievlaanderen/OSLO-UML-Transformer) som möjliggör att de inblandade kan jobba med de UML-verktyg de är vana vid. En praktisk förutsättning för att konverteraren ska fungera är att de som skapar informationsmodellerna lägger till semantiska annotationer i UML-modellerna. 

### Utveckling och förvaltningsperspektiv
OSLO-ramverket är en integrerad del av hur Digital Flanders arbetar med digitalisering i den offentliga förvaltningen, vilket synliggörs på [data.vlaanderen.be](https://data.vlaanderen.be/). Där finns bland annat 133 etablerade standarder, 33 standarder i kandidatstatus samt 24 standarder under utveckling som alla använder sig av OSLO-ramverket. UML-transformatorn är skriven i typescript och klarar av att transformera EAP-filer från SPARX Enterprise Architect. Digital Flanders är en stor myndighet med över 600 medarbetare varav ett 40-tal är involverade i OSLO-ramverket. Det är dock oklart hur stor utvecklargruppen är. Dokumentationen av de tekniska ramverken är i huvudsak skrivna på engelska, däremot är stödmaterial och användarmaterial oftast skrivna på belgiska. Gruppen kring OSLO-ramverket har ett starkt engagemang kring frågor om interoperabilitet och deltar aktivt i olika samarbetsforum som leds av Europeiska kommissionen. Det är oklart i vilken omfattning det finns kommersiell support kring ramverket. Digital Flanders samarbetar med The Flemish Data Utility Company i ett så kallat public private partnership kring OSLO-ramverket.

### Komponenter som stöds
| Komponent | Status | Kommentar |
|-----------|--------|-----------|
| 1. IM_NB  | x      | De framtagna informationsmodellerna kan utforskas i en enklare webbapplikation. |
| 2. IM_SK  | -      | Informationsmodellerna tas fram i en kontrollerad samarbetsprocess av olika expertgrupper och finns att tillgå i ett antal centrala git repositorys. Dvs. det sker ingen skördning i allmän bemärkelse. |
| 3. IE_LD  | x      | Informationsmodeller sparas som RDF filer i git repositories. |
| 4. IE_NB  | x      | De individuella informationselementena kan dock enbart ses som en del av en större informationsmodell. Det saknas både ett kompetent sökgränssnitt och separata sidor där det syns hur informationselementen återanvänds mellan olika informationsmodeller. Detta minskar incitamentet för återanvändning. |
| 5. UML    | x      | Det finns en transform från UML modeller till RDF Scheman givet att de är taggade på rätt sätt. |
| 6. VER    | -      | OSLO erbjuder inte ett enhetligt verktyg utan snarare en hel samarbetsprocess där man har expertgrupper som tar fram en informationsmodell m.h.a. specifika verktyg som Sparx Enterprise Architect. |
| 7. DIA    | -      | Det diagramstöd som finns i UML verktyg räknas inte då denna komponent syftar till stöd i ett centralt verktyg. |

### Versionshantering och accesskontroll
Då hanteringen av informationsmodeller sker i olika git repositories sker versionshantering och accesskontroll via git protokollet och den plattform man administrerar genom. Dvs, hanteringen sker inte i en webbapplikation utan kräver mer teknisk hantering av personer i en central arbetsgrupp, eventuellt uppdelat inom olika domäner.

## Slutsatser

Först och främst är det mycket som tyder på att det är rimligt att man bygger vidare på den existerande dataportalen då det finns vinster i att knyta samman existerande funktionalitet med hantering av informationsmodeller.

Tabellen nedan sammanfattar grovt lösningsuppfyllnaden av de 7 komponenterna per lösning.

| Komponent | Dataportal | Tietomallit | Felles datakatalog | EntryScape Models | OSLO |
|----------|------------|-------------|--------------------|-------------------|------|
| 1. IM_NB | x          | x           | x                  | -                 | x    |
| 2. IM_SK | x          | -           | x                  | -                 | -    |
| 3. IE_LD | -          | x           | -                  | x                 | x    |
| 4. IE_NB | -          | -           | x                  | x                 | x    |
| 5. UML   | -          | -           | -                  | -                 | x    |
| 6. VER   | -          | x           | -                  | x                 | -    |
| 7. DIA   | -          | x           | -                  | x                 | -    |


Från tabellen går det att utläsa tre alternativa sätt att realisera alla komponenterna. Vi går igenom dessa tre alternativ nedan lite kort. Men först är det viktigt att observera att genomförbarheten av alternativen kräver en djupare tekniskt, kostnadsmässigt och användbarhetsanalys innan man kan dra några slutsatser.

En stor osäkerhet i alla alternativen nedan är hur stor omställning det blir för de som jobbar med existerande UML modelleringsverktyg (så att konvertering till informationsmodeller baserade på länkade data möjliggörs). 

### Alternativ 1 - Dataportal, Tietomallit och OSLO
Några av de utmaningar som finns med detta alternativ:
1. Hitta ett sätt för dataportalen att referera / länka in i Tietomallit, t.ex. från specifikationer.
2. Hur kan man föra in information i Tietomallit från skördning, t.ex. via OSLO-ramverkets UML konverterare.
3. Bryta loss Tietomallit från några av de system som är specifika för den finska driftsättningen.
4. Hitta en gemensam förvaltningsmodell med Myndigheten för digitalisering och befolkningsdata.

### Alternativ 2 - Dataportal, EntryScape Models och OSLO
Några av de utmaningar som finns med detta alternativ:
1. EntryScape Models är en ny produkt som inte funnit sin form i alla delar ännu.
2. Hitta ett bra sätt att integrera ett bibliotek av informationsmodeller och informationselement med resten av dataportalen.

### Alternativ 3 - Dataportal och OSLO
Några av de utmaningar som finns med detta alternativ:
1. Kräver en större central bemanning för att leda arbetet inom olika domäner för att ta fram specifikationer.
2. Få in resultatet av specifikationer i dataportalens databas.
3. Hitta ett bra sätt att integrera ett bibliotek av informationsmodeller med resten av dataportalen. (Samma som för alternativ 2.)

Observera att detta alternativ innebär att man väljer att satsa på en ordnad process som hålls i av en central aktör istället för att ta fram ett centralt verktyg. Detta innebär en risk för att man skapar flaskhalsar eller till och med utesluter andra aktörer som inte kan få den hjälp som skulle behövas. Värt att påpeka här är att gruppen som jobbar med OSLO-ramverket i Flandern sammantaget består av ett 40-tal personer och det då inkluderar både teknisk personal som jobbar med utveckling och de som håller i standardiseringsprocessen tillsammans med olika domänexperter.