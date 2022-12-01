# Sammanfattning av dialoger
För att få en enklare översikt sammanfattar vi de olika aktörerna på följande sätt:
Aktör | Kortnamn
--- | ---
Grunddatadomän Person | Person
Grunddatadomän Transportsystem | Transport
Naturvårdsverket | Natur
Grunddatadomän företag | Företag
Grunddatadomän Fastighets- och geografisk information | Fastighet
Grunddatadomän hälsa, vård och omsorg | Hälsa

## A. Hur jobbar ni med informationsmodeller idag.

### A1. Hur många är inblandade och i vilken omfattning?
Aktör | Resultat
--- | ---
Person | 10-15
Transport | 5-30 (spann motsvarar tre myndigheter)
Natur | 10-20
Företag | 5-10
Fastighet | ca 10
Hälsa |

### A2. Pågår arbetet stötvis eller kontinuerligt?

Aktör | Resultat
--- | ---
Person | Pågående
Transport | Både och
Natur | Pågpende
Företag | Kontinuerligt
Fastighet | Stötvis, projektdrivet
Hälsa |

### A3. Är det ett jobb som görs i samband med framtagning av nya system i huvudsak?

Aktör | Resultat
--- | ---
Person | Ja, bygga vidare på existerande modeller.
Transport | Ja
Natur | Ja, huvudsakligen
Företag | Ja, huvudsakligen
Fastighet | Ja, huvudsakligen
Hälsa |

### A4. Vilken modelleringsstil använder ni er av (t.ex. är det UML, i så fall vilka diagram)?

Aktör | Resultat
--- | ---
Person | Klassdiagram
Transport | Klassdiagram / oklart
Natur | Klassdiagram
Företag | ER-diagram, Klassdiagram, RDFS/SHACL
Fastighet | Klassdiagram
Hälsa |

### A5. Har ni några interna regler kring hur verktyget ska användas (t.ex. modelleringsprinciper som ska följas, undvikas etc.)?

Aktör | Resultat
--- | ---
Person | Vägledning för principer & verktyg
Transport | Vägledning finns / oklart
Natur | Vägledning för principer & verktyg
Företag | Vägledning finns (mycket sker informellt dock)
Fastighet | Vägledning för principer & verktyg
Hälsa |

### A6. Separerar ni mellan olika nivåer av modellering? (T.ex. inom ramverket för grunddata talar man om begreppsmodeller, grunddatadomänmodeller och informationsutbytesmodeller.)

Aktör | Resultat
--- | ---
Person | Ja, begrepp och grunddatadomänmodeller
Transport | Ja / oklart
Natur | Ja, begrepp och grunddatadomänmodeller
Företag | Ja
Fastighet | Ja, begrepp och grunddatadomänmodeller
Hälsa |

## B. Hur samarbetar ni kring informationsmodeller?

### B1. Är det grupparbete vid vita tavlan som sen uppdateras i verktyget av en person i efterhand?

Aktör | Resultat
--- | ---
Person | Grupparbete, ofta direkt i verktyg
Transport | Enskilt, visst grupparbete
Natur | Enskilt, visst grupparbete
Företag | Enskilt, visst grupparbete
Fastighet |
Hälsa |

### B2. Hur delar / förvarar ni modellerna, delad folder på intranät?

Aktör | Resultat
--- | ---
Person | Databas
Transport | Databas
Natur | Databas
Företag | Databas + Confluence
Fastighet |
Hälsa |

### B3. Har ni versionshantering av modellerna?

Aktör | Resultat
--- | ---
Person | Flytta mellan repositorys 
Transport | Backuper av databas
Natur | Backuper av databas + manuella backupper
Företag | Ja
Fastighet |
Hälsa |

### B4. Hur refererar ni till delar av informationsmodellerna (gör ni det)?

Aktör | Resultat
--- | ---
Person | Länka in klasser i repository 
Transport | Via namn
Natur | Länk till internwebb, bilder
Företag | Länkar, confluence (internwebb) & externwebb (QualiWare)
Fastighet | 
Hälsa |

## C. Sker någon återanvändning av informationsmodeller?

### C1. Återanvänder ni andras informationsmodeller på något sätt?

Aktör | Resultat
--- | ---
Person | Nej
Transport | Ja manuell integration
Natur | Ja
Företag | Ja manuell integration
Fastighet | 
Hälsa |

### C2. Gör ni era informationsmodeller synliga utanför den egna organisationen?

Aktör | Resultat
--- | ---
Person |  Ja, olika format på webb
Transport | Nej
Natur | Ja, informellt
Företag | Ja, externwebb via QualiWare vid efterfrågan
Fastighet |
Hälsa |

### C3. Känner ni till om någon vidareutnyttjar era informationsmodeller?

Aktör | Resultat
--- | ---
Person | Ja
Transport | Ja
Natur | Ja, planerat
Företag | Ja för dokumentation
Fastighet |
Hälsa |

### C4. Har ni krav på er att återanvända eller uppmuntra återanvändning av informationsmodeller?

Aktör | Resultat
--- | ---
Person | Nej
Transport | Nej
Natur | Nej (bara självpåtagna krav)
Företag | Mjuka krav (arkitekturgrupp, DIGGs ramverk)
Fastighet |
Hälsa |

## D. Vilka verktyg använder ni?

Aktör | Resultat
--- | ---
Person | Sparx EA
Transport | Sparx EA, QualiWare, MooD, Visio 
Natur | Sparx EA
Företag | QualiWare (avvecklas), draw.io, Visio
Fastighet | Sparx EA
Hälsa |

### D1. Exporterar ni till andra format (t.ex. utöver .eap exportera till xmi eller rena bilder)?

Aktör | Resultat
--- | ---
Person | XMI, PDF
Transport | Bilder, PDF, Word
Natur | HTML (internt)
Företag | HTML
Fastighet |
Hälsa |

### D2. Använder ni några extra funktioner, t.ex. UML stereotyper eller liknande?

Aktör | Resultat
--- | ---
Person | Ja, MDG technologies
Transport | Nej (dvs. inte modelleringsfunktioner)
Natur | Ja
Företag | Metodanpassning i QualiWare
Fastighet |
Hälsa |

### D3. Finns det behov som inte är tillgodosedda med verktygen ni jobbar med?

Aktör | Resultat
--- | ---
Person | Återanvändning av attribut mellan klasser
Transport | Förenklat gränssnitt
Natur | Enklare versionshantering, bättre webb, bättre hantering av beroenden till andra modeller
Företag | Kombinera externa & interna modeller, modernt arbetssätt med stöd för interoperabilitet
Fastighet |
Hälsa |

### D4. Finns modellerna lättillgängliga utanför verktygen?

Aktör | Resultat
--- | ---
Person | Word, HTML, PDF
Transport | Webb (inte för Transportstyrelsen)
Natur | Webb (internt)
Företag | Webb, bilder
Fastighet |
Hälsa |

### D5. Är det viktigt att kunna bestämma exakt hur diagrammen ser ut? (Dvs. flyttar ni runt klasser och relationer, eller låter ni systemet göra layouten själv?)

Aktör | Resultat
--- | ---
Person | Ja
Transport | Ja
Natur | Ja
Företag | Ja
Fastighet |
Hälsa |

## E. Hur använder ni er av informationsmodeller?

### E1. För kommunikation inför framtagande av system?

Aktör | Resultat
--- | ---
Person | Ja
Transport | Ja
Natur | Ja
Företag | Ja
Fastighet | Ja
Hälsa | Ja

### E2. För dokumentation syfte och framtida underhåll av system?

Aktör | Resultat
--- | ---
Person | Ja
Transport | Ja
Natur | Ja
Företag | Ja
Fastighet | Ja
Hälsa | Ja

### E3. För kravställning av system?

Aktör | Resultat
--- | ---
Person | Ja
Transport | Ja
Natur | Ja
Företag | Ja
Fastighet | Ja
Hälsa | Ja

### E4. För roundtrip engineering?

Aktör | Resultat
--- | ---
Person | Nej
Transport | Nej
Natur | Nej
Företag | Nej
Fastighet | Nej
Hälsa | Nej

### E5. För kommunikation mellan olika grupperingar, t.ex. arkitekturgrupp och utvecklargrupp.

Aktör | Resultat
--- | ---
Person | Ja
Transport | Ja
Natur | Ja
Företag | Ja
Fastighet | Ja
Hälsa | Ja

### E6. För att stärka ett enhetligt språkbruk och förståelse inom organisationen?

Aktör | Resultat
--- | ---
Person | Ja
Transport | Ja
Natur | Ja
Företag | Ja
Fastighet | Ja
Hälsa | Ja

## F. Hur skulle ett nationellt systemstöd för informationsmodeller påverka er?

### F1. Skulle ni undersöka möjligheten att byta?

Aktör | Resultat
--- | ---
Person | Nej
Transport | Ja
Natur | Ja
Företag | Ja
Fastighet |
Hälsa |

### F2. Skulle ni sträva efter att hitta en möjlighet att automatisera så informationsmodellerna finns både lokalt och centralt?

Aktör | Resultat
--- | ---
Person | Nej
Transport | Ja
Natur | Ja
Företag | Ja
Fastighet |
Hälsa |

### F3. Är ni villiga att anpassa arbetssättet i era nuvarande verktyg för att öka interoperabiliteten med interoperabilitet med andra aktörer (och därmed också med det nationella systemstödet)?

Aktör | Resultat
--- | ---
Person | Ja (för grunddatadomänen)
Transport | Ja
Natur | Kanske
Företag | Ja (undersöka möjligheten iallafall)
Fastighet |
Hälsa |

### F4. Skulle ni kunna tänka er att underhålla en delmängd av informationsmodellerna i båda systemen?

Aktör | Resultat
--- | ---
Person | Nej (om nödvändigt bara grunddatadomänen)
Transport | Nej
Natur | Nej
Företag | Helst inte (om inget annat går)
Fastighet |
Hälsa |

### F5. Föredrar ni en enklare lösning där ni kan lägga upp era informationsmodeller i ett bibliotek och undvika att använda ett nationellt systemstöd?

Aktör | Resultat
--- | ---
Person | Tveksamt
Transport | Ja, om brist på tvingande regleringar
Natur | Ja, definitivt
Företag | Ja (behövs governance)
Fastighet |
Hälsa |
