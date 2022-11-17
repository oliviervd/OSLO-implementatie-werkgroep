---
description: Bert Lemmens, Olivier Van D'huynslager, Sofie Teugels
---

# 20220622-werkgroep1-notes



Deelnemers:

* Bert Lemmens, meemoo
* Olivier d'Huynslaegher, Coghent
* Sofie Teugels, Coghent

Agenda

* vgl Invulboek Basisregistratie in OSLO JSON-LD vs Coghent LDES

Verslag

*

Actiepunten

*





### Naamgeving

Entiteiten: Upper Camel Case bvb. MensgemaaktObject

Eigenschappen: Lower Camel Case bvb. maaktDeelUitVan

### Dot notation voor terms?

Waarom wordt voor de naamgeving van eigenschappen in de OSLO context gebruikt gemaakt van dot notation?

```
{
"MaterieelDing.beheerder": {
      "@container": "@set",
      "@id": "http://www.cidoc-crm.org/cidoc-crm/P50_has_current_keeper",
      "@type": "@id"}
}      
```

Wat is de preciese relatie van het 'subject' bij de eigenschap?

Waarom niet het vocabularium uit de OSLO voor erfgoed namespace overnemen?

### Keywords

Wat is in de CoGhent implementatie de aanpak mbt de keywords @id ,  @type,  @language en @container?&#x20;

#### Value Types

Value Types worden systematisch gedefinieerd in de context.

```
{"@context":{
    "skos:prefLabel":{
        "@id":"http://www.w3.org/2004/02/skos/core#prefLabel"
        "@type":""
        }
    }
}
```

```
niet {
"@type":"MensgemaaktObject",
"toegekend door:{
    "@type":"Agent", 
    "skos:prefLabel":{
        "@value":"Olivier", 
        "@language":"nl"
        }
    }
}
```



#### Identificators

* "identificator" leidt steeds naar twee keywords:
  * @type met het value type, nl een IRI die verwijst naar het corresponderende veld in het Invulboek. Bvb. "cest:objectnummer
  * @value met de Literal die het identificatienummer weergeeft.

```
{
"@type":"MensgemaaktObject",
"identificator":{
    "@type":"Identificator",
    "identifcator"
    "@type":"cest:databanknummer", 
    "@value":"93003-C"
    }
}
{
optie 2
"@type":"MensgemaaktObject",
    "identificator":{{
        "@type":"Identificator",
        "entiteit.type":{
            "@id":"cest:databanknummer",
            "label":"databanknummer"
            }
        "identificator":{
            "@type":"Taalstring"'
            "@value":"93003-C"
            }

optie 3


}

```

wel "entiteit.identificator":{"@type":"Identificator", "@value":"93003-C"}

### Agents/Concepten/Plaatsen/Gebeurtenissen linken:

1. als je een externe bron als beheersysteem gebruikt, meteen de URI:

```
{
"beheerder":"http://wikidata.org/entity/Q84930"
}
```

2\. als je je eigen Agent wil linken aan een agent uit een externe bron, gebruik de "equivalent" eigenschap:

```
{
"beheerder":{
    "@type":"Agent",
    "equivalent":{
        @id: "http://wikidata.org/entity/Q84930", 
        skos:prefLabel: {
            @value: Museum voor Schone Kunsten,
            @language: "nl"
            }
        }
    }
}
```

### Toekenningen

Er zijn drie soorten activiteiten waarbij een eigenschap wordt toegekend. Hieronder volgen de Invulboek elementen die aan elk soort toekenning gekoppeld zijn.

#### Classificaties

Volgende (spectrum gerealteerde) trefwoorden worden gedocumenteerd via classificatie events, om de herkomst van trefwoorden te kunnen traceren:

* objectnaam&#x20;
* objectclassificatie
* hoofdmotief
* afgebeeld concept/agent/locatie/gebeurtenis

#### Meting

* afmetingen

#### ConditiebeoordelingConditiebeoordeling

* conditie

Toekenning zelf?

Gebruiken voor elke andere eigenschap die toegekend wordt?\
Wat met het toekennen van Identificators? Shorthand "isToegkendDoor" gebruiken? Of toch via een Activiteit?

