# LDES-objecten (musea)

Binnen het project _de collectie van de gentenaar_ wordt gebruik gemaakt van de invulinstructies zoals beschreven in het [CEST-invulboek](https://www.projectcest.be/wiki/Invulboek\_objecten). Het naleven en toepassen van deze instructies vormen een cruciale schakel voor het correct transformeren van de data uit adlib naar de OSLO standaard.&#x20;

De OSLO-standaarden worden aangevuld met de Linked Art-standaard.&#x20;

### @context&#x20;

Voor het beschrijven van erfgoeddata met betrekking tot objecten in de musea wordt gebruik gemaakt van van de volgende OSLO applicatie profielen:&#x20;

* Cultureel erfgoed object: [https://test.data.vlaanderen.be/doc/applicatieprofiel/cultureel-erfgoed-object/ontwerpstandaard/2020-05-28#Collectie](https://test.data.vlaanderen.be/doc/applicatieprofiel/cultureel-erfgoed-object/ontwerpstandaard/2020-05-28#Collectie)
* Cultureel erfgoed event: [https://data.vlaanderen.be/doc/applicatieprofiel/cultureel-erfgoed-event](https://data.vlaanderen.be/doc/applicatieprofiel/cultureel-erfgoed-event)
* persoon basis: [https://data.vlaanderen.be/ns/persoon](https://data.vlaanderen.be/ns/persoon)
* Generiek basis: [https://data.vlaanderen.be/doc/applicatieprofiel/generiek-basis/](https://data.vlaanderen.be/doc/applicatieprofiel/generiek-basis/)
* Dossier: [https://data.vlaanderen.be/doc/applicatieprofiel/dossier/](https://data.vlaanderen.be/doc/applicatieprofiel/dossier/)

```
{
    @context: [
        "https://apidg.gent.be/opendata/adlib2eventstream/v1/context/cultureel-erfgoed-object-ap.jsonld",
        "https://apidg.gent.be/opendata/adlib2eventstream/v1/context/persoon-basis.jsonld",
        "https://apidg.gent.be/opendata/adlib2eventstream/v1/context/cultureel-erfgoed-event-ap.jsonld",
        "https://apidg.gent.be/opendata/adlib2eventstream/v1/context/organisatie-basis.jsonld",
        "https://apidg.gent.be/opendata/adlib2eventstream/v1/context/generiek-basis.jsonld",
        "https://apidg.gent.be/opendata/adlib2eventstream/v1/context/dossier.jsonld",
    {
    dcterms:isVersionOf: {
        @type: "@id"
    },
    prov: "http://www.w3.org/ns/prov#",
    skos: "http://www.w3.org/2004/02/skos/core#",
    label: "http://www.w3.org/2000/01/rdf-schema#label",
    opmerking: "http://www.w3.org/2004/02/skos/core#note",
    foaf: "http://xmlns.com/foaf/0.1/",
    foaf:page: {
        @type: "@id"
    },
    cest: "https://www.projectcest.be/wiki/Publicatie:Invulboek_objecten/Veld/",
    inhoud: "http://www.cidoc-crm.org/cidoc-crm/P190_has_symbolic_content",
    la: "https://linked.art/ns/terms/",
    conforms_to: {
        @id: "dcterms:conformsTo",
        @type: "@id",
        @container: "@set"
    },
    equivalent: {
        @id: "la:equivalent",
        @type: "@id"
    },
    dig: "http://www.ics.forth.gr/isl/CRMdig/",
    DigitalObject: {
        @id: "dig:D1_Digital_Object"
    }
}
]
```

\
