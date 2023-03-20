# Transformatieplan

## Technische infrastructuur

Het Museum bewaart vijf soorten collecties. Het belangrijkste voor de eerste stap naar OSLO is de collectie “personen”.

* Wat: De collectie ‘personen’ bestaat uit historische persoonsgegevens van militairen die een verband hebben met de Slag bij Passendale.
* Beheer en ontsluiting: Deze gegevens worden ontsloten op de Passchendaele Archives website / geoportaal en beheert op het achterliggende MySQL server.
* Deze gegevens verrijken we (of willen we verrijken) met collectiedata en geografische informatie (plaatsen, coördinaten, etc.)

Transformatie van de huidige databank naar OLSO (a.d.h.v. 20221109\_SQL\_OSLO\_complexiteit\_haalbaarheid\_MMP1917)

* Meemoo stelt twee opties voor:
  * Optie 1: Een extensie bovenop de bestaande SQL-databank om output in JSON LD te krijgen.
  * Voordeel: de invoerinterface blijft behouden en is de goedkoopste optie.
  * Nadeel: het huidige relationele model moet herwerkt worden en is nadien “bevroren”.
*   Optie 2: Een nieuwe linked data oplossing (triple store of graph databank) vervangt de huidige SQL databank.

    * Voordeel 1: het datamodel is eenvoudiger, flexibeler en makkelijker uitbreidbaar,&#x20;
    * Voordeel 2: via dezelfde endpoint kunnen wijzigingen of verrijking binnen getrokken worden (en is ten opzichte van optie 1 niet enkel éénrichtingsverkeer).
    * Nadeel: grotere investering, momenteel vrij lage adoptiegraad van deze technologie.


*   Het Passchendaele Museum kiest voor optie 1.

    * Het uitbouwen van een extensie bovenop de bestaande databank is momenteel realistischer, aangezien de OSLO standaard voor cultureel erfgoed vrij nieuw is (onduidelijk toekomstperspectief) en grote investerngingen voorlopig moeilijk te verantwoorden zijn.
    * Het “bevriezen” van het relationele model hoeft niet noodzakelijk een probleem te zijn. Het huidige model is organisch gegroeid doorheen het project, wat een algemene evaluatie en aanpassing noodzakelijk maakt (onafhankelijk van het OLSO-project). Tijdens deze evaluatie zal rekening houden met de noden van de OSLO standaard.


* Technologische oplossingen voor optie 1.
  *   Miel Vander Sande (meemoo) raadt deze optie ook aan omdat hier al oplossingen voor bestaan:

      * [R2RML](https://www.w3.org/TR/r2rml/) als taal om relationele databanken mappen naar semantisch model (RDF).
      * [Ontop ](https://ontop-vkg.org/)(opensource) of [Ontopic Studio](https://ontopic.ai/en/ontopic-studio/) (betalend) zijn twee mogelijke softwares om R2RML te implementeren.


* De gevaren / nadelen van deze technologische oplossing:
  * Technische partners / ontwikkelaars moeten R2RML eigen maken.
  * De R2RML-taal heeft een vrij steile leercurve.
  * Er is kennis “in house” nodig om de stap naar LOD te maken.

## Inschatting benodigde middelen

Projectmedewerker (Wouter De Witte) werkte onder begeleiding van meemoo in de context van hun engagement binnen het Collectie van de Gentenaar project een concrete use-case en transformatieplan uit:

* Ca. 110 uren (ca. 15 werkdagen) aan weddeschaal B. Dit omvat de vijf workshops, zelfstudie en opmaken van de veldtekening en de use case).
* Het feit dat dit traject uitgevoerd kon worden binnen het kader van de subsidie ‘inhaalbeweging digitale collectiedata’ was een groot voordeel.
  * Zonder deze subsidie zou het bijna onmogelijk zijn geweest om dit te realiseren binnen de context van het huidige personeelsbestand van ons regionaal museum, waar digitalisering slechts een fractie is van de bredere functie 'publieksmedewerker'.
  * Betekent dit dat een OSLO implementatie enkel mogelijk is voor grote organisaties? Neen. Je moet niet persé beschikken over een digitaal team. Wat wel nodig is, is een personeelslid die kennis heeft van de collectie, een basiskennis heeft over digitale/ICT-concepten en die - gedurende een aaneengesloten periode - tijd kan investeren in het bijleren van de Linked Data technologie.
* Door de stimulans van het subsidieproject beschikt het museum nu over een fundament waarop verder gebouwd kan worden. Het nadeel hiervan is dat het huidige vaste museum-team een OSLO-project niet kan dragen na 1 januari 2024. Hiervoor zou er een nieuwe werkkracht moeten bijkomen of - beter nog - dat de in het traject opgedane expertise van de huidige tijdelijke werkkracht geborgd wordt door deze opdracht te verlengen.

Technische partners (Citybeats vzw): transformatie van bestaande databank naar linked open data volgens de OSLO uitwisselingsstandaard. Zij verdelen de ingeschatte tijd en middelen in drie onderdelen, namelijk het aanleren van de technologie en de programmeertalen, het op orde stellen van de huidige databank in functie verder uitbouw en de effectieve implementatie van de gekozen LOD-oplossing.

| Taak                                                                                                                                                                                                                                                                                                     | Geschatte duur                                              | Kostprijs         |
| -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------- | ----------------- |
| <p>Opleidingen LOD/OSLO</p><ul><li>Analyse van de systeemopbouw</li><li>Onderzoek en aanleren van de bestaande componenten (zie advies Miel Van Der Sande (meemoo))</li><li>Aanleren van de programmeertaal R2RML</li></ul>                                                                              | +-180 - 200 uur                                             | €18.000 - €20.000 |
| <p>Aanpassingen aan de huidige opbouw van de PA-database</p><ul><li>De huidige SQL-database is voorlopig niet voorzien op de OSLO implementatie.</li><li>Als het bestaande relationele model bevroren zal worden, is belangrijk om dit model grondig te evalueren en waar nodig aan te passen.</li></ul> | +- 30 - 50 uur                                              | €3.000 - €5.000   |
| <p>OSLO implementatie </p><ul><li>Dit onderdeel beschrijft de implementatie van OSLO via R2RML en Ontop.</li><li>De duur van de implementatie is sterk afhankelijk van uiteindelijk gekozen oplossing (hetzij een product “off the shelf” of een volledig eigen ontwikkeling).</li></ul>                 | +- 100 - 150 uur                                            | €10.000 - €15.000 |
| Totaal                                                                                                                                                                                                                                                                                                   | <p>+- 310-400 uur of</p><p>38 à 50 werkdagen</p><p><br></p> | €31.000 - €40.000 |

\


## Link naar use-case

* Het centrale idee van de use case is de ontwikkeling van een kennisnetwerk op basis van verschillende gegevensbronnen.
  * Er bestaan al heel wat gegevens en databases over WOI, elk vergelijkbaar met de andere maar met een unieke invalshoek.
  * De gegevens uit deze databases zijn zelden (her)bruikbaar. Ze blijven vaak steken binnen organisaties.
* Een mogelijke concretisering van dit "kennisnetwerk" is een gemeenschappelijke interactieve kaart of routeplannerapplicatie op basis van gekoppelde gegevens van verschillende erfgoedorganisaties.
* Deze applicatie suggereert een route door het lokale landschap op basis van de voorkeuren of interesses van de gebruiker. Het pad verbindt locaties of punten over een persoon, object of verhaal.
* Als meer (erfgoed)organisaties hun gegevens als linked data publiceren, kan de applicatie deze gegevens ook aan gebruikers tonen. Dit vergroot de zichtbaarheid van alle collecties in de regio.
  * bv. Een route over soldaten die stierven in de buurt van Passendale, gebaseerd op gegevens van het Passendale Museum en het In Flanders Fields Museum.
  * bv. Een route over de recuperatie van oorlogsmateriaal tijdens de wederopbouw, aangevuld met gegevens over wederopbouwwoningen van Agentschap Onroerend Erfgoed.
  * bv. Een route die museumobjecten verbindt met locaties in het landschap. Deze objecten zijn afkomstig uit de collectie het Talbot House en Passendale Museum.
* Het projectplan beschrijft mogelijkheden voor WWI-LOD in het algemeen, maar de applicatie routeplanner is een goede eerste, concrete use case.
