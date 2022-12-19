# Scenarior

För att göra det enklare att beskriva de olika scenariorna beskriver vi först ett antal funktioner / komponenter som vi sen kombinerar på olika sätt. För att göra det enklare nedan använder vi följande vokabulär:

- Informationsmodell - motsvarar antingen grunddatadomänmodell eller informationsutbytesmodell enligt Ramverket för nationella grunddata.
- Informationselement - motsvarar det som en informationsmodell typiskt består av, dvs i UMLs klassdiagram motsvarar det klasser, attribut och relationer medans i länkade data motsvarar det klasser, properties och applikationsprofiler.

## Komponenter

### Komponent 1 - Nationellt bibliotek av informationsmodeller
Ett nationellt bibliotek av informationsmodeller innebär att man synliggöra informationsmodeller på en central plats. Genom att tillhandahålla metadata kring informationsmodellerna skapar man en mininivå av interoperabilitet för sökning, filtrering och presentation på webben av modeller. Ett nationellt modellbibliotek tillåter olika modelleringsparadigm och format att samexistera då man inte gör några försök att titta in i informationsmodellerna.

I praktiken innebär det att biblioteket behandlar alla informationsmodellerna lika, oberoende om de är enkla bilder uttryckta i format som PNG eller SVG eller rikare format som motsvarar olika modelleringsparadigm som UML uttryckt som XMI filer eller RDFS / SHACL.

En rekommendation är att man kan bygger vidare på dataportalens existerande infrastrukturen för specifikationer där informationsmodeller blir en av specifikationens olika delar. Det är viktigt att notera att en specifikation innebär en ytterligare abstraheringsnivå utöver en informationsmodell som av en del kan ses som onödig. Fördelen med att utnyttja specifikationer är att man får möjligheten att knyta samman informationsmodeller med andra relevanta resurser, t.ex. datascheman, vokabulärer, vägledningar, översättningar osv. Förhoppningen är att detta kommer ske ofta nog för att motivera den ökande komplexiteten som nivån av specifikationer innebär.

### Komponent 2 - Skördning av informationsmodeller
Idag har dataportalen stöd för manuell hantering av specifikationer i en central administrativ funktion. För de aktörer som har informationsmodeller exponerade i en externwebb kan en skördningsfunktion introduceras för att minska dubbelarbete och minska risken för idiosynkratier. Notera att med dataportalens nuvarande angreppsätt kan man inte registrera informationsmodeller direkt, det krävs en specifikation där informationsmodellen blir en resurs. Det är möjligt att här göra en rikare integration där man fyller på med fler resurser utöver informationsmodellen.

### Komponent 3 - Hantera informationselement som länkade data

Att hantera informationselement som Länkade Data (LD) innebär grundläggande förståelse för hur klasser och properties uttrycks i RDFS och hur applikationsprofiler uttrycks i SHACL eller motsvarande. Alla delar ges egna identifierare i form av URI:er och beskrivs med metadata. Notera att samma informationselement kan ingå i flera olika modeller, väsentligen återanvändning av klasser och properties.

### Komponent 4 - Nationellt biblioteket med informationselement

När man väl har etablerat ett sätt att hantera informationselement (komponent 3) är ett naturligt nästa steg att kunna vilja visa upp dessa i det nationella biblioteket över informationsmodeller (komponent 1). Det är rimligt att tänka sig att man kan söka och utforska informationselement oberoende av modellerna, dvs det blir möjligt att:

1. Söka fram och utforska klasser, properties och applikationsprofiler (SHACL) inte bara informationsmodeller som helhet.
2. Referera direkt till klasser, properties och applikationsprofiler i kommunikation via djuplänkning.
3. Uppmuntra och visa på hur klasser, properties och applikationsprofiler har/kan vidareutnyttjats.

Den sista punkten innebär till exempel att man kan se hur Core-Vocabularies från den Europeiska kommisionen har används eller hur klasser återanvänds mellan grunddatadomäner.

### Komponent 5 - Extrahera informationselement ur UML klassdiagram

