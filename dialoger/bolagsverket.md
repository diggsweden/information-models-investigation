# Dialog med grunddatadomän företag
I huvudsak representerat av Bolagsverket.

## A. Hur jobbar ni med informationsmodeller idag.

### A1. Hur många är inblandade och i vilken omfattning?
Ca. 5-10 personer.

### A2. Pågår arbetet stötvis eller kontinuerligt?
Kontinuerligt då det nästan alltid finns ett projekt / uppdrag som kräver kartläggning / uppdatering / framtagning av nya modeller.

### A3. Är det ett jobb som görs i samband med framtagning av nya system i huvudsak?
Ja, men inte uteslutande, se ovan.

### A4. Vilken modelleringsstil använder ni er av (t.ex. är det UML, i så fall vilka diagram)?
Crowsfoot notation (ER-diagram) för intern modellering. För grunddatadomänen sker UMLs klassdiagram.
Viss modellering (semi-automatiska diagram) via Tietomalit.

### A5. Har ni några interna regler kring hur verktyget ska användas (t.ex. modelleringsprinciper som ska följas, undvikas etc.)?
Liten kärna av personer som modellerar.
Det finns principer, men det mesta sker informellt. T.ex. bra att använda dubbelriktade relationer i UML.

Det finns ett antal modelltyper som man utgår från vid ER modellering.

### A6. Separerar ni mellan olika nivåer av modellering? (T.ex. inom ramverket för grunddata talar man om begreppsmodeller, grunddatadomänmodeller och informationsutbytesmodeller.)
Ja, myndigheten har fler nivåer som man separerar mellan.

## B. Hur samarbetar ni kring informationsmodeller?

### B1. Är det grupparbete vid vita tavlan som sen uppdateras i verktyget av en person i efterhand?
Solitärt och grupparbete. Oftast i verktygen direkt.

### B2. Hur delar / förvarar ni modellerna, delad folder på intranät?
QualiWare har ett repository.
Confluence i övrigt, integrerat via draw.io integration.

### B3. Har ni versionshantering av modellerna?
Ja, i QualiWare. Ändringslogg i Confluence.

### B4. Hur refererar ni till delar av informationsmodellerna (gör ni det)?
Dela länkar till Confluence eller skärmdump. Extern webb finns URI:er till hela modeller.

## C. Sker någon återanvändning av informationsmodeller?

### C1. Återanvänder ni andras informationsmodeller på något sätt?
Indirekt, manuell integration.

### C2. Gör ni era informationsmodeller synliga utanför den egna organisationen?
Ja, externwebb via QualiWare när det finns en efterfrågan. Andra exportformat är möjliga men inte realiserade.

### C3. Känner ni till om någon vidareutnyttjar era informationsmodeller?
Ja, ur ett dokumentationsperspektiv, inte som en modellimport.

### C4. Har ni krav på er att återanvända eller uppmuntra återanvändning av informationsmodeller?
Arkitektgruppen ställer krav, DIGGs ramverk ställer krav.

## D. Vilka verktyg använder ni?

Avveckling sker av Qualiware, bakgrund i ledningssystem. Viss aktiv förvaltning kvarstår.
I dagsläget sker modellering i draw.io och Visio.

Exempel:
http://samverkan.bolagsverket.se/gu/ConceptModel/288841c9-624f-47bb-a007-9dbd21f2675b.html
http://samverkan.bolagsverket.se/gu/DataModelDiagram/cad45e93-c3ad-40b2-a66d-f73f9f1de2bd.html
http://samverkan.bolagsverket.se/gu/HTMLDocument/df494ff5-33db-4508-b4b8-73df079f688c.html

### D1. Exporterar ni till andra format (t.ex. utöver .eap exportera till xmi eller rena bilder)?
Webbexport från QualiWare i vissa fall.

### D2. Använder ni några extra funktioner, t.ex. UML stereotyper eller liknande?
Metodanpassning i QualiWare, inte riktigt motsvarande stereotyper.

### D3. Finns det behov som inte är tillgodosedda med verktygen ni jobbar med?
Kombinera extern och interna modeller. Hur hitta ett modernt arbetssätt som tar höjd för interoperabilitet.

### D4. Finns modellerna lättillgängliga utanför verktygen?
Qualiware webb, exporter av bilder i presentationer etc. Ej som modeller.

### D5. Är det viktigt att kunna bestämma exakt hur diagrammen ser ut? (Dvs. flyttar ni runt klasser och relationer, eller låter ni systemet göra layouten själv?)
Sannolikt behöver man kunna justera utseendet manuellt.

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
Ja.

### F2. Skulle ni sträva efter att hitta en möjlighet att automatisera så informationsmodellerna finns både lokalt och centralt?
Ja.

### F3. Är ni villiga att anpassa arbetssättet i era nuvarande verktyg för att öka interoperabiliteten med interoperabilitet med andra aktörer (och därmed också med det nationella systemstödet)?
Ja, iallafall undersöka möjligheten. Också att försöka återanvända gemensamma begrepp / klasser mellan domäner via dessa mekanismer.

### F4. Skulle ni kunna tänka er att underhålla en delmängd av informationsmodellerna i båda systemen?
Helst inte, men inte omöjligt om inget annat går.

### F5. Föredrar ni en enklare lösning där ni kan lägga upp era informationsmodeller i ett bibliotek och undvika att använda ett nationellt systemstöd?
Ja, det finns ett värde, men man behöver ta fram en governance funktion för att försöka uppmuntra till enhetlighet och hur man tar sig vidare mot ökad interoperabilitet.


## Referenser:

* [Logisk och fysiska datamodeller](https://online.visual-paradigm.com/knowledge/visual-modeling/conceptual-vs-logical-vs-physical-data-model#:~:text=The%20conceptual%20model%20is%20to,implementation%20of%20the%20data%20model)
* [XBRL taxonomi](https://xbrl.taxonomier.se/dokumentation/arsredovisning/k3/2021-rev20220524/index.html)
* [Bastjänsten för grundläggande uppgifter om företag](https://www.bolagsverket.se/omoss/utvecklingavdigitalatjanster/densammansattabastjanstenforgrundlaggandeuppgifteromforetag/dokumentationforsammansattabastjansten.2249.html)
* [Modell i Tietomallit](https://tietomallit.suomi.fi/model/ncdrm/Organization/)
