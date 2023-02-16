# Kravställning och testfall

## Krav per scenario
### Scenario A - Nationellt bibliotek av informationsmodeller

1. Informationsmodeller är sökbara och har egna landningssidor
2. Informationsmodeller har persistenta identifierare i form av URI:er
3. Informationsmodeller har metadata, t.ex. titel, utgivare, ämnesklassificering och beskrivande texter
4. Informationsmodeller som motsvarar bilder visas, alla andra format blir länkar / nedladdning
5. Informationsmodeller som beskrivs hos dataleverantör skördas in
6. Informationsmodellens listar kompatibla datamängder på sin landningssida

### Scenario B - Nationellt bibliotek av informationsmodeller och informationselement

1. Informationselement i form av klasser är sökbara och har egna landningssidor
2. Informationselement i form av egenskaper (attribut och relationer) är sökbara och har egna landningssidor
3. Informationselement har persistenta identifierare i form av URI:er
4. Informationsmodeller listar de ingående informationselementen på sin landningssida
5. Informationselement har metadata motsvarande teknisk interoperabilitet, t.ex. datatyper, datastruktur, kardinalitet.
6. Informationselement har metadata motsvarande semantisk interoperabilitet, t.ex. beskrivningar / definitioner, relationer mellan informationselement
7. Informationsmodeller och informationselement kan extraheras ur klassdiagram uttryckta i UML
8. Informationsmodeller och informationselement kan extraheras ur RDF Schema och SHACL

### Scenario C - Nationellt verktyg för informationsmodeller och informationselement

1. Verktyget stödjer hantering av informationselement
2. Verktyget stödjer hantering av informationsmodeller
3. Verktyget stödjer aktörer att samarbeta
4. Verktyget stödjer hantering av olika versioner av informationsmodeller (informationselement kan bara uppdateras)
5. Verktyget stödjer aktörer att skapa UML klassdiagram beskrivande en informationsmodell

### Scenario D - Nationellt bibliotek och verktyg för informationsmodeller och informationselement

1. Informationsmodeller och informationselement som skapats i verktyget syns i det nationella biblioteket efter publicering
2. Verktyget stödjer även återanvändning av informationselement som finns i det nationella biblioteket
3. Informationsmodeller som skapats av verktyget kan exporteras som UML och göras tillgängliga från det nationella biblioteket

## Testfall

I följande testfall finns antaganden om användning av PROF-SE och dataportalen för att hantera informationsmodeller som en del av specifikationer. Vissa av dessa antaganden kräver vidare utredning innan de slås fast. Trots osäkerheten i dessa antaganden beskrivs testfallen som om dessa antaganden är givna då det leder till en större konkretisering som är enklare att förhålla sig till än om testfallen skulle beskrivas i mer allmänna ordalag.

### 1. Informationsmodeller i form av webbsidor och bilder synliggörs på dataportalen
En aktör har lagt upp ett antal informationsmodeller på sin externwebb, några är rena bilder, andra är webbsidor. Aktören meddelar dataportalen om informationsmodellernas existens genom att utnyttja PROF-SE där informationsmodellerna beskrivs som specifikationer. PROF-SE gör det möjligt att peka ut flera specifikationsdelar, t.ex. för att representera olika format som en bild (t.ex. PNG) och en webbsida (HTML). I de fall samma informationsmodell finns beskriven både som en bild och en webbsida läggs de som två specifikationsdelar i samma specifikation. Ytterligare specifikationsdelar kan läggas till vid behov med olika roller, t.ex. vägledningar, exempel, bakgundsinformation.

Dataportalen skördar in PROF-SE och alla specifikationer dyker med egna landningssidor. De som är rena bilder visas upp direkt på landningssidan och för de som är webbsidor finns en utgående länk. Dataportalen gör det möjligt att söka på specifikationer, och metadatan per specifikation enligt PROF-SE innehåller en mängd lämpliga fält som titel, beskrivning, utgivare och ämnesklassificering osv.

Exemplifierar A1, A3-A5.

### 2. Kopplingar mellan datamängder och informationsmodeller visas 
En datamängd som följer en viss informationsmodell indikerar detta genom en relation till specifikation (som innehåller informationsmodellen som specifikationsdel). Relationen uttrycks med hjälp av `dcterms:conformsTo` som är en del av DCAT-AP-SE specifikationen. Följaktligen ska det på datamängdens landningssida finns en länk till specifikationens landningssida om den har en relation via `dcterms:conformsTo`. Omvänt gäller att på specifikationens landningssida finns länkar tillbaka till alla datamängder som uppfyller specifikationen (informationsmodellen).

En förutsättning för att relationen mellan en datamängd och en specifikation kan göras är att det på landningssidan är tydligt vilken beständig identifierare som ska användas för specifikationen.

Exemplifierar A2, A6.

### 3. En klass i ett UML klassdiagram får en egen landningssida
En aktör har lagt upp en informationsmodell i form av ett UML klassdiagram uttryckt i formatet XMI eller EAP. UML klassdiagrammet har tagged values som bland annat ger en persistent identifierare för klassen. Klassens landningssida listar de informationsmodeller där klassen används och även de egenskaper som har klassen som range eller domain. Klassen går att ladda ner som en beskrivning i RDFS oberoende av sin förekomst i olika informationsmodeller. Om klassen har en superklass visas det. Det går att söka fram klassen.

Exemplifierar B1, B3, B6, B7.

