---
description: samenvatting van gebruikte tools voor het implementeren van OSLO
---

# tooling

## Termennetwerken

Zoals beschreven in de strategie ([link met andere databronnen](strategie-tot-implementatie.md#3.-link-met-andere-databronnen)) is het belangrijk om bij het registreren voldoende rekening te houden voor het toekennen van URIs die verwijzen naar andere termennetwerken. Zo verrijk je niet enkel de fiches inhoudelijk, maar verzeker je ook dat de gepubliceerde data aansluiting en verbinding vindt met andere datasets.&#x20;

### gebruikte termennetwerken: nationaal/regionaal

#### [Inventaris onroerend erfgoed ](https://inventaris.onroerenderfgoed.be)

_Deze inventaris geeft je een overzicht van het waardevolle erfgoed in Vlaanderen. Zowel archeologisch, bouwkundig, landschappelijk als varend erfgoed zijn opgenomen, goed voor meer dan 90.000 erfgoedobjecten in totaal. Ben je op zoek naar specifiek erfgoed? Dan kan je onze inventaris heel gericht doorzoeken._

{% tabs %}
{% tab title="json-ld (LDES)" %}
```
InformatieObject.gaatOver: [
    {
        @type: "Entiteit",
        Entiteit.type: [
    {
    @id: "https://inventaris.onroerenderfgoed.be/themas/2909",
    skos:prefLabel: {
        @value: "Kleine Vismarkt",
        @language: "nl"
        }
    },
    {
        @id: "cest:Naam_geassocieerd_concept",
        label: "associatie.onderwerp"
    }
]
```
{% endtab %}
{% endtabs %}

#### databank kunstenpunt&#x20;

#### fashion thesaurus (MoMU)

### gebruikte termennetwerken: internationaaal

#### AAT (Getty Vocabularies)

#### ULAN (Getty Vocabularies)

#### TGN (Getty Vocabularies)



&#x20;