Idag är det få som jobbar direkt med RDFS och SHACL men desto fler som jobbar med UML. Det är möjligt att hitta översättningar från UML klassdiagram till klasser och properties uttryckta i RDFS och SHACL. Men, för att detta ska fungera krävs att man jobbar med UML modellerna på ett särskilt sätt. Inpiration från OSLO i Belgien och ODM modellen från OMG kan användas för att hitta en väg framåt här.

Viktiga målsättningar i detta scenario är att:
1. Undvika duplicering av klasser och properties.
2. Detektera relationer mellan modeller när man återanvänt klasser och properties.
3. Hitta ett bra arbetsätt i de populäraste UML verktygen som går att underhålla.

### Komponent 6 - Nationellt verktyg för informationselement
Ett modelleringsverktyg behöver som ett miniumum kunna redigera definitioner av klasser, properties i RDFS och applikationsprofiler (SHACL). För förvaltning av applikationsprofiler är det nödvändigt att kunna välja att återanvända klasser och properties som andra redan definierat, dvs ett beroende till komponent 1, 3 och 4.

### Komponent 7 - Diagramstöd för informationsmodeller 
Utöver de formella informationselement  finns det ofta ett behov av att skapa visuella representationer i form av diagram av hela informationsmodellen. Det finns tre nivåer av stöd för diagram:

1. Genererade via algoritmer
2. Stöd för manuell redigering av layout
3. Stöd för redigera / skapa / ta bort informationselement direkt i diagrammet

## Scenarios

Nedan beskriver vi ett fåtal huvudscenarior baserat på de olika komponenterna ovan. Det går att hitta fler kombinationer, men dessa är det huvudsakliga. Först har vi en översiktlig tabell över scenarios och vilka komponenter som krävs:

Scenario | 1 | 2 | 3 | 4 | 5 | 6 | 7
--- | --- | --- | --- | --- | --- | --- | ---
A | x | x |   |   |   |   |
B | x | x | x | x | x |   | ?
C |   |   |   |   |   | x | x
D | x | x | x | x | x | x | x

### Scenario A - Nationellt bibliotek av informationsmodeller

Detta scenario är i stort sett på plats redan idag på dataportalen och motsvarar komponent 1. Man kan tänka sig att man också lägger till stöd för skördning av informationsmodeller från olika aktörer motsvarande komponent 2. Notera dock att i detta scenario försöker vi oss inte på att tolka och koppla samman informationsmodellerna, de är svarta lådor.

### Scenario B - Nationellt bibliotek av informationsmodeller och informationselement
Scenario B bygger vidare på scenario A med stöd för informationselement. Då de flesta inte uttrycker informationselement på ett interoperabelt sätt är det nödvändigt att skörda in informationsmodeller och också inkludera UML integrationen, dvs komponent 1-5. Man kan även tänka sig att man för in komponent 7 på den enklaste nivån, dvs algoritmiskt genererade layouter.

### Scenario C - Nationellt verktyg för informationsmodeller och informationselement
I detta scenario fokuserar vi helt på verktyget utan ett separat bibliotek. Dvs komponent 6 och 7 med stöd för manuell redigering av layout. Det är dock inte realistiskt att hitta verktyg som klarar av att även redigera mer än layout direkt i diagrammet då det innebär att man går över en gräns i komplexitet och gör återanvändning av existerande ramverk mycket svårare.

I scenario är det tänkt att man i verktyget någorlunda enkelt kan skapa sin egna informationsmodeller eller ännu bättre utgå från existerande informationsmodeller och lägga till / anpassa så det fungerar i den egna domänen. En tydlig begränsning är att man kommer behöva jobba dubbelt i olika verktyg då skördning och tolkning av UML inte ingår i detta scenario.

### Scenario D - Nationellt bibliotek och verktyg för informationsmodeller och informationselement
Detta scenariot är det mest komplexa då det innefattar ett samspel mellan informationsmodeller och informationselement som förvaras utanför verktyget och de som skapas i verktyget. Scenariot motsvarar fallet då organisationer som redan jobbar i verktyg kan stanna i dessa medans de som saknar kan välja att använda ett nationellt systemstöd för informationsmodeller och informationselement. Det betyder att alla komponenterna behövs här, även komponent 3 inkluderande skördning och komponent 5 inkluderande tolkning av UML.