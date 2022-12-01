# Dialog med grunddatadomän person
I huvudsak representerat av Skatteverket.

## A. Hur jobbar ni med informationsmodeller idag.
Man jobbar med ett flertal diagram i Sparx EA.

### A1. Hur många är inblandade och i vilken omfattning?
Cirka 10-15 informationsarkitekter är inblandade.

### A2. Pågår arbetet stötvis eller kontinuerligt?
Pågående arbete.

### A3. Är det ett jobb som görs i samband med framtagning av nya system i huvudsak?
I samband med utveckling. Ofta bygger man vidare på existerande modeller snarare än börjar om på nytt.

### A4. Vilken modelleringsstil använder ni er av (t.ex. är det UML, i så fall vilka diagram)?
UML klassdiagram. Övriga diagram används för andra behov utöver informationsmodelleringen, t.ex. processdiagram.

### A5. Har ni några interna regler kring hur verktyget ska användas (t.ex. modelleringsprinciper som ska följas, undvikas etc.)?
Det finns en handbok. Både en kring principer och en kring hur man använder verktyget. Metamodell för både begreppsmodeller och informationsmodeller

* Astrakan för begreppsmodeller.
* Anpassad UML för Informationsmodeller

T.ex. har man valt att inte använda av komposit och aggregering relationer.

### A6. Separerar ni mellan olika nivåer av modellering? (T.ex. inom ramverket för grunddata talar man om begreppsmodeller, grunddatadomänmodeller och informationsutbytesmodeller.)
Ja, begrepp och informationsmodeller.

## B. Hur samarbetar ni kring informationsmodeller?

### B1. Är det grupparbete vid vita tavlan som sen uppdateras i verktyget av en person i efterhand?
Första gången är det ofta identifiera substantiv som ska motsvara begrepp / klasser för att fånga verksamhetens behov. Vilka aktörer och artefakter som är involverade.

Modelleringsmöten med flera personer från verksamheten, man jobbar oftast direkt i verktyget.

### B2. Hur delar / förvarar ni modellerna, delad folder på intranät?
Skatteverket repository, en databas som EA lagrar i.

### B3. Har ni versionshantering av modellerna?
Man jobbar med två olika repositorys, man flyttar över när modeller är godkända. Ibland jobbar man lokalt för prematura modeller.
Det finns ett repository "Sandbox" som används för test och utbildning.

### B4. Hur refererar ni till delar av informationsmodellerna (gör ni det)?
Länka in klasser inom repositoryt.

## C. Sker någon återanvändning av informationsmodeller?

### C1. Återanvänder ni andras informationsmodeller på något sätt?
Ingen återanvändning hittills. Planen är att använda XMI för detta när det förekommer. Det finns tankar om att komplettera handboken för att hantera detta på sikt.

### C2. Gör ni era informationsmodeller synliga utanför den egna organisationen?
Person modellen (grunddata) publiceras på en extern webb som PDF och XMI. Man använder Sparx Webb enterprise architect för detta.

### C3. Känner ni till om någon vidareutnyttjar era informationsmodeller?
Naturvårdsverket har tagit in skatteverkets modeller.

### C4. Har ni krav på er att återanvända eller uppmuntra återanvändning av informationsmodeller?
På gång med krav / samarbeten för att exponera begrepp och information mellan myndigheter.

## D. Vilka verktyg använder ni?
Sparx för enterprisenivå.

### D1. Exporterar ni till andra format (t.ex. utöver .eap exportera till xmi eller rena bilder)?
Ja, XMI och PDF på extern webb.

### D2. Använder ni några extra funktioner, t.ex. UML stereotyper eller liknande?
Ja, egen metamodell via MDG technologies.

### D3. Finns det behov som inte är tillgodosedda med verktygen ni jobbar med?
Återanvändning av attribut mellan klasser är svårt, det blir kopior.

### D4. Finns modellerna lättillgängliga utanför verktygen?

Man publicera till Word, HTML, PDF etc. De licenser man har är begränsande till vilka som får jobba i verktyget, inte titta på resultatet.

### D5. Är det viktigt att kunna bestämma exakt hur diagrammen ser ut? (Dvs. flyttar ni runt klasser och relationer, eller låter ni systemet göra layouten själv?)
Man justerar positionering manuellt till stor del.

## E. Hur använder ni er av informationsmodeller?

### E1. För kommunikation inför framtagande av system?
Ja.

### E2. För dokumentation syfte och framtida underhåll av system?
Ja.

### E3. För kravställning av system?
Ja.

### E4. För roundtrip engineering?
Tidiga försök gjordes, men har övergivits. Inga implementationsspecifika detaljer anges på informationsmodeller.

### E5. För kommunikation mellan olika grupperingar, t.ex. arkitekturgrupp och utvecklargrupp.
Ja. Kommunikation med integrationspartners.

### E6. För att stärka ett enhetligt språkbruk och förståelse inom organisationen?
Ja, etablering av begrepp. Beskrivningar är viktiga.

## F. Hur skulle ett nationellt systemstöd för informationsmodeller påverka er?

### F1. Skulle ni undersöka möjligheten att byta?
Nej.

### F2. Skulle ni sträva efter att hitta en möjlighet att automatisera så informationsmodellerna finns både lokalt och centralt?
Länkade informationsmodeller från specifikationer vore en bra lösning.
Det finns inget behov / värdeskapande från Skatteverkets sida med en djupare integration. 

### F3. Är ni villiga att anpassa arbetssättet i era nuvarande verktyg för att öka interoperabiliteten med interoperabilitet med andra aktörer (och därmed också med det nationella systemstödet)?
För grunddatadomänen så är det en rimlig väg framåt.
För alla informationsmodeller på Skatteverket är det inte alls självklart att det finns ett mervärde.

### F4. Skulle ni kunna tänka er att underhålla en delmängd av informationsmodellerna i båda systemen?
* Helst inte.
* Man vill ha en master.
* Möjligtvis bara grunddatadomänen.

### F5. Föredrar ni en enklare lösning där ni kan lägga upp era informationsmodeller i ett bibliotek och undvika att använda ett nationellt systemstöd?
Tveksamt, en automatik är det viktiga. Hur mycket information blir tillgänglig beror på andra faktorer.

## Övrigt

* E-sam har samarbetsgrupp kring hur man använder Sparx.
* På skatteverket betraktas de interna informationsmodellerna som folkbokföring medans de informationsmodeller som motsvarar det man kommunicerar utåt kallas för avisering.