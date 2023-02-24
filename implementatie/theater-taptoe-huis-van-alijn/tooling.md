# Transformatieplan

## Technische infrastructuur

De databronnen van het Huis van Alijn zijn de volgende:&#x20;

* Axiell/adlib (metadata collectiestukken)
* Meemoo mam (afbeeldingen)
* Wikidata (producties en voorstellingen, momenteel enkel op databank kunstenpunt)

(voor de thesaurus, en de vermelding van agents trachten we zoveel mogelijk te verwijzen naar erkende bronautoriteiten):&#x20;

* AAT (concepten)
* Geonames/TGN (plaatsen)
* inventaris onroerend erfgoed (associaties locaties)
* wikidata, ULAN, RKD (agents)
* FOMU register van fotografen

Transformatielaag:

* 2 endpoints
* LDES > integratie van data uit verschillende bronnen
* levert ‘alles’ , volledig , complex maar juist\
  (vraag is OSLO data te produceren, LDES maakt dit mogelijk)
* integratie Adlib
* REST API > aanleveren data op maat van de use case
* levert eenvoudige, direct bruikbare (platte) data die je meteen kan omzetten naar een visuele representatie
* gecureerde sets definieren
* data plat slaan
* kan in welke format dan ook

Interfaces:

* (data.collectie.gent)
* netwerkbrowser
* google voor poppentheater (zoek alle ‘commendatore’ poppen in belgie
* verrijking met thesauri (AAT, TGN, geonames etc)
* verrijking met meemoo mam
* verrijking met wikidata.org

## Inschatting benodigde middelen

Enerzijds is er een **personeelskost** geassocieerd met dataverrijking, datacleaning en registratie. Momenteel gebeurt de registratie en dataverrijking van de dataset poppenspel binnen het kader van een tijdelijk project inhaalbeweging digitale collectie waarvoor Huis van Alijn voor de duur van het project één voltijdse werkkracht in dienst heeft. In het kader van het project Collectie van de Gentenaar is er eveneens een voltijdse werkkracht aangesteld voor datacleaning.&#x20;

Naast datacleaning zou deze persoon ook verantwoordelijk zijn voor het publiceren van data over voorstellingen op Wikidata, het uitbreiden van de bestaande Linked Data Event Stream (Collectie van de Gentenaar) en het in de lucht houden van ervan.

Idealiter heb je dus een voltijdse vaste werkkracht die dit soort taken voor de gehele collectie op zich neemt.

Daarnaast zijn er middelen nodig voor **infrastructuur**:

* REST API opzetten: geeft de data zoals die op dat moment is door. (biedt minder mogelijkheden voor Linked data, maar is makkelijker hanteerbaar voor developers)&#x20;
* Browser/applicatie bouwen op endpoints zodat eindgebruikers makkelijk, overzichtelijk en gebruiksvriendelijk toegang krijgen tot data.

## Link naar use-case

Huis van Alijn wilt op twee manieren toegang geven tot de Taptoe data:

* We willen ontwikkelaars de mogelijkheid bieden om aan de slag te gaan met onze data en hierop zelf applicaties te bouwen.
* Daarnaast maken we, om onderzoekers, jonge makers of potentiële bruikleennemers te bedienen, een netwerkbrowser waar gelinkte kennis over poppenspel doorzocht en gevisualiseerd kan worden.
