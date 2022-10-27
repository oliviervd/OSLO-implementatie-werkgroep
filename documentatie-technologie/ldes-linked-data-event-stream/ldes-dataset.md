# LDES-Dataset

De dataset catalogus omvat verschillende datasets. In totaal worden er binnen het project 8 aparte datasets gepubliceerd. Hierin onderscheiden we 4 specifieke datasets:&#x20;

* Dataset met beschrijvingen over personen en instellingen (agents)
* Dataset met beschrijvingen van de thesaurus (gebruikte concepten)
* Dataset met objecten uit elke collectie (5x)
* Dataset met informatie over de tentoonstellingen.&#x20;

De structuur van deze vier unieke cases wordt hieronder verder toegelicht. Dit aangezien elke specifieke case een unieke mapping vereist.

![](<../../.gitbook/assets/Naamloos (3).png>)

### Dataset.titel

Titel van de dataset in kwestie, hier wordt steeds het label (@label) en de taal (@language) meegegeven. Een dataset kan titels in meerdere talen kennen. De gewenste interpretatie van de cardinaliteit is: per taal 1 waarde.

* Type: object&#x20;
* Gebaseerd op: [http://purl.org/dc/terms/title](http://purl.org/dc/terms/title)

```json
Dataset.titel: {
 @value: "thesaurus van Archief Gent, Design Museum Gent, Het Huis van Alijn (Gent), Industriemuseum, STAM (Gent)",
 @language: "nl"
}
```

### Dataset.beschrijving&#x20;

Korte beschrijving waarover de dataset handelt. hier wordt steeds het label (@label) en de taal (@language) meegegeven. Een dataset kan in verschillende talen beschreven worden. De gewenste interpretatie van de cardinaliteit is: per taal 1 waarde.

* Type: object&#x20;
* Gebaseerd op: [http://purl.org/dc/terms/description](http://purl.org/dc/terms/description)

```json
Dataset.beschrijving: {
 @value: "Event stream van de Adlib database 'thesaurus' van de   instelling: Archief Gent, Design Museum Gent, Het Huis van Alijn (Gent), Industriemuseum, STAM (Gent)",
 @language: "nl"
}
```

### Dataset.contactinfo

Voor elke gepubliceerde dataset voorziet het project contactinfo die verwijst naar de eigenaar van de dataset zodat de afnemer indien gewenst contact op kan opnemen met de verantwoordelijken van de dataset.

* Type: object
* Gebaseerd op: [http://www.w3.org/ns/dcat#contactPoint](http://www.w3.org/ns/dcat#contactPoint)

```json
Dataset.contactinfo: {
 @type: "contactinfo",
 Contactinfo.eMail: "data@designmuseumgent.be"
}
```

### Dataset.toegankelijkheid&#x20;

De toegankelijkheid categorie van de dataset. Voor Open Data is de waarde hiervan steeds PUBLIC. Hierin volgt het de afspraken zoals gemaakt bij Vlaanderen.&#x20;

* Type: string
* Gebaseerd op: [https://dublincore.org/specifications/dublin-core/dcmi-terms/#accessRights](https://dublincore.org/specifications/dublin-core/dcmi-terms/#accessRights)

```json
Dataset.toegankelijkheid: "http://publications.europa.eu/resource/authority/access-right/PUBLIC"
```

### Dataset.heeftUitgever&#x20;

Verwijzing naar de uitgever van de dataset. In sommige gevallen kunnen dit meerdere uitgevers zijn. Zoals het geval bij de geagrageerde datasets “personen en instellingen” en “thesaurus”. Voor het beschrijven van de uitgever wordt [Agent.naam](http://xmlns.com/foaf/0.1/name) gehanteerd. Elke uitgever kan in meerdere talen beschreven worden. hier wordt steeds het label (@label) en de taal (@language) meegegeven. De gewenste interpretatie van de cardinaliteit is: per taal 1 waarde.

* Type: object of array (indien meerdere uitgevers)&#x20;
* Gebaseerd op:&#x20;

```json
Dataset.heeftUitgever: [
 {
  @id: "http://www.wikidata.org/entity/Q41776192", 
  Agent.naam: {
   @value: "Archief Gent",
   @language: "nl"
  }
 }, 
  @id: "http://www.wikidata.org/entity/Q1809071" 
  Agent.naam: {
   @value: "Design Museum Gent",
   @language: "nl"
  }
]
```

### heeftDistributie

De distributie van een dataset. Hierin worden de linken opgenomen die verwijzen naar de gepubliceerde dataset. Daarnaast wordt hierin nogmaals de licentie van de gedistribueerde dataset opgenomen. Binnen het project geldt hier steeds dezelfde Creative Commons-licentie, CC0, dit conform aan de afspraken bij Vlaanderen.&#x20;

* Type: object
* Gebaseerd op: [http://www.w3.org/ns/dcat#distribution](http://www.w3.org/ns/dcat#distribution)

```json
heeftDistributie: {
 @type: "Distributie",
 toegangsURL: "https://apidg.gent.be/opendata/adlib2eventstream/v1/adlib/thesaurus", 
 dcterms:conformsTo: "https://w3id.org/tree", 
 Distributie.heeftLicentie: {
  @id: "https://creativecommons.org/publicdomain/zero/1.0/"
 }
}


```







