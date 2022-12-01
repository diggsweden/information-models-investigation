# Dialog med grunddatadomän Fastighets- och geografisk information
I huvudsak representerat av Lantmäteriet.

## A. Hur jobbar ni med informationsmodeller idag.

### A1. Hur många är inblandade och i vilken omfattning?
Ca. 10 personer.

### A2. Pågår arbetet stötvis eller kontinuerligt?
Mestadels stötvis, projektdrivet. Viss hantering sker i förvaltning / linjen.

### A3. Är det ett jobb som görs i samband med framtagning av nya system i huvudsak?
Ofta i relation till tekniska lösningar som tas fram.
Begreppsmodeller ibland för kommunikation oberoende av teknisk utveckling.

### A4. Vilken modelleringsstil använder ni er av (t.ex. är det UML, i så fall vilka diagram)?
Klassdiagram i UML. 

### A5. Har ni några interna regler kring hur verktyget ska användas (t.ex. modelleringsprinciper som ska följas, undvikas etc.)?
Separata regelverk för notation och programvaran. T.ex. ej använda komposit och aggregat, hur mycket information på attribut, namnsättning osv.

### A6. Separerar ni mellan olika nivåer av modellering? (T.ex. inom ramverket för grunddata talar man om begreppsmodeller, grunddatadomänmodeller och informationsutbytesmodeller.)
Ja. Grunddatadomänmodeller kallas för informationslagringsmodell. Begreppsmodeller handlar mer om att definiera begreppen än hur informationen ska bli uttryckt praktiskt. Större fokus på begrepp och relationer, snarare än attribut.

## B. Hur samarbetar ni kring informationsmodeller?

### B1. Är det grupparbete vid vita tavlan som sen uppdateras i verktyget av en person i efterhand?
Ofta grupparbete med en vit tavla som bas. Beroende på sammanhanget, så ritar man direkt eller i efterhand utifrån det gemensamma modellen på tavlan.

### B2. Hur delar / förvarar ni modellerna, delad folder på intranät?
Intern databas med ett repository i samband med enterprise architect. 

### B3. Har ni versionshantering av modellerna?
Exportera ögonblicksbilder i databasen. Olika paket för version 1.0 och 2.0 där systemunderhåll kräver parallella versioner.

### B4. Hur refererar ni till delar av informationsmodellerna (gör ni det)?
Återanvändning av klasser mellan modeller.
Länka till publicering som hemsida.

## C. Sker någon återanvändning av informationsmodeller?

### C1. Återanvänder ni andras informationsmodeller på något sätt?
Inspire modellen är importerad för referens och mappningar.

### C2. Gör ni era informationsmodeller synliga utanför den egna organisationen?
Som webbsidor. Enskilda förfrågningar att få ut som XMI.

### C3. Känner ni till om någon vidareutnyttjar era informationsmodeller?
SSB (Smartare SamhällsByggnads process) används t.ex. av Naturvårdsverket (lite oklart exakt hur).

### C4. Har ni krav på er att återanvända eller uppmuntra återanvändning av informationsmodeller?
INSPIRE på metadatanivån. På datanivån finns andra krav, t.ex. byggnadsmodellen från INSPIRE. Men man har oftast en egen modell som man mappar till de modeller som krävs i kommunikationslagret (GML).

## D. Vilka verktyg använder ni?
Huvudsak: Enterprise Architect
Skisser: Visio

### D1. Exporterar ni till andra format (t.ex. utöver .eap exportera till xmi eller rena bilder)?
XMI eller bilder som skickas runt eller hamnar i presentationer. Publicering till internwebb (Prolaborate). Egen HTML snurra för extern publicering (och internt), kommer fasas ut och ersättas av Webb EA.

### D2. Använder ni några extra funktioner, t.ex. UML stereotyper eller liknande?
Stereotyper används. I internationella sammanhang används MDG teknologier. Tagged values används internationellt.

### D3. Finns det behov som inte är tillgodosedda med verktygen ni jobbar med?
Bättre versionshantering. Bättre användbarhet.

### D4. Finns modellerna lättillgängliga utanför verktygen?
Interwebb och externwebb (där finns i huvudsak byggnad, adress och lägenhet modeller).

### D5. Är det viktigt att kunna bestämma exakt hur diagrammen ser ut? (Dvs. flyttar ni runt klasser och relationer, eller låter ni systemet göra layouten själv?)
Manuell placering är viktigt.

## E. Hur använder ni er av informationsmodeller?

### E1. För kommunikation inför framtagande av system?
Ja

### E2. För dokumentation syfte och framtida underhåll av system?
Ja

### E3. För kravställning av system?
Ja

### E4. För roundtrip engineering?
Nej

### E5. För kommunikation mellan olika grupperingar, t.ex. arkitekturgrupp och utvecklargrupp.
Ja.

### E6. För att stärka ett enhetligt språkbruk och förståelse inom organisationen?
Ja.

## F. Hur skulle ett nationellt systemstöd för informationsmodeller påverka er?

### F1. Skulle ni undersöka möjligheten att byta?
Ja, iallafall i arbetet kring grunddatadomänen.

### F2. Skulle ni sträva efter att hitta en möjlighet att automatisera så informationsmodellerna finns både lokalt och centralt?
Ja, om man sitter kvar med det egna verktyget så handlar det om att hitta en lätt väg framåt, med hänsyn till begränsade resurser, för att minimera det manuella arbetet.

### F3. Är ni villiga att anpassa arbetssättet i era nuvarande verktyg för att öka interoperabiliteten med interoperabilitet med andra aktörer (och därmed också med det nationella systemstödet)?
Ja, det är intressant att se vad som är möjligt. Beroende på hur omfattande insatsen är sätter man en ambitionsnivå.

### F4. Skulle ni kunna tänka er att underhålla en delmängd av informationsmodellerna i båda systemen?
Nej, sannolikt inte, det finns inte resurser att underhålla och säkerställa att det är synkroniserat.

### F5. Föredrar ni en enklare lösning där ni kan lägga upp era informationsmodeller i ett bibliotek och undvika att använda ett nationellt systemstöd?
Det är en möjlig mellanväg, men inte optimalt. Kan vara en brygga för mindre organisationer för att komma igång.