# Dialog med grunddatadomän transportsystem
Perspektiv från Trafikverket (TV), Transportstyrelsen (TS) och Luftfartsverket (LV).

## A. Hur jobbar ni med informationsmodeller idag.

### A1. Hur många är inblandade och i vilken omfattning?
TV: 5-6 personer på hög nivå. 100-tal om informationsmodellering i bredare mening.<br>
TS: 20-30 på transportstyrelsen med informationsmodellering - lösningsarkitekter, kravanalytiker, verksamhetsarkitekter.<br>
LV: 5-10 på luftfartsverket, distribuerat underhåll via webben.

### A2. Pågår arbetet stötvis eller kontinuerligt?
TS: projektberoende insatser (uppdragsrelaterat)<br>
TV: stötvis hos lösningsarkitekterna, kontinuerligt för informationsförvaltning (ofta via QualiWares webbgränssnitt)<br>
LV: samma som ovan.

### A3. Är det ett jobb som görs i samband med framtagning av nya system i huvudsak?
Se ovan.

### A4. Vilken modelleringsstil använder ni er av (t.ex. är det UML, i så fall vilka diagram)?
TV: UML klassdiagram, liknande i QualiWare.<br>
LV: kan bero från projekt till projekt, olika grupper kan ha olika behov.<br>
TS: Archimate / UML, ej fastställt exakt modelleringsstil. Alla kan klassdiagram.

### A5. Har ni några interna regler kring hur verktyget ska användas (t.ex. modelleringsprinciper som ska följas, undvikas etc.)?
TV: Regler finns, men oklart vilka.<br>
TS: guidelines kring verktygsanvändning.<br>
LV: oklart.

### A6. Separerar ni mellan olika nivåer av modellering? (T.ex. inom ramverket för grunddata talar man om begreppsmodeller, grunddatadomänmodeller och informationsutbytesmodeller.)
TV: Ja, de separeras.<br>
TS: oklart<br>
LV: oklart

## B. Hur samarbetar ni kring informationsmodeller?

### B1. Är det grupparbete vid vita tavlan som sen uppdateras i verktyget av en person i efterhand?
Ensam, visst samarbete i workshop.

### B2. Hur delar / förvarar ni modellerna, delad folder på intranät?
TV: Databas<br>
TS: Databas<br>
LV: Databas + en del dokumenthanteringssystemet.

### B3. Har ni versionshantering av modellerna?
Alla: Nej, senaste versionen underhålls, backuper görs.<br>
TS: Versionshantering sker dock på begreppsdefinitioner (i pdf:er).

### B4. Hur refererar ni till delar av informationsmodellerna (gör ni det)?
TV: Ibland, men då endast via namn i modell

## C. Sker någon återanvändning av informationsmodeller?

### C1. Återanvänder ni andras informationsmodeller på något sätt?
Ja, mellan myndigheter, t.ex. skatteverket.
(Man tolkar och plockar in person och företagsmodellen. Kopierar den manuellt.)

### C2. Gör ni era informationsmodeller synliga utanför den egna organisationen?
Nej

### C3. Känner ni till om någon vidareutnyttjar era informationsmodeller?
TV: Nationella vägdatabasen utnyttjas av andra.

### C4. Har ni krav på er att återanvända eller uppmuntra återanvändning av informationsmodeller?
Nej.

## D. Vilka verktyg använder ni?
TV: Sparx, Qualiware<br>
TS: Sparx, Visio<br>
LV: MooD Software

### D1. Exporterar ni till andra format (t.ex. utöver .eap exportera till xmi eller rena bilder)?
LF: Inkludering av bilder i presentationer. Exporterar till PDF eller word.<br>
TS: Inkludering av bilder i presentationer.

### D2. Använder ni några extra funktioner, t.ex. UML stereotyper eller liknande?
LV: Kraftfullt med överlagring av faktisk data som modellen representerar i form av fakta / statistik.

### D3. Finns det behov som inte är tillgodosedda med verktygen ni jobbar med?
TS: Förenkla begreppshantering så verksamheten kan jobba med ett förenklat gränssnitt, t.ex. definitioner utan att behöva jobba med modellen som helhet.<br>
LV: Ovan finns i Mood.

### D4. Finns modellerna lättillgängliga utanför verktygen?
TS: Nej<br>
LV: Tillgänglig via webb.

### D5. Är det viktigt att kunna bestämma exakt hur diagrammen ser ut? (Dvs. flyttar ni runt klasser och relationer, eller låter ni systemet göra layouten själv?)
TS: Ja, viktigt att bestämma layout beroende på vem man talar med.<br>
LV: Samma.

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
Ja

### E6. För att stärka ett enhetligt språkbruk och förståelse inom organisationen?
Ja

## F. Hur skulle ett nationellt systemstöd för informationsmodeller påverka er?

### F1. Skulle ni undersöka möjligheten att byta?
LV: Ja<br>
TS: Ja, men tveksamt om realistiskt.

### F2. Skulle ni sträva efter att hitta en möjlighet att automatisera så informationsmodellerna finns både lokalt och centralt?
Ja

### F3. Är ni villiga att anpassa arbetssättet i era nuvarande verktyg för att öka interoperabiliteten med interoperabilitet med andra aktörer (och därmed också med det nationella systemstödet)?
Ja

### F4. Skulle ni kunna tänka er att underhålla en delmängd av informationsmodellerna i båda systemen?
Nej, man vill helst förvalta på ett ställe.

### F5. Föredrar ni en enklare lösning där ni kan lägga upp era informationsmodeller i ett bibliotek och undvika att använda ett nationellt systemstöd?
TS: I huvudsak nej om det stoppar oss från ett mer fullödigt införande av ett kompetent verktyg. Men en bred användning blir svår att få till (t.ex. på grund av brist på krav/regleringar/föreskrifter), då kan det fylla att syfte att på ett enkelt sätt kunna finna / referera till informationsmodeller som helhet.
