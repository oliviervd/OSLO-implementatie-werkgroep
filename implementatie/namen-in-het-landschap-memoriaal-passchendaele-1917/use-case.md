---
description: >-
  Bezoekers van het Memoriaal gebruiken een routeplanner om een
  gepersonaliseerde wandel- of fietstocht uit te stippelen om die plekken in
  Passendale te bezoeken waarmee zij een persoonlijke band hebben
---

# Use Case

De applicatie combineert persoonsdata van gesneuvelde soldaten uit WOI en geografische data om unieke gepersonaliseerde routes te genereren en verrijkt dit met de verhalen over de soldaten die op deze plekken gesneuveld zijn.&#x20;

Memoriaal Passchendaele 1917 zit in een regionaal netwerk van erfgoedinstellingen die vergelijkbare collecties en werking hebben: Flanders Fields Museum, Talbot House, Lijssenthoek, IJzertoren, CO7 en WHI(Willem Segers van de Belgian War Dead databank). Maar Memoriaal Passchendaele 1917 heeft ook een internationaal netwerk partners die gegevens beheren over soldaten die in Passendale gesneuveld zijn. (Commonwealth war Graves Commission, Volksbund deustsche Kriegsgraberfursorge, National Library of Canada). Memoriaal Passchendaele wil ook deze gegevens graag gebruiken in hun routeplanner.&#x20;

Het Passchendaele Museum onderzoekt of LOD een technische oplossing is die **organisatie-overschrijdende netwerk van databanken met gegevens over actoren, plaatsen, evenementen en objecten** over de slag bij Passendale te maken.&#x20;

De meerwaarde van zo een netwerk is:

1. Het (internationale) WOI-erfgoedveld bestaat uit verschillende (erfgoed)organisaties en (professionele of amateur) onderzoekers die gelijkaardige collecties beheren of onderzoeksresultaten produceren die voor het volledige erfgoedveld relevant zijn.
2. Deze organisaties en onderzoekers stellen gelijkaardige vragen en gebruiken hetzelfde bronnen bronmateriaal.
3. Het (overgrote deel van het) bronmateriaal met betrekking tot de Eerste Wereldoorlog bevindt zich vandaag in het publieke domein.
4. De kennisdeling van onderzoeksresultaten en gegevens tussen organisaties is beperkt en externe collecties zijn moeilijk vindbaar. Onderzoeken en de transformatie van bronnenmateriaal naar gegevens wordt vaak herhaald.
5. WOI-onderzoek vertrekt vaak vanuit complexe vragen dat actoren, plaatsen, evenementen en objecten met elkaar in verband brengen (bv. de historische waarde van objecten hangt af van de historische context).

De lange termijn doelstelling van deze samenwerking is:

1. Het creëren van een gezamenlijk corpus van WOI gegevens en hergebruik ervan mogelijk maken.
2. Het bundelen van de krachten van verschillende organisaties.
3. Het faciliteren van complexe vragen in functie van onderzoek, collectiemobiliteit en publiekswerking.

Memoriaal Passchendaele 1917 is naar aanleiding van dit traject met een rondvraag begonnen i.v.m. technische infrastructuur, (technische) partners, noden/wensen en mogelijke koppelingen i.v.m. hergebruik.

## Data

De databank [Passchendaele Archives Database](https://archives.passchendaele.be/nl/) verzamelt historische persoonsgegevens van militairen die sneuvelden in WO1. De gegevens in de databank zijn verzameld uit publiek toegankelijke bronnen. Het gaat enerzijds om gegevens uit nationale slachtofferlijsten (The Commonwealth War Graves Commission, Volksbund Deutsche Kriegsgräberfürsorge, etc.) nationale en internationale archieven (bv. The National Archives, National Library of Canada, etc.), literatuur (bv. regimentsgeschiedenissen), gegevens uit historische objecten en objecten/documentatie (digitaal) ter beschikking gesteld door nabestaanden.

De databank bevat:

* persoonsgegevens (bv. geboortedatum, sterfplaats (eigennaam))
* militaire persoonsgegevens (bv. eenheid, rang, datum van indiensttreding)
* geografische data:&#x20;
  * Plaatsen (bv. Mosselmarkt, Passendale)
  * Coördinaten (bv. sterfplaats)
* beeldmateriaal (bv. portretfoto’s)
* onderzoeksresultaten (in tekstvorm; zie “mijn verhaal”)
* bronnen (link met archieven, boeken, artikelen, websites etc.)

De databank ontstond in 2006 en is sinds 2016 digitaal. Deze relationele databank (MySQL) is organisch ontstaan en is over de jaren heen aangepast aan de veranderende noden van het museum. Ook vandaag staan er verbeteringen/ wijzigingen op de planning, zoals de connecties van personen met objecten (bv. bronnen of collectiestukken) of evenementen (bv. de ‘[Inname van Westhoek](https://en.wikipedia.org/wiki/Capture\_of\_Westhoek)’).

Een subset van deze dataset wordt via geoportaal ‘[Namen in het Landschap](https://passchendaele.be/kenniscentrum-2/namen-in-het-landschap/)’ publiek toegankelijke en doorzoekbaar gemaakt. Dit online portaal geeft weer waar meer dan 1.400 gesneuvelde Canadezen sneuvelden of vermoedelijk begraven werden. Door persoonlijke en militaire data toe te voegen, wil het museum deze verhalen bewaren en ontsluiten. Iedereen kan hiertoe bijdragen door informatie op het portaal te delen.

## Verwachte (her)gebruik

**Gebruik**

Toeristen gebruiken de applicatie.

**Hergebruik**

Eens vernetwerking van deze verschillende datasets voor de specifieke use-case van de routeplanner gebeurd is, kunnen andere afnemers met hun specifieke use-case aan de slag.

**Organisaties en onderzoekers** kunnen gegevens uit de kennisbank hergebruiken voor:

* onderzoek:
  * door de mogelijkheid om complexe vragen te stellen en de voordelen van grote datasets.
* collectiemobiliteit:
  * door de toegenomen zichtbaarheid van minder bekende of internationale collecties
* publiekswerking:
  * door te toegenomen vindbaarheid van informatie
* het opzetten van organisatie-overschrijdende toepassingen:
* bv. gezamenlijke fototheken, cartotheken, cartografische toepassingen, etc.

Grote, middelgrote en kleine **organisaties versterken elkaars werking en interne processen** door het publiceren en verrijken van WOI-gegevens.

* De verwachting is dat grote en middelgrote organisaties de grootste producenten van gegevens zullen zijn en middelgrote en kleine organisaties de grootste hergebruikers zullen zijn.
* Het voordeel voor de producenten van gegevens is dat hergebruikers vaak organisaties zijn met een beperkte focus. Hierdoor kunnen zij specifieke of niche gegevens bijdragen en gegevens producenten aanvullen of corrigeren.
* Het verzamelen en transformeren van gegevens kost door de mogelijkheid tot hergebruik en de toegenomen zichtbaarheid minder tijd en middelen.

**Doelgroep OSLO voor organisatie-overschrijdende kennisbank**

Het brede WOI-erfgoedveld in binnen- en buitenland:

* Erfgoedmedewerkers
  * Collectiebeheerders (bv. i.f.v. collectiemobiliteit)
  * Publieksmedewerkers (bv. terugvinden van informatie)
* Professionele en amateur onderzoekers
  * Informatie terugvinden, gegevens contextualiseren en nieuwe inzichten creëren door door nieuwe verbanden.
  * Het WOI-erfgoedveld beschikt over een grote gemeenschap van amateur onderzoekers die gelijkaardige vragen stellen als professionele onderzoekers.

Organisaties en onderzoekers buiten het WOI-erfgoedveld:

* Zij kunnen gegevens hergebruiken en koppelen (bv. Red Star Museum en hun databank rond emigratie naar Canada.)

**Doelgroep bezoekersapplicatie OSLO en geografische data:**
