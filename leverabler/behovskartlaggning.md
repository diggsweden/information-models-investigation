# Behovskartläggning

Behovskartläggningen har genomförts i fem steg:

1. Framtagning av lämpliga frågor
2. Dialoger med ett antal aktörer utifrån frågor
3. Sammanfattning av dialoger och rapportering till aktörer
4. Framtagning av scenarier för att möta behoven
5. Workshop kring scenarier

## 1. Framtagning av frågor

För att få en mer enhetlig dialog med de olika aktörerna togs 30 frågor fram indelat i 6 kategorier:

- A. Hur jobbar ni med informationsmodeller idag. 6 frågor.
- B. Hur samarbetar ni kring informationsmodeller? 4 frågor.
- C. Sker någon återanvändning av informationsmodeller? 4 frågor.
- D. Vilka verktyg använder ni? 5 frågor.
- E. Hur använder ni er av informationsmodeller? 6 frågor.
- F. Hur skulle ett nationellt systemstöd för informationsmodeller påverka er? 5 frågor.

Alla frågorna finns att läsa i ett [separat dokument](../dialoger/fragor.md).

## 2. Dialoger med aktörer

Möten bokades in med 6 olika aktörer. Innan mötena efterfrågades följande roller kunde vara representerade, vilket realiserades i flera av fallen:


1. Någon som är införstådd och har förskunskap om förstudien.
2. Någon som jobbar aktivt med informationsmodellering inom myndigheten idag, gärna jobbar med specifika verktyg som Enterprise Architect eller liknande.
3. Någon som jobbar som mottagare av informationsmodellerna i verksamheten, t.ex. med utveckling / kravställning av system.

Resultatet av respektive dialog finns i separata dokument:

* [Grunddatadomän Person](../dialoger/skatteverket.md)
* [Grunddatadomän Transportsystem](../dialoger/trafikverket.md)
* [Naturvårdsverket](../dialoger/naturvardsverket.md)
* [Grunddatadomän företag](../dialoger/bolagsverket.md)
* [Grunddatadomän Fastighets- och geografisk information](../dialoger/lantmateriet.md)
* [Grunddatadomän hälsa, vård och omsorg](../dialoger/ehalsomyndigheten.md)

## 3. Sammanfattning av dialogerna

Följande dokument är en sammanställning av svaren från alla aktörer:
[Sammanfattning av dialogerna](../dialoger/sammanfattning.md)

## 4. Framtagning av scenarier

Sammanfattningen visade att det fanns både stora likheter och skillnader mellan de olika aktörerna. De viktigaste observationerna var:

1. Informationsmodeller delas både inom och mellan organisationer men det sker idag på olika sätt.
2. Arbetssättet inom de olika organisationerna varierar men det finns också stora likheter, t.ex. använder nästan alla UML klassdiagram eller motsvarande.
3. Det finns stora beroenden till verktyg som man behöver ta hänsyn till.
4. Det finns en vilja att anpassa hur man jobbar, men det är viktigt att hitta realistiska lösningar och tydliggöra vad man vinner med ett ändrat arbetssätt.
5. En lösning måste möjliggöra gradvis anpassning från ett enklare bibliotek av informationsmodeller till full interoperabilitet.

Följande fyra scenarior har tagits fram, se [separat dokument](scenarior-modeller.md) för en längre diskussion om dessa scenarier och de komponenter de beror av.

### Scenario A - Nationellt bibliotek av informationsmodeller
Informationsmodeller samlas in till ett nationellt bibliotek för att möjliggöra sökning, filtrering och utforskning, typiskt i anslutning till den nuvarande dataportalen. Olika modelleringsparadigm och format kan samexistera då man inte gör några försök att titta in i informationsmodellerna. Informationsmodellerna är i huvudsak uttryckta som UML klassdiagram.

### Scenario B - Nationellt bibliotek av informationsmodeller och informationselement
Informationselement i form av i huvudsak klasser och egenskaper detekteras i de insamlade informationsmodellerna och exponeras i biblioteket så de kan utforskas. Informationselement uttrycks i enlighet med länkade data principer men kan extraheras ur UML. Återanvändning mellan aktörer synliggörs då samma informationselement återfinns i olika informationsmodeller.

### Scenario C - Nationellt verktyg för informationsmodeller och informationselement
Ett nationellt verktyg etableras som möjliggör uttryck av informationselement både på ett formellt sätt och i diagramform. Aktörer kan jobba i verktyget helt oberoende av varandra, bygga informationsmodeller som utvidgar varandras eller till och med använda verktyget som en samarbetsplattform. Man kan dock bara bygga vidare på informationsmodeller som byggts inom verktyget.

### Scenario D - Nationellt bibliotek och verktyg för informationsmodeller och informationselement
I detta scenario kan aktörer välja själva om de vill jobba i det nationella verktyget eller fortsätta att jobba i sina lokala verktyg och få sina informationsmodeller med informationselement insamlade till det nationella biblioteket. I det nationella verktyget kan man bygga nytt eller bygga vidare på både det som skapats direkt i verktyget och det som samlats in till det nationella biblioteket.

## 5. Workshop kring scenarior

En workshop hölls kring sammanfattningen av dialogerna samt slutsatserna i form av scenarior. Workshoppen [innefattade en presentation](https://docs.google.com/presentation/d/13m_GIoAGZme_Qci1ev4koSywH9lP5Pm_9kDDTWgwhPA/edit?usp=sharing) ([pdf version](../workshops/workshop1.pdf)) och den efterföljande diskussionen handlade både om scenarios och behovet att klargöra vilka fördelar som ett nationellt systemstöd skulle innebära.  

Det poängterades att de fyra scenariorna sannolikt inte bör ses som fyra olika val utan som en progression mot ett starkare systemstöd. Det är värt att notera att det är först när man når till scenariot D som värdeerbjudandet av ett nationellt systemstöd för informationsmodeller blir riktigt starkt. Värdet blir här i form av både en tidsvinst i modelleringsfasen och enklare samverkan med andra aktörer då man är interoperabel i större utsträckning redan från början. Det finns också fördelar i att det finns mer guidning kring hur man ska tänka kring informationsmodellering och ett gemensamt språkbruk. Förhoppningsvis leder systemstödet och fram till mindre dubbelarbete och öppnar upp för mer transparans, innovation och effektivering.