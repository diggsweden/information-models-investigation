# Översikt

Denna leverabel syftar till att ge en bakgrund vad som menas med informationsmodeller, systemstöd för informationsmodeller och relationer till annan metadata i en digital infrastruktur. Speciellt behöver koppling till ramverket för nationella grunddata samt European Interoperability Framework tydliggöras.

Innehållsförteckning

* Introduktion
* Modelleringsspråk
* Relationer till svenska och europeiska ramverk
* Stöd på dataportal idag
* Analys av interoperabiliteskrav och användning av länkade data som en väg framåt
* Användning av länkade data
* Sammanfattning

## Introduktion
Med informationsmodell menar vi de ramar som man sätts upp för att beskriva hur informationen är strukturerad. Mer konkret sker detta genom att man beskriver karaktären på ett antal (typer av) entiteter samt eventuella relationer mellan dessa.

Sedan 1970 talet har det tagits fram ett flertal olika modelleringsspråk för att beskriva informationsmodeller från Entity-Relationships diagrams, Express, UML och RDFS. De olika Modelleringsspråken skiljer sig åt både i visuellt uttryck och i vilka användningsfall / målbilder man stödjer. Nedan beskriver vi kort fyra möjliga nyttor med modelleringsspråk för informationsmodeller:

Nytta | Beskrivning
---| ---
**Deskriptiv** | Beskriva informationsmodellen på ett tillräckligt noggrant sätt för att förenkla utveckling och kravställning inom en organisation / utvecklargrupp.
**Diagram** | Skapa diagram med enhetligt visuellt uttryck som ligger till grund för kommunikation kring informationsmodellen både inom och mellan organisationer.
**Regler** | Tillhandahålla regler och semantik, dvs hur information hänger samman för att dra härleda fakta som enbart finns implicit uttryckt.
**Interoperabilitet** | Möjliggöra att informationsmodeller knyts samman och återanvänds mellan olika aktörer.

När vi tittar på behoven av systemstöd för informationsmodeller är det viktigt att förstå vilka nyttor man siktar på och därvid informera oss kring vilket / vilka modelleringsspråk man behöver stödja.

## Modelleringsspråk
Vi begränsar oss till en översikt av de två moderna modelleringsspråk som är förhärskande idag, UML och RDFS/OWL/SHACL. Vi börjar med en översiktslig bild av hur de möter nyttorna ovan:

Nytta | UML | RDFS/OWL/SHACL
---| --- | ---
**Deskriptiv** | x | x
**Diagram** | x | -
**Regler** | - | x
**Interoperabilitet** | - | x

Ur denna enkla tabell ser man att det vore optimalt om man kunde kombinera styrkan hos UML kring diagram med RDFS/OWL/SHACL för att skapa en mer komplett lösning.

### UML

UML är ett modelleringspråk som har sin grund i objektorienterad mjukvaruutveckling och används främst för att beskriva hur system är designade. UML togs fram på 90-talet för att förena den flora av olika visuella uttryck som växt fram. Sedan dess har UML standardiserats inom ISO och uppdaterats i flera omgångar. Den senaste versionen är 2.5.1 och innefattar en mängd olika diagramtyper där den som oftast används är klassdiagram vilket också den som är mest relevant för informationsmodellering. För att utbyta UML modeller finns XML baserade uttrycket XMI. 

UML togs fram med det uttryckligt syftet att stödja "round-trip engingeering" vilket betyder att man kan beskriva sina informationsmodeller och få kod, iallafall den översiktliga strukturen automatiskt genererad. Den omvända riktningen var också tänkt, dvs att man fortsätter att skriva kod och UML diagrammen hålls uppdaterade utifrån de ändringar / tillägg man gör. Detta realiserades sällan (och fungerade i allmänhet också dåligt). En viktig effekt av detta är att UML diagram har en relativt stark bindning till det objektorienterade arbetsättet och leder till att det finns konstruktioner som är för detaljerade / irrelevanta för de behov som finns kring informationsmodellering. Låt oss fokusera på klassdiagram.

Klassdiagram tillåter att man beskriver klasser med klassens namn, dess attribut och dess metoder. Attributen beskrivs med namn, datatyper, kardinalitet vilket är bra. Men de har också information om attributens synlighet (private, public, protected) samt om de är konstruktorer. Den senare informationen är implementationsdetaljer som inte behövs ur ett informationsmodelleringsperspektiv. Detsamma gäller för klassens metoder, det är inget som behövs.

Man kan också uttrycka relationer mellan klasser. Med generaliseringsrelationen uttrycker man om klasser ärver från varandra. Ur ett mer matematiskt perspektiv motsvarar en klass en mängd instanser. För generaliseringsrelationen innebär det att om vi har två klasser A och B, där A generaliserar B så innebär det att A är en delmängd av B. Dvs. generalisering är delmängdsrelationen.

De andra relationerna som uttrycks i diagramet mellan klasserna är egentligen platshållare för relationer mellan instanserna. Den viktigaste är relationen association, en association kan i princip relatera många klasser men vi kommer här fokusera på de binära associationerna. En binär association går mellan två klasser och kan vara riktad eller oriktad, man kan ge den namn samt beskriva klassernas roller och kardinalitet. T.ex. är associationen en-till-många, många-till-en eller många-till-många.

Relationerna aggregation och komposition är egentligen specialfall av associationsrelationen som innebär att man uttrycker att en klass är en del av en annan klass. Oftast innebär det att man inte namnger relationen, vilket kan bli problematiskt ur ett kompatibiltetsperspektiv.


### RDFS/OWL/SHACL

RDF är ett ramverk för att uttrycka påståenden om *ting* som identifieras med URI:er. URI:erna kan representera digitala ting som webbsidor men kan fysiska objekt som personer och platser eller mer abstrakta fenomen som organisationer, datamängder eller begrepp. Alla påståenden består av tre delar, subject, predicat och objekt. Man kallar ofta påståenden för tripplar då de består av tre delar. Subjektet är det ting som påståendet handlar om. Predikat och objekt i en trippel kan ses som ett attribut värde-par om tinget (subjektet). Precis som tinget uttrycks predikatet också alltid med URI:er, dessa URI:er kallas properties. Objektet däremot kan vara en sträng, en datatyp eller ett annat ting (då i form av en URI).

En mängd triplar kan använda samma URI:er, en del i subjektposition och en del i objektposition, tillammans bygger de upp en RDF graf. Det är möjligt att tänka sig att alla tripplar i världen bildar en gigantisk jättegraf, men i praktiken går en sådan graf aldrig att samla in. Ett mer praktiskt betraktelsesätt är att det finns många mindre grafer som är nåbara på olika webbadresser. Om det inne i graferna finns URI:erna som motsvarar ting och dessa ting motsvarar RDF grafer har vi skapat länkar till grafer. Det är detta som är kallas länkade data.

Förutom de exempel på ting som nämns ovan kan ting också vara klasser (för att dela in ting i olika mängder) och properties (som förekommer i predikatpositionen i triplar). Det språk som man använder för att definiera klasser och properties är en slags data-modelleringsvokabulär som kallas RDF Schema. RDF Schema har ett sätt att ange att ett ting är en klass eller en property, samt ett antal andra mekanismer för att beskriva dess karaktär.

En av de större skillnaderna mellan RDFS och UML är att properties kan definieras oberoende av klasser. T.ex. `dcterms:publisher` är en property som utrycker att ett ting har en utgivare. Men propertyns användningsområde behöver inte vara begränsad till böcker eller tidningar. Istället är `dcterms:publisher` definerad på ett allmänt sätt (den appliceras på den generella klassen rdf:Resource vilket alla ting är instanser av). Det innebär att när en annan standardiseringsgrupp i ett senare skede ville definiera klassen av alla datamängder, då kan man återanvända dcterms:publisher utan att bryta mot några regler.

En annan viktig skillnad är att det är väldefinierat hur man kombinerar påståenden från olika källor. Dvs om två aktörer beskriver samma ting genom att referera till tinget med samma URI så kan deras påståenden förstärka varandra. Rent praktiskt innebär det att det är väldinierat hur man slår samman två RDF grafer. T.ex. skatteverkets och trafikverkets påståenden om en person kan kombineras i en RDF graf utan att man behöver introducera nya format, nya informationsmodeller eller bygga nya system (givet att systemen använder RDF som intern modell). Detta innebär inte nödvändigtvis att skattverkets system förstår vad påståenden från Trafikverket betyder och kan agera utifrån dem på något sätt. Det avgörs av vilka klasser och properties som används och vilka skatteverket förstår. En sannolik effekt är att Skatteverkets system helt ignorerar den nya informationen fram till den punkt att man väljer att lägga till ytterligare stöd i systemet. Möjligheten att enkelt kombinera information innebär att bör vara mer uppmärksam på vilka källor man har förtroende för. Detat är förstås inget unikt för RDF med flexibiliteten gör att det blir extra tydligt.

En naturlig konsekvens av att information kan kombineras enkelt är att man då kan fokusera mer på interoperabilitetsaspekter. I praktiken vill man återanvända klasser och properties så långt som möjligt för att därmed maximera förståelsen i olika system. Samtidigt har man möjligheten att enkelt utvidga existerande informationsmodeller när klasser och propeties saknas för att uttrycka något nytt. I dagsläget finns en uppsjö av klasser och properties som etableras av olika grupperingar, internationellt, på EU nivå, nationellt, av olika intressegrupper, domän specifika uttryck osv. Att återanvända klasser och properties är idag den rekommenderade vägen framåt, men det kan ibland vara utmanande att hitta rätt. Det finns lite olika mekansismer för att formellt uttrycka hur man återanvänder klasser och properties, den mest etablerade idag kallas SHACL.

För att sammanfatta, ur ett interoperabilitetsperspektiv är det fyra saker som är särskilt användbara när man använder länkade data för informationsmodeller:

1. Att alla klasser och properties har identifierare i form av URI:er gör att det är väldefinierat hur man återanvänder dem.
2. Att properties kan definieras helt oberoende av klasser.
3. Att påståenden (RDF grafer) enkelt kan kombineras vilket lägger grunden för gemensam bearbetning och interoperabilitet.
4. Att det finns en stor mängder av genomtänkta klasser och properties som kan återanvändas direkt, kombineras på nya sätt eller förfinas. Man behöver sällan börja helt från början. 


## Relationer till svenska och europeiska ramverk

### European Interoperability Framework

EIF är en omfattande ramverk för att ge vägledning kring hur man uppnår en bättre tillgång och interoperabilitet kring publika tjänster inom EU. Ramverket innehåller hela 47 rekommendationer men då man har valt att använda en bredare definition av interoperabilitet än den vi fokuserar på i denna förstudie är inte alla relevanta att beakta.

Nedan plockar vi ut och reflekterar kort kring de rekommendationer som är av särskild vikt när det gäller hantering av informationsmodeller. 

#### Rekommendationer inom teknisk neutralitet (kapitel 2.6)

> **Recommendation 9:** Ensure data portability, namely that data is easily transferable between systems and applications supporting the implementation and evolution of European public services without unjustified restrictions, if legally possible.

Denna rekommendation har långtgående konsekvenser kring hur man designar system. Även om det inte står explicit skrivet, så är denna kravställning en av de viktigaste för att motivera att man ska ta fram, dokumentera och göra informationsmodeller och utbytesformat publikt tillgänliga.

#### Rekommendationer kring flerspråkighet (kapitel 2.10)

> **Recommendation 16:** Use information systems and technical architectures that cater for multilingualism when establishing a European public service. Decide on the level of multilingualism support based on the needs of the expected users.

Ett rimligt krav är alltså att i de lösningar man väljer bör informationsmodeller kunna hanteras / översättas till andra språk. En naturlig målsättning är att leverera metadata på både svenska och engelska.

#### Rekommendation kring identifiering och val av standarder och specifikationer (kapitel 3.1.1)

I detta kapitel talas om hur viktigt det är med att återanvända etablerade standarder / specifikationer för att uppnå interoperabilitet. I rekommendationen nedan används förkortningen NIF för *National Interoperability Framework* och också DIF som står för *Domain-specific Interoperability* Framework.

> **Recommendation 23:** Consult relevant catalogues of standards, specifications and guidelines at national and EU level, in accordance with your NIF and relevant DIFs, when procuring and developing ICT solutions.

Vad man säger är att det räcker inte med at vara tydlig med vilka informationsmodeller man använder sig av, istället ska man i första hand välja etablerade standarder och specifikationer. Notera att det finns stort överlapp med rekommendation 32. Vidare är man medveten om att etablerade standarder / specifikationer inte alltid passar, därav kommer följande rekommendation:

> **Recommendation 24:** Actively participate in standardisation work relevant to your needs to ensure your requirements are met.

Även om rekommendationen är bra, så är det intressant att notera att det ofta inte är tillräckligt. Man kan oftast inte invänta uppdateringar av en internationell / europeiskt framtagen specifikation / standard för att lösa specifika behov. Istället behöver man oftast gå vidare och hitta praktiska lösningar i stunden som sen kan argumenteras för i olika fora. Det blir också starkare argument om man kan påvisa faktiska behov och implementationer för att få acceptans för tillägg av nya aspekter i en standard / specifikation.

#### Rekommendationer inom semantisk interoperabilitet (kapitel 3.5)

I detta kapitel introducerar man semantisk interoperabilitet och definierar det som bevarandet av betydelse mellan aktörer, dvs *"what is sent is what is understood"*.

> **Recommendation 30:** Perceive data and information as a public asset that should be appropriately generated, collected, managed, shared, protected and preserved.

Här poängterar man att information inte bara är ett medel för att uppnå andra mål, t.ex. att utföra en tjänst. Istället är information / data offentliga tillångar som är värdefulla i sig. Detta perspektiv gör det enklare att motivera en nogrannare hantering, inklusive hantering av de informationsmodeller som beskriver informationen.

> **Recommendation 31:** Put in place an information management strategy at the highest possible level to avoid fragmentation and duplication. Management of metadata, master data and reference data should be prioritised.

I den förklarande texten kring rekommendation 31 talar man om vikten av nå samsyn och exponera vokabulärer, taxonomier / kodlistor och återanvändbara datastrukturer / modeller. Som konkreta exempel tas här taxonomin ESCO som uttrycks i SKOS och ett antal informationsmodeller som gemensamt brukar kallas core vocabularies, mer specifikt core person, core business, core location och core public service.

Man pekar också på hur användning av datadriven design i kombination med länkade data teknologier är innovativa sätt att förbättra semantisk interoperabiltiet utan att man skapar dubbelarbete. De exempel man ger med core vocabularies visar på hur detta kan fungera praktiskt, särskilt genom användning av så kallade applikations profiler.

> **Recommendation 32:** Support the establishment of sector-specific and cross-sectoral communities that aim to create open information specifications and encourage relevant communities to share their results on national and European platforms.

Här pekar man på hur teknisk interoperabilitet har varit en framgång i många år, men för att på ett effektivt sätt bemöta språkliga, kulturella, juridiska och administrativa skillnader är det viktigt att adressera den semantiska interoperabiliteten. Mer specifikt pekar man på att för att uppnå samsyn kring standarder /specifikationer krävs att det går att involvera relevanta grupperingar / communities och att resultaten från deras överenskommelser bör göras tillängliga i nationella och europeiska plattformar.

#### Rekommendationer inom teknisk interoperabilitet (kapitel 3.6)

> **Recommendation 33:** Use open specifications, where available, to ensure technical interoperability when establishing European public services.

Denna rekommendation poängterar att specifikationer av bland annat protokoll och interface har och fortsätter spela en stor roll för att realisera teknisk interoperabilitet. Rent praktiskt finns det massor av gamla system som växt fram inom offentlig sektor som idag kan utbyta information med sådana tekniska specifikationer.

Ett exempel är hur specifikationerna kring INSPIRE möjliggör utbyte av information om geodata. Här kan det dock vara värt att notera att det ibland saknas semantik. För att ta ett konkret exempel har man inom INSPIRE definierat hur man utbyter information om spatial data services. Vidare har man delat in dessa tjänster i *invocable*, *interoperable* och *harmonized* utan att det finns en klar konsensus om vad skillnaden faktiskt är, detta skapar långa diskussioner och osäkerhet för implementatörer.

#### Rekommendationer inom base registers (kapitel 4.3.3)

