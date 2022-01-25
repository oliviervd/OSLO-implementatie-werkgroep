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

### @id&#x20;

### @type

### Dcterms:isVersionOf

### prov:generatedAtTime

### foaf:page

### Object.identificator&#x20;

![](<../../.gitbook/assets/id (3).png>)

Uit de OSLO-standaard Cultureel Erfgoed Object. Beschrijving van de verschillende identificatiecodes die toegekend zijn aan specifiek object of een onderdeel van dat object, zoals objectnummer (zoals toegekend in het collectieregistratiesysteem adlib) en priref (het database-nummer van het object in adlib). Het onderscheid tussen objectnummer en priref wordt gemaakt door het toevoegen van een label onder Entiteit.type.&#x20;

Het type van de string slaat op het identificatiesysteem, de string zelf op de eigenlijke identificator.&#x20;

* type: array&#x20;
* Gebaseerd op:&#x20;

<mark style="background-color:orange;">Opmerking CEST (meemoo): is het hier nodig om de bron van het nummer toe te kennen. Dit nummer verwijst naar wie het nummer heeft toegekend.</mark>&#x20;

```
Object.identificator [
 {
  @type: "Identificator", 
  Identificator.identificator: {
   @value: "530027903",
   @type: "https://stad.gent/id/identificatiesysteem/priref"
  }
 }, 
  @type: "Identificator",
  Identificator.identificator: {
   @value: "2021-0002",
   @type: "https://stad.gent/id/identificatiesysteem/objectnummer"
},
  Entiteit.type: {
    @id: "cest:Waarde_objectnummer",
    label: "objectnummer"
  }
```

### MaterieelDing.beheerder

Uit de OSLO-standaard Cultureel Erfgoed Object. Wordt toegekend aan het Adlib/Axiell Collections-veld ‘instelling.naam’. Het concept verwijst naar de beheerder van het mensgemaakt object. Voor het verwijzen naar de beheerder wordt gebruik gemaakt van het Wikidata record.&#x20;

* Type: string
* Gebaseerd op:

```
MaterieelDing.beheerder: "http://wikidata.org/entity/Q1809071"
```

### MensgemaaktObject.maaktDeelUitVan <a href="#docs-internal-guid-376fc7ba-7fff-be09-2033-49f727d01855" id="docs-internal-guid-376fc7ba-7fff-be09-2033-49f727d01855"></a>

Uit de OSLO-standaard Cultureel Erfgoed Object. Wordt toegekend aan het Adlib/Axiell Collections-veld ‘collectie’. Objecten worden door de beherende instellingen geaggregeerd in verschillende deelcollecties.&#x20;

Elk van deze deelcollecties krijgt het type: “Collectie” en wordt beschreven door middel van het veld entiteit.beschrijving. Indien de collectiebeschrijving verwijst naar een door een externe bron gepubliceerd concept wordt dit verder gedocumenteerd via entiteit.type.

Hierin verwijst @id naar de URI van het beschreven concept, gepaard met het label en de taal waarin dit label beschreven staat. Een tweede @id wordt toegekend om te verwijzen naar de invulinstructies in CEST met betrekking tot het veld waarin deze informatie in de bron beschreven staat.&#x20;

![](<../../.gitbook/assets/id (2).png>)

```
MensgemaaktObject.maaktDeelUitVan: [
 {
  @id: "https://stad.gent/id/concept/530009136", 
  @type: "Collectie", 
  Entiteit.beschrijving: "huishoudelijke apparaten", 
  Entiteit.type: [
    {
    @id: "https://vocab.getty.edu/aat/300257284", 
    Label: {
     @value: "huishoudelijke apparaten", 
     @language: "nl"
    }
   }, 
   {
    @id: "cest:Naam_Collectie", 
    label: "collectie"
   }
  ]
 }, 
  @id: "https://stad.gent/id/concept/530009137", 
  @type: "Collectie", 
  Entiteit.beschrijving: "Novan", 
  Entiteit.type: [ 
   {
    @id: "cest:Naam_Collectie", 
    label: "collectie"
   }
  ]
 }
]


```

### Entiteit.classificatie

Object kan onder verschillende classificaties getypeerd worden, waaronder ‘objectcategorie’ en ‘objectnaam’. Onderscheid wordt gemaakt door het toekennen van Entiteit.type waarin verwezen wordt naar CEST.

Classificatie.getypeerdeEntiteit verwijst naar de URI van het object. Classificatie.toegekendType verwijst naar het type van classificatie a.d.h.v. een externe autoriteit (bijv. Getty Vocabularies).

```
Entiteit.classificatie:[{
 @type: "Classificatie",
 Classificatie.getypeerdeEntiteit:  "https://stad.gent/id/mensgemaaktobject/dmg/530027903",
 Classificatie.toegekendType:{
  @id: "http://vocab.getty.edu/aat/300208278",
  skos:prefLabel:{
   @value: "mixer",
   @language: "nl"
  }
 },
 Entiteit.type:{
  @id: "cest:Term_objectnaam",
  label: "objectnaam"
 }
},
{
 @type: "Classificatie",
 Classificatie.getypeerdeEntiteit: "https://stad.gent/id/mensgemaaktobject/dmg/530027903",
 Classificatie.toegekendType:{
  @id: "http://vocab.getty.edu/aat/300055100",
  skos:prefLabel:{
   @value: "productverpakking",
   @language: "nl"
  }
 },
 Entiteit.type:{
  @id: "cest:Term_objectnaam",
  label: "objectnaam"
 }
}
]
```

