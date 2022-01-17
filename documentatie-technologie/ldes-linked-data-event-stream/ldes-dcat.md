---
description: >-
  De verschillende datasets worden op een hoogste niveau beschrijven binnen de
  overkoepelende DCAT. Deze dataset catalogus bevat een verzameling van Open
  Datasets.
---

# LDES-DCAT

De verschillende datasets worden op een hoogste niveau beschrijven binnen de overkoepelende DCAT. Deze dataset catalogus bevat een verzameling van Open Datasets.

### &#x20;@context <a href="#docs-internal-guid-67b30351-7fff-ad25-d2d9-c41aed4f2f5c" id="docs-internal-guid-67b30351-7fff-ad25-d2d9-c41aed4f2f5c"></a>

documenteert de gebruikte context&#x20;

* type: array\
  \
  voorbeeld:

```
{@context: 
["https://apidg.gent.be/opendata/adlib2eventstream/v1/context/DCAT-AP-VL.jsonld",
{
 dcterms: "http://purl.org/dc/terms/",
 ldes: "https://w3id.org/ldes#",
 tree: "https://w3id.org/tree#",
 tree:view: {
  @type: "@id"
 }
}]}
```

### &#x20;@id + @type <a href="#docs-internal-guid-67b30351-7fff-ad25-d2d9-c41aed4f2f5c" id="docs-internal-guid-67b30351-7fff-ad25-d2d9-c41aed4f2f5c"></a>

```
@id: "https://stad.gent/id/dcat/coghent
@type: "Datasetcatalogus"
```

### Datasetcatalogus.titel

titel van de catalogus, hier wordt steeds het (@label) en de taal (@language) meegegeven. Een dataset kan in verschillende talen beschreven worden. De gewenste interpretatie van de cardinaliteit per taal is 1 waarde.&#x20;

* type: object
* gebasseerd op: [http://purl.org/dc/terms/title](http://purl.org/dc/terms/title)

```
Datasetcatalogus.titel: {
 @value: "Catalogus Coghent", 
 @language: "nl"
}
```

### Datasetcatalogus.heeftbeschrijving

korte beschrijving van waarover de datasetcatalogus handelt.

* type: object&#x20;
* gebasseerd op: [http://purl.org/dc/terms/description](http://purl.org/dc/terms/description)

```
Datasetcatalogus.beschrijving: {
 @value: "Catalogus van datasets voor de Collectie van de Gentenaar",          
 @language: "nl"
}

```
