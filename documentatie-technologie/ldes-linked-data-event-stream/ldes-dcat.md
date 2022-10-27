---
description: >-
  De verschillende datasets worden op een hoogste niveau beschrijven binnen de
  overkoepelende DCAT. Deze dataset catalogus bevat een verzameling van Open
  Datasets.
---

# LDES-DCAT

De verschillende datasets worden op een hoogste niveau beschrijven binnen de overkoepelende DCAT. Deze dataset catalogus bevat een verzameling van Open Datasets.&#x20;

{% hint style="info" %}
de LDES publicatie van de DCAT kan hier geraadplaagd worden; [https://apidg.gent.be/opendata/adlib2eventstream/v1/](https://apidg.gent.be/opendata/adlib2eventstream/v1/)
{% endhint %}

### &#x20;@context <a href="#docs-internal-guid-67b30351-7fff-ad25-d2d9-c41aed4f2f5c" id="docs-internal-guid-67b30351-7fff-ad25-d2d9-c41aed4f2f5c"></a>

documenteert de gebruikte context&#x20;

* type: array

```json
{@context: 
["https://apidg.gent.be/opendata/adlib2eventstream/v1/context/DCAT-AP-VL.jsonld",
{
 dcterms: "http://purl.onrg/dc/terms/",
 ldes: "https://w3id.org/ldes#",
 tree: "https://w3id.org/tree#",
 tree:view: {
  @type: "@id"
 }
}]}
```

### &#x20;@id + @type <a href="#docs-internal-guid-67b30351-7fff-ad25-d2d9-c41aed4f2f5c" id="docs-internal-guid-67b30351-7fff-ad25-d2d9-c41aed4f2f5c"></a>

Verwijzing naar de Catalogus van datasets voor de Collectie van de Gentenaar.&#x20;

```json
@id: "https://stad.gent/id/dcat/coghent",
@type: "Datasetcatalogus"
```

### Datasetcatalogus.titel

titel van de catalogus, hier wordt steeds het (@label) en de taal (@language) meegegeven. Een dataset kan in verschillende talen beschreven worden. De gewenste interpretatie van de cardinaliteit per taal is 1 waarde.&#x20;

* type: object
* gebasseerd op: [http://purl.org/dc/terms/title](http://purl.org/dc/terms/title)

```json
Datasetcatalogus.titel: {
 @value: "Catalogus Coghent", 
 @language: "nl"
}
```

### Datasetcatalogus.heeftbeschrijving

korte beschrijving van waarover de datasetcatalogus handelt.

* type: object&#x20;
* gebasseerd op: [http://purl.org/dc/terms/description](http://purl.org/dc/terms/description)

```json
Datasetcatalogus.beschrijving: {
 @value: "Catalogus van datasets voor de Collectie van de Gentenaar",          
 @language: "nl"
}

```

### Datasetcatalogus.heeftLicentie  <a href="#docs-internal-guid-3008e947-7fff-0d38-6eb4-d964064fae99" id="docs-internal-guid-3008e947-7fff-0d38-6eb4-d964064fae99"></a>

documenteert de toegekende licentie aan de dataset catalogus in kwestie. Binnen het project wordt hier steeds de licentie public domain aan toegekend en volgt hierbij de vastgelegde licentie voor het Vlaams Open Data Portaal.

* type: object&#x20;
* gebasseerd op: [http://purl.org/dc/terms/license](http://purl.org/dc/terms/license)

```json
Datasetcatalogus.heeftLicentie: {
 @id: "https://creativecommons.org/publicdomain/zero/1.0/"
}
```

### Datasetcatalogus.heeftUitgever

binnen het project is de uitgever van de dataset catalogus Stad Gent. Voor het beschrijven van de agent wordt [Agent.naam](http://xmlns.com/foaf/0.1/name) gehanteerd. Een agent kan in meerdere talen beschreven worden. De gewenste interpretatie van de kardinaliteit is: per taal 1 waarde.&#x20;

* Type: object
* Gebaseerd op: [http://purl.org/dc/terms/publisher](http://purl.org/dc/terms/publisher)

```json
Datasetcatalogus.heeftUitgever: {
 @id: "https://stad.gent/", 
 Agent.naam: {
  @value: "Stad Gent", 
  @language: "nl"
 }
}
```

### Datasetcatalogus.heeftDataset&#x20;

container met hierin de beschrijvende metadata en distributie van de datasets beschreven in de data set catalogus. Voor de leesbaarheid van dit document te bewaken wordt de structuur van een dataset hieronder in een apart deel verder besproken.

* Type: array
* Gebaseerd op: [http://www.w3.org/ns/dcat#dataset](http://www.w3.org/ns/dcat#dataset)

```json
Dataset.catalogus.heeftDataset: [
    ...
]
```

voor de structuur per dataset kan men terecht op de volgende [pagina](ldes-dataset.md).&#x20;