### MensgemaaktObject.titel <a href="#docs-internal-guid-d8672be9-7fff-763e-9e8d-d388387dbc23" id="docs-internal-guid-d8672be9-7fff-763e-9e8d-d388387dbc23"></a>

Uit de OSLO-standaard Cultureel Erfgoed Object. Wordt toegekend aan het Adlib/Axiell Collections-veld ‘titel’. Het concept verwijst naar de titel van het object, zoals toegekend door de beheerder.

### Entiteit.beschrijving <a href="#docs-internal-guid-849a4a27-7fff-cbc6-6852-b173af81f3fb" id="docs-internal-guid-849a4a27-7fff-cbc6-6852-b173af81f3fb"></a>

OSLO-standaard Cultureel Erfgoed Event. Wordt toegekend aan het Adlib/Axiell Collections-veld ‘beschrijving’. Het concept verwijst naar de beschrijving van het object, zoals toegekend door de beheerder.

* Type: object

```
Entiteit.beschrijving: {
 @value: "Deze staafmixer ontving in 1959 het Gouden Kenteken van het Belgische Design Centre,  wat betekent dat hij werd erkend als een geslaagd voorbeeld van industrieel design. Het toestel was dan ook het resultaat van een samenwerking van een bekende Belgische producent van huishoudtoestellen met het befaamde ontwerpbureau van Raymond Loewy. Novamix was de eerste handmixer van Nova. Het onderscheid tussen de licht verschillende varianten van dit ontwerp in de collectie moet verder worden onderzocht. We verwierven dit exemplaar voor zijn bijzondere productverpakking. Dat er meerdere verpakkingen voor dit product bestaan, kan erop wijzen dat de mixer lang in productie was en dus goed verkocht. De steekkaart waarmee de jury van het Design Centre objecten selecteerde voor zijn tentoonstellingen, vermeldt dat de prijs 750 Belgische frank bedroeg, en dat de mixer het kwaliteitsmerk 'Cebec' kreeg. Dit exemplaar was vermoedelijk in gebruik door de broeders van het Scheppersinstituut in Wetteren.", 
 @language: "nl"
}
```

### Entiteit.wordtNaarVerwezenDoor <a href="#docs-internal-guid-4d5a0bab-7fff-aeb4-31dc-f00846e03758" id="docs-internal-guid-4d5a0bab-7fff-aeb4-31dc-f00846e03758"></a>

Verwijst naar de vervaardiger, de rol van de vervaardiger en de datum van vervaardiging. Het project maak hierin een onderscheid aan de hand van de toegekende rol van de vervaardiger.

\
Enkel indien de rol “ontwerper” in het collectieregistratiesysteem aan een vervaardiger werd toegekend wordt het OSLO object Entiteit.wordtNaarVerwezenDoor gebruikt om te verwijzen naar de vervaardiging van een ConceptueelDing. Van het ConceptueelDing wordt datum vervaardiging gespecificeerd door ConceptueelDing.heeftCreatie en Gebeurtenis.tijd. De vervaardiger van een ConceptueelDing wordt aangeduid met Activiteit.uitgevoerdDoor, waaraan Entiteit.type wordt toegevoegd voor het bepalen van het CEST-veld. De rol van de vervaardiger wordt aangeduid door Rol.activiteit (uit OSLO-standaard Cultureel Erfgoed Event) en het toevoegen van Entiteit.type (uit OSLO-standaard Cultureel Erfgoed Event) voor het bepalen van het CEST-veld.  &#x20;

Indien de rol van de vervaardiger ‘producent’ of ’uitvoerder’ is, zie MaterieelDing.productie.   &#x20;

Het object (hier Entiteit) is de materialisering van een ‘conceptueel ding’, hieronder verstaan we het ontwerp. Voorbeeld hiervan is de .03 stoel van Maarten van Severen, deze stoel werd maar 1 maal ontworpen maar heeft verscheidene uitvoeringen (resulterende uit productie) waarvan fysieke objecten in de collectie van het Design Museum Gent.&#x20;

Binnen het project _de Collectie van de Gentenaar_ wordt gefilterd op drie rollen:&#x20;

* ontwerp
* uitvoering&#x20;
* Productie

```
Entiteit.wordtNaarVerwezenDoor:{
 @type: "ConceptueelDing",
 ConceptueelDing.heeftCreatie:{
  @type: "Creatie",
  Gebeurtenis.tijd:{
   @value: "..",
   @type: "http://id.loc.gov/datatypes/edtf/EDTF"
  },
  Activiteit.uitgevoerdDoor: {
   @type: "Agent",
   equivalent:{
    @id: "https://stad.gent/id/agent/530000512",
    @type: "Agent",
    Label:{
     @value: "Hankar, Paul", 
     @language: "nl"
    }
   },
   Entiteit.type:{
    @id: "cest:Naam_vervaardiger",
    label: "vervaardiger"
   }
  },
  Gebeurtenis.plaats: {
   @type: “Plaats”, 
   equivalent: { 
    @id: “http://vocab.getty.edu/tgn/7007868”
    skos:prefLabel: {
    }
   }
  }
  @reverse:{
   Rol.activiteit:{
    @type: "Rol",
    Rol.agent: "https://stad.gent/id/agent/530024154",
    Rol.rol:{
     @id: "http://vocab.getty.edu/aat/300025190",
     skos:prefLabel:{
      @value: "ontwerper",
      @language: "nl"
      }
    },
    Entiteit.type:{
     @id: "cest: Rol_vervaardiger",
     label: "vervaardiger.rol"
    }
   }
  }
 }
}
```