### 4. Ett attribut / relation i ett UML klassdiagram får en egen landningssida
En aktör har lagt upp en informationsmodell i form av ett UML klassdiagram uttryckt i formatet XMI eller EAP. UML klassdiagrammet har tagged values som tillhandahåller persistent identifierare för varje attribut / relation. Attributets / relationens landningssida listar de informationsmodeller där det används och även de klasser som den utgår från / pekar på. Attributet / relationen går att ladda ner som en property i RDFS oberoende av sin förekomst i olika informationsmodeller. Begränsningar i nodtyp / datatyp visas upp. 

Exemplifierar B2, B3, B5, B6, B7.

### 5. Ett UML klassdiagram berikar landningssidan för en specifikation
En aktör har lagt upp en informationsmodell i form av ett UML klassdiagram uttryckt i formatet XMI eller EAP. Landningssidan visar UML modellen som diagram i kombination med en mer textuell beskrivning av alla ingående klasser, attribut och relationer. För varje klass, attribut och relation finns en länk till motsvarande landningssida som beskriver den på ett sätt som är oberoende av dess användning i en specifikation.
Hela UML klassdiagrammet går att ladda ner som en SHACL beskrivning.

Exemplifierar B4, B5, B7.

### 6. Ett UML klassdiagram återanvänder klasser, attribut och relationer från en annan informationsmodell
En aktör har lagt upp en informationsmodell i UML där tagged values indikerar att några av klasserna, attributen och relationerna är återanvända från en annan modell (de kommer från en annan namnrymd). Landningssidan för informationsmodellen / specifikationen blir berikad som i testfall 5, men för de klasser, attribut och relationer som återanvänds skapas inte nya landningssidor. Istället kan man på de landningssidorna se att dessa informationselement ingår i flera informationsmodeller. 

Exemplifierar B5.

### 7. En SHACL fil berikar en specifikation 
En aktör har lagt upp en informationsmodell i form av en SHACL fil. Landningssidan för specifikationen ser likadant ut som när man laddat upp en UML fil.

Exemplifierar B8.

### 8. En RDFS fil berikar en specifikation
En aktör har lagt upp en RDF Schema fil för att deklarera nya klasser och egenskaper som introduceras i specifikationen. Landningssidorna för klasser och egenskaper ser likadata ut som för UML.

Exemplifierar B8.

### 9. En aktör skapar en ny informationsmodell där nya klasser och egenskaper ingår
En aktör som fått tillgång till verktyget kan definiera upp nya klasser och egenskaper. En informationsmodell skapas genom att kombinera klasser och egenskaper. Avgränsningar i användningen av klasser och egenskaper görs, t.ex. kardinalitet eller att definiera att en mindre mängd av värden accepteras för ett attribut.

Klasserna och egenskaperna uttrycks i huvudsak som RDF Schema där också persistent identifierare skapas i en vald namnrymd. Informationsmodellen uttrycks med hjälp av SHACL.

Exemplifierar C1, C2

### 10. Två aktörer jobbar med en informationsmodell
Två olika aktörer ges tillgång att utveckla en informationsmodell gemensamt. Verktyget har stöd för redigeringshistorik vilket gör det möjligt att följa vem som gjort vad.

Exemplifierar C3.

### 11. En aktör uppdaterar en informationsmodell med en ny version
En informationsmodell kan komma i en ny version genom att använda versionshanteirngen i PROF-SE. Uppdateringen innefattar ändringar i vilka egenskaper som associeras till en klass samt eventuellt genom ändringar i kardinalitet och vilka värdemängder som accepteras. En ny version av en informationsmodell innebär att en ny persistent identifierare introduceras.

Det är fullt möjligt att i en ny informationsmodell har man bytt ut eller lagt till klasser och egenskaper. Till skillnad från informationsmodeller har klasser och egenskaper inte någon versionshantering, när de väl tagits i bruk får deras persistent identifierare eller semantik bytas. Däremot är det möjligt att gradvis förbättra / förtydliga / komplettera eller översätta de beskrivningar som redan finns.

Exemplifierar C4.

### 12. En aktör skapar ett tillrättalagt diagram av informationsmodellen
För att förenkla översikten av vilka klasser och egenskaper som ingår i informationsmodellen kan ett UML klassdiagram hjälpa. Automatisk rendering av ett diagram är ofta möjlig men bör kompletteras av manuell redigering för att säkerställa att informationsmodellens centrala delar hamnar i centrum utan för många korsande linjer.

Exemplifierar C5.

### 13. Informationsmodell skapad i verktyget publiceras till dataportalen
När en informationsmodell är mogen kan den publiceras. Efter publicering blir informationsmodellen synlig på dataportalen på samma sätt som om den blivit skördad. Då skördning sker vissa tidpunkter på dygnet innebär det en fördröjning innan publicerade informationsmodeller blir synliga.

Exemplifierar D1.

### 14. En informationsmodell skapas i verktyget utifrån skördade informationselement
I verktyget kan man välja att återanvända klasser och egenskaper, inte bara de som skapats i verktyget utan även de som finns på dataportalen.

Exemplifierar D2.

### 14. En informationsmodell skapad i verktyget laddas ner från dataportalen som en UML modell för återanvändning
Publicerade informationsmodeller, oavsett härkomst, går att ladda ner från dataportalen som XMI filer. En informationsmodell skapad i det nationella verktygsstödet laddas ner och används i ett UML verktyg.

Exemplifierar D3.