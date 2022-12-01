# Dialog med Naturvårdsverket

## A. Hur jobbar ni med informationsmodeller idag.

### A1. Hur många är inblandade och i vilken omfattning?
10-20 användare.

### A2. Pågår arbetet stötvis eller kontinuerligt?
Kontinuerligt, men kopplat till utvecklingsprojekt.

### A3. Är det ett jobb som görs i samband med framtagning av nya system i huvudsak?
Ja i huvudsak. Men ibland vid samverkan med andra myndigheter.

### A4. Vilken modelleringsstil använder ni er av (t.ex. är det UML, i så fall vilka diagram)?
UML klassdiagram.

### A5. Har ni några interna regler kring hur verktyget ska användas (t.ex. modelleringsprinciper som ska följas, undvikas etc.)?
Vägledning finns. Hur jobbar man i verktyget, hur refererar man till saker i den interna webbpublikationen. Modelleringsprinciperna inkluderar motiveringar men också avgränsningar:

Klasser med attribut, relationer (associationer, eventuellt med namn och riktning), multipliciteter.

### A6. Separerar ni mellan olika nivåer av modellering? (T.ex. inom ramverket för grunddata talar man om begreppsmodeller, grunddatadomänmodeller och informationsutbytesmodeller.)
Ja, begreppsmodeller och grunddatadomänmodeller.

## B. Hur samarbetar ni kring informationsmodeller?

### B1. Är det grupparbete vid vita tavlan som sen uppdateras i verktyget av en person i efterhand?
I huvudsak enskilt arbete.
Grupparbete sker ibland med kravställare, då i form av parmodellering, post-it lappar + modellsekreterare eller verktyget direkt.

### B2. Hur delar / förvarar ni modellerna, delad folder på intranät?
Central databas. Särskiljer mellan kvalitetssäkrade modeller och ett allmänt repository.
Manuellt batch jobb en gång per vecka där man lägger upp HTML sidor på en intern webb. 

### B3. Har ni versionshantering av modellerna?
Nej, backup hantering.

### B4. Hur refererar ni till delar av informationsmodellerna (gör ni det)?
Intern via referensen till publikation på internwebb. Ibland via bilder.
Alla modellelement går att referera till unikt.

## C. Sker någon återanvändning av informationsmodeller?

### C1. Återanvänder ni andras informationsmodeller på något sätt?
Återanvändning internt i huvudsak. Informationsmodeller är spridda utåt.
Skatteverkets personmodell återanvänds, XMI-filen är importerad.
Återpublicering av INSPIRE modeller i den interna webbpubliceringen.

### C2. Gör ni era informationsmodeller synliga utanför den egna organisationen?
Inte rutinmässigt, spridning sker informellt via bilder.

### C3. Känner ni till om någon vidareutnyttjar era informationsmodeller?
Modeller för årlig miljörapportering kommer återanvändas.

### C4. Har ni krav på er att återanvända eller uppmuntra återanvändning av informationsmodeller?
Självpåtagna krav, men inga från ledning eller lagstiftning.

## D. Vilka verktyg använder ni?
Sparx EA för modellering. Fuskas med powerpoint och Visio.

### D1. Exporterar ni till andra format (t.ex. utöver .eap exportera till xmi eller rena bilder)?
HTML för webbpublicering internt. Vokabulär migrerad till dataportal kring metadatahantering.

### D2. Använder ni några extra funktioner, t.ex. UML stereotyper eller liknande?
Ja, inga constraints, tag-values etc.

### D3. Finns det behov som inte är tillgodosedda med verktygen ni jobbar med?
Avsaknad av en bra och någorlunda enkel versionshantering. Webbpubliceringen duger för internt bruk, men saknar saker som sökfunktionalitet. Uppdatera av beroenden till externa modeller (t.ex. Skatteverkets person modell) stöds inte utan att man klipper av beroendena (merge / diff saknas).

### D4. Finns modellerna lättillgängliga utanför verktygen?
Ja webbpublicerat internt.

### D5. Är det viktigt att kunna bestämma exakt hur diagrammen ser ut? (Dvs. flyttar ni runt klasser och relationer, eller låter ni systemet göra layouten själv?)
Defaultutseende vore trevligt. Manuell layout som komplement är ett bör krav.
Slå på olika mycket information bär också vara ett bör krav.

## E. Hur använder ni er av informationsmodeller?

### E1. För kommunikation inför framtagande av system?
ja

### E2. För dokumentation syfte och framtida underhåll av system?
ja

### E3. För kravställning av system?
ja

### E4. För roundtrip engineering?
Nej.

### E5. För kommunikation mellan olika grupperingar, t.ex. arkitekturgrupp och utvecklargrupp.
Ja.

### E6. För att stärka ett enhetligt språkbruk och förståelse inom organisationen?
Ja.

## F. Hur skulle ett nationellt systemstöd för informationsmodeller påverka er?

### F1. Skulle ni undersöka möjligheten att byta?
Ja. Vad är kostnaden kring migrering, förvaltning i nya systemet osv.

### F2. Skulle ni sträva efter att hitta en möjlighet att automatisera så informationsmodellerna finns både lokalt och centralt?
Ja. Det vore en bra lösning om de kan fungera tillsammans.

### F3. Är ni villiga att anpassa arbetssättet i era nuvarande verktyg för att öka interoperabiliteten med interoperabilitet med andra aktörer (och därmed också med det nationella systemstödet)?
Kanske.

### F4. Skulle ni kunna tänka er att underhålla en delmängd av informationsmodellerna i båda systemen?
Nej.

### F5. Föredrar ni en enklare lösning där ni kan lägga upp era informationsmodeller i ett bibliotek och undvika att använda ett nationellt systemstöd?
Detta kommer utnyttjas om det finns. Kan vara en brygga.