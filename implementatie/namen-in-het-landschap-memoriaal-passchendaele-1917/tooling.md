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

Personele middelen:

* Opleidingen OSLO, Analyse systeem (opbouw), onderzoek bestaande componenten = +-180 - 200 uur
* Basisaanpassingen Archives opbouw (bv; structuur plaatsen, eenheden -> ombouwen tot algemene boomstructuur) = +- 30 - 50 uur
* Implementatie OSLO - Afhankelijk van uiteindelijk gekozen oplossing (bestaande oplossing / volledig eigen ontwikkeling) = +- 100 - 150 uur

## Link naar use-case