Base registers är en beteckning på de offentliga tjänster som tillhandahåller kärnan i den offentliga sektorn. Detta inkluderar information om personer, företag, fordon, licenser, byggnader, platser, vägar osv. Här finns ett stort överlappet med grunddata domänerna och det som kallas särskilt värdefulla datamängder.

> **Recommendation 38:** Develop interfaces with base registries and authoritative sources of information, publish the semantic and technical means and documentation needed for others to connect and reuse available information.

Här tydliggör man att informationen i dessa base registers bör beskrivas så att man uppnår både semantisk och teknisk interoperabilitet.

#### Rekommendationer inom öppna data (kapitel 4.3.4)

> **Recommendation 42:** Publish open data in machine-readable, non-proprietary formats. Ensure that open data is accompanied by high quality, machine-readable metadata in non-proprietary formats, including a description of their content, the way data is collected and its level of quality and the licence terms under which it is made available. The use of common vocabularies for expressing metadata is recommended.

Det är den sista meningen som är särskilt relevant där det referas till att man bör använda sig av *common vocabularies* vilket återigen pekar på att man bör jobba med länkade data principer för återanvändning av klasser och egenskaper.

### Ramverk för nationella grunddata inom den offentliga förvaltningen – bilaga informationsarkitektur

I introduktionen till [ramverket](https://www.digg.se/download/18.23524b0a17e9caeb23da7b8/1651217442229/grunddata_underlag_ramverk_informationsarkitektur_20210129.pdf) står det:

> Ramverket för nationella grunddata omfattar grafiska modeller på olika nivåer.

Vidare förtydligas det att de modeller som omfattas delas in i två kategorier, *begreppsmodeller* och *informationsmodeller* där den senare delas upp i *grunddatadomänmodell* och *informationsutbytesmodell*. Då informationsutbytesmodell syftar på datascheman som XML schema, JSON schema etc. kan vi bortse från dessa i denna studie. Kvar finns behovet av stöd för grafiska representationer av begreppsmodeller och grunddatadomänmodeller.

Ramverket säger tydligt att den grafiska modell som rekommenderas är UML.

Till skillnad från EIG så talar man i det svenska ramverket inte om interoperabilitet. Däremot säger man något som är lika starkt och kanske tydligare, både begrepp i begreppsmodellerna och klasser/ informationsobjekt i grunddatadomänmodellerna ska återanvändas. Återanvändningen beskrivs i form av att man har samma namn och definition, refererar till källan i en annan modell via en URL samt krav på att klasser / informationsobjekt ska ha attributet objektidentitet.

Ramverket pekar på vikten att återanvända standarder när så är möjligt och samtidigt tydliggörs att grunddatadomänansvariga ska ansvara för att ta fram specifikationer för att förenkla för konsumenter. Det är dock inte helt klart ur ramverkets perspektiv hur standarder och specifikationer samverkar.

Kvar att utreda är också hur man kan återanvända europeiska specifikationer som core vocabularies på ett systematiserat sätt då man behöver skapa referenser till externa definitioner för både klasser, attribut och relationer. Eventuellt kan man här förlita sig på UMLs Stereotyper, tagged values och / eller Ontology Definition Metamodel som togs fram 2014 av OMG för att representera RDFS/OWL i UML.

## Stöd på dataportal idag

På dataportalen finns idag stöd för tre saker, datamängder / API:er, terminologier / begrepp och specifikationer. Det är de två senare som är relevanta ur perspektivet informationsmodeller.

### Stöd för begrepp
De begrepp som hanteras på dataportalen ska närmast ses som koder i en kodlista eller klassifikationer i en hierarkisk taxonomi. Den standards som används är W3C rekommendationen SKOS. SKOS tillhandahåller en mängd beskrivande attribut på ett begrepp som gör att man definiera, avgränsa och ge olika alternativa namn på ett begrepp. Men när det kommer till relationer mellan begreppen är man mer begränsad. Väsentligen har man en hierarkisk relation "narrow" samt en allmän "relation" att jobba med.

Här finns risk för förvirring då det i det svenska ramverket talas om begreppsmodeller som innefattar begrepp och dess samband. Dessa begrepp kommer då närmast påminna om olika entiteter som "person", "organisation" och "plats". De relationer som finns mellan dem passar inte att representera i en hierarki då sambandet inte fångas av vare sig "narrow" eller den mer allmänna "relation". 

Slutsaten blir här att begrepp som hanteras på dataportalen passar väl för att representera värden för attribut på klasser inte klasserna själva. Det vill säga, terminologier och de begrepp som de innefattar bör ses som byggstenar när man tar fram informationsmodell.

### Stöd för specifikationer
De specifikationer som beskrivs på dataportalen följer metadataprofilen PROF som är ett initiativ från en arbetsgrupp på W3C för hur man beskriver specifikationer (där specifikationer innefattar både mer formella standarder, profiler av standarder och mer domänspecifika specifikationer). En viktig princip i PROF är att man inte betraktar en specifikation som ett dokument. Istället betraktar man en specifikation som ett samling av kompletterande resurser. Här är några exempel på resurser som en specifikation kan innefatta:

* Specifikationsdokument
* Informationsmodell
* Dataschema (t.ex. XML schema)
* Exempeldata
* Valideringar
* Terminologier
* Vägledningar

Här ser vi hur specifikationer hjälper till att skapa den överblick som behövs för hur informationsmodeller, datascheman, terminologier och en mängd andra resurser tillsammans målar upp en bild om hur en datamängd ska förstås.

Det är viktigt att notera att genom att specifikationer finns representerade på detta sätt kan stöd för hantering av informationsmodeller vara ett erbjudande och inte ett krav. De som väljer att skapa informationsmodeller på andra sätt än via ett nationellt systemstöd kan fortfarande delta och exponera sina specifikationer.

Mer konkret betyder det att även framöver blir det möjligt att rita ett UML diagram för hand och ladda upp som en bild till en specifikation. Att ett sådant alternativ finns är viktigt då en informationsmodell i form av en bild är bättre än ingenting alls. 

Samtidigt är det viktigt att för de som använder ett tilltänkt nationellt systemstöd för att skapa sina informationsmodeller ska kunna knyta dem enkelt till sina specifikationer (utan att det sker som export av en bild). En informationsmodell i ett systemstöd kan ge en rikare bild av specifikationen, särskilt då den kombineras med andra resurser.

## Analys av interoperabiliteskrav och användning av länkade data som en väg framåt

### Interoperabilitet

Om två system kan utbyta information och agera på informationen på ett sätt som är i enlighet med den ursprungliga intentionen kan man säga att man uppnått interoperabilitet. Ett vanligt sätt att åstadkomma interoperabilitet är att noggrant beskriva hur informationen är strukturerad och hur den ska tolkas i en dataspecifikation.

Tyvärr blir det snabbt mer komplicerat om flera olika system behöver utbyta information och de har olika behov som inte täcks av en enskild specifikation. T.ex. är det vanligt att man hamnar i situationer där man behöver stödja flera specifikationer med delvis överlappande information. Noggrann beskrivning hur datat ska tolkas, semantik, blir nu extra viktigt.

I grunden för all semantik ligger förmågan att referera till begrepp (ofta i form av klasser, egenskaper, kodlistor etc.) som man har en delad förståelse kring. Utifrån sådana etablerade begrepp kan vi bygga upp en modell för hur vi ska förstå vår data, antingen via formella språk som predikatlogik och mängdlära eller mer informellt via naturliga språk. Ontologier är modeller som i stor utsträckning förlitar sig på formella språk för att beskriva hur datat får uttryckas, men även här behövs oftast naturligt språk som komplement för att förtydliga skillnaden mellan olika begrepp.

Det finns en växande förståelse för värdet att återanvända begrepp mellan modeller. Att kunna sätta samman en modell genom att identifiera en mängd relevanta etablerade begrepp, förfina och begränsa när så behövs och skapa helt nya när inga passande finns att tillgå är ett angreppssätt som är grundbulten inom länkade data. Modeller över data som i stor utsträckning kombinerar etablerade begrepp kallas applikationsprofiler snarare än ontologier. Återanvändning av begrepp mellan modeller ger oss en djupare form av interoperabilitet som vi kallar harmonisering.

Term | Målsättning
--- | ---
Interoperabilitet | Återanvända data
Harmonisering | Återanvända begrepp och modeller för data


## Användning av länkade data

För att möta kraven på interoperabilitet och återanvändning av både data och informationsmodeller bör man följa principerna bakom länkade data, detta grundar sig både i kravbilden och i de riktlinjer som tagits fram inom European Interoperability Framework.
För informationsmodeller innebär länkade data bland annat att metadata om klasser och egenskaper (properties) etableras med globala identifierare (URI:er). Metadatan om klasserna och egenskaperna tillhandahåller också semantik, både i form av ett formellt språk som relaterar klasser och egenskaper med varandra, men också i form av beskrivningar uttryckta i naturligt språk.

En viktig princip hos länkade data är att man tillåts definierar egenskaper (properties) mer eller mindre oberoende av klasser. Dessutom används klasser ofta mer som en markör av vad ett ting är snarare än som ett sätt att beskriva exakt vilka egenskaper det ska ha. T.ex. om Skatteverket väljer att återanvända klassen Person definierad i EU vokabulären Core Vocabularies Person för att representera alla personer som är folkbokförda i Sverige så är det en god ide om Försäkringskassan som har överlappande behov också göra det. Samtidigt har Försäkringskassan och Skatteverket behov att uttrycka mer specifika egenskaper som inte delas, detta fångas bäst upp genom att man definierar applikations profiler.

Applikationsprofiler innebär en förtydling om vilken data (information om ting i form av egenskaper) man förväntas uttrycka / acceptera i ett givet sammanhang (applikation). Användningen av applikationsprofiler innebär att informationsmodeller (klasser och egenskaper) kan återanvändas i stor utsträckning både inom och mellan olika domäner.

För att uppmuntra återanvändning av klasser och egenskaper (properties) behöver man ofta definiera egenskaperna, särskilt användningen av applikationsprofiler att föredra.

Observera att bara för att man använder länkade data och därmed RDF för att uttrycka informationsmodeller så betyder inte det att datat självt måste uttryckas som RDF. Det är helt legitimt och normalt att hitta på andra uttryck för datat i CSV, JSON, XML osv. Men det är förstås bra om man förtydligar hur uttrycket förhåller sig till informationsmodellen, man vill att det ska finnas sätt att översätta mellan olika uttryck via informationsmodellen. Notera att det finns mekanismer i en del datascheman för att formellt specificera kopplingen till informationsmodellen, t.ex. ett "context" i JSON som gör att det blir JSON-LD eller ett CSV schema för CSV.

## Sammanfattning

Det är tydligt att idag finns inget självklart val av modelleringsspråk som täcker alla behov. Väljer man att förlita sig på UML så tappar man aspekter kring interoperabilitet. Väljer man istället att fokusera på enbart länkade data i form av RDFS/OWL/SHACL så får man istället problem med att etablera bra grafiska / visuella representationer i form av diagram som många förstår.

Vi ser också att det finns en stark rörelse mot användning av länkade data på europeisk / internationell nivå, särskilt då det är de enda exemplen som tas i European Interoperability Framework (t.ex. core vocabularies).

Samtidigt poängteras i det svenska nationella ramverket kring grunddata hur viktigt de grafiska / visuella representationerna av informationsmodeller är.

Utifrån det perspektivet blir det extra viktigt när man tittar på systemstöd för informationsmodeller att se om det går att hitta system som hanterar både aspekter kring interoperabilitet och fortfarande har en visuell karaktär.

Slutligen finns stora vinster i hur hanteringen av informationsmodeller kan integreras med hanteringen av specifikationer på dataportalen. Särskilt blir det intressant när kopplingar mellan datamängder och deras specifikationer görs explicita.

Ytterligare fördelar uppnås när man informationsmodeller skapas med återanvändning av klasser och egenskaper. Först och främst innebär det att man uppnår interoperabilitet i större utsträckning, både inom Sverige och i Europa. Utöver detta kan det också bli möjligt att se hur datamängder kan komplettera eller förstärka varandra då de har överlappande information. I praktiken skulle man kunna tänka sig en rubrik "Se relaterade/kompletterande datamängder" på en datamängds landningssida på dataportalen. 
