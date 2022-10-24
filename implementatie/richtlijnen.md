---
description: Algemene implementatie richtlijnen voor OSLO voor Erfgoed
---

# Richtlijnen

## Principes Naamgeving

1\. **Entiteiten** worden zowel in de Specificatie als de Context in **Upper Camel Case** geschreven.\
_bvb. "MensgemaaktObject", niet: "Mensgemaakt Object", "Mensgemaakt object"_

2\. **Eigenschappen** worden zowel in de Specificatie als in de Context in **Lower Camel Case** geschreven:\
_bvb "heeftTitel", niet "heeft titel", "heeft-titel"_

3\. Namen in de **Specificatie** zijn **identiek** aan namen in de **Context**.\
_bvb. "heeftTitel" in de specificatie, wordt in de @context gedefinieerd als:_&#x20;

```json
"heeftTitel": {
      "@id": "http://www.cidoc-crm.org/cidoc-crm/P102_has_title",
      "@type": "http://www.w3.org/1999/02/22-rdf-syntax-ns#langString",
      "@container": "@set"
      }
```

_niet:_

```json
"MensgemaaktObject.Titel": {
      "@id": "http://www.cidoc-crm.org/cidoc-crm/P102_has_title",
      "@type": "http://www.w3.org/1999/02/22-rdf-syntax-ns#langString",
      "@container": "@set"
      }
```

4\. Namen van eigenschappen vormen een **actieve of passieve zinsconstructie**.\
_bvb "heeftTitel", "isTitelVan", niet "titel"_&#x20;

_5._ Namen van eigenschappen zijn een zo **nauwkeurig mogelijke vertaling** van de broneigenschap uit CIDOC-CRM, LRM of RIC.\
_bvb CIDOC CRM: "P1 is identified by (identifies)" wordt OSLO: :wordtGeïdentificeerdDoor_ \
_(Let op: @context mapt op in dit geval naar ""http://www.w3.org/ns/adms#identifier"._

## Basispatronen

### 1. Types

* Gebruik **@type** om de Entiteit te identificeren waarop het JSON-object betrekking heeft.

```json
{
"@id":"https://stad.gent/id/mensgemaaktobject/dmg/530008250/2022-06-22T00:00:50.901Z",
"@type":"MensgemaaktObject"
}
```

* Gebruik "**heeftType**" / CIDOC-CRM P2: has type / is type als OSLO geen nauwkeurig matchende Entiteit beschikbaar heeft en je de Entiteit **zelf** nader wil **karakteriseren**.

```json
{
"@id":"https://data.passchendaele.be/begraving/id/530008250",
"@type":"Activiteit",
"heeftType":{
    "@type:"Type",
    "@value":"begraving"
    }
}
```

* Gebruik "**heeftType**" / CIDOC-CRM P2: has type / is type ook om een Entiteit te mappen met een 'veld' uit het **Invulboek** dat beschrijvingsregels bevat voor de inhoud van het JSON-object.​

```
{
"@id":"https://data.passchendaele.be/begraving/id/530008250",
"@type":"Activiteit",
"heeftType":[{
    "@type:"Type",
    "@value":"begraving"
    },
    {
    "@type":"Type",
    "@id":"cest:Term_geassocieerde_gebeurtenis"
    }]
}
```

* Gebruik "**isGeclassificeerdDoor**" en een "**Classificatie**" om de "objectnaam" (i.e. het type erfgoedobject) of anderen trefwoorden voor de Entiteit te documenteren.

```json
{
"@id":"https://data.cagnet.be/item/530008250",
"@type":"MensgemaaktObject",
"isGeclassificeerdDoor":{
    "@type":"Classificatie",
    "heeftType":{
        "@type":"Type",
        "@id":"cest:Term_objectnaam"},
    "wijstToe":{
        "@type":"Type",
        "voorkeursterm":{
            "@value":"filmkopie",
            "@language":"nl"}
        }
    }
}
```

### 2. Namen

*   Gebruik **@value** om Entiteiten van een mensleesbaar label te voorzien.

    ```json
    {
    "@type":"ZelfstandigeExpressie",
    "@id":"https://data.cagnet.be/item/F95043",
    "@value":"Frischer Wind In Streudorf"
    }
    ```
*   &#x20;Wanneer je een Entiteit van meerdere namen wil voorzien, of informatie over de toekenning van de naam wil documenteren, gebruik de eigenschap "**heeftNaam**" en "**Naam**" (cf. CRM E35 Title) om vervolgens eigenschappen van de naam te documenteren.

    ```json
    {
    "@type":"ZelfstandigeExpressie",
    "@id":"https://data.cagnet.be/item/F95043",
    "@value":"Frischer Wind In Streudorf",
    "heeftNaam":[{
        	"@type":"Naam",
        	"@value":"Frischer Wind In Streudorf",
     	},
     	{
    	"@type":"Naam",
        	"@value":"Een Frisse Wind In Strodorp"
     	}]
     }
    ```
*   Gebruik **@language** om de taal van namen te documenteren.&#x20;

    ```json
    {
    "@type":"ZelfstandigeExpressie",
    "@id":"https://data.cagnet.be/item/F95043",
    "@value":"Frischer Wind In Streudorf",
    "heeftNaam":[{
        	"@type":"Naam",
        	"@value":"Frischer Wind In Streudorf",
      	"@language":"de"
     	},
     	{
    	"@type":"Naam",
        	"@value":"Een Frisse Wind In Strodorp",
      	"@language":"nl", 
     	}]
     }
    ```
*   Gebruik de eigenschap "**heeftType**" om het soort naam te karakteriseren.&#x20;

    ```json
    {
    "@type":"ZelfstandigeExpressie",
    "@id":"https://data.cagnet.be/item/F95043",
    "heeftNaam":[{
        	"@type":"Naam",
        	"@value":"Frischer Wind In Streudorf",
      	"@language":"de",
    	"heeftType":{
      		"@type":"Type",
      		"heeftVoorkeursterm":{
    			"@type":"TaalString",
    	    		"@value":"originele titel",
        			"@language":"nl"
        			}
      		} 
     	}
     }
    ```
* Gebruik de eigenschap "**isToegekendDoor**" en "**Toekenning**" om uit te drukken wie en wanneer een naam werd toegekend.&#x20;

```json
{
"@type":"ZelfstandigeExpressie",
"@id":"https://data.cagnet.be/item/F95043",
"heeftNaam":{
    	"@type":"Naam",
    	"@value":"Frischer Wind In Streudorf",
  	"@language":"de",
	"heeftType":{
  		"@type":"Type",
  		"heeftVoorkeursterm":{
			"@type":"TaalString",
	    		"@value":"originele titel",
    			"@language":"nl"
    			}
  		},
        "isToegekendDoor":{
            "@type":"Toekenning",
            (todo)
 	}
 }
```

### 3. Identificatienummers

* Gebruik **@id** om de persistente URI te documenteren voor de Entiteit waarop het JSON-object betrekking heeft.&#x20;
*   Het gebruik van **@id** is **verplicht** voor de (hoofd-)Entiteit waarop de root van het JSON-document betrekking heeft.

    ```
    { "@id":"https://stad.gent/id/mensgemaaktobject/dmg/530008250/2022-06-22T00:00:50.901Z"}
    ```
* Het gebruik van **@id**  is **aanbevolen** voor de Entiteiten die een eigenschap van de hoofdEntiteit karakteriseren.&#x20;

```
{
"@id":"https://stad.gent/id/mensgemaaktobject/dmg/530008250/2022-06-22T00:00:50.901Z",
"@type":"MensgemaaktObject"
"heeftType":{
    "@type:"Type",
    "@id":"http://stad.gent/id/concept/300033618",
    "heeftVoorkeursterm":{
        "@value":"schilderij"
        }
    }
}
```

*   &#x20;Het gebruik van **@id**  is **verplicht** wanneer je een Entiteiten wil mappen naar een Veld in het Invulboek Objecten waar zich de beschrijvingsregels bevinden voor de inhoud van het JSON-object.&#x20;

    ```
    {
    "@id":"https://stad.gent/id/mensgemaaktobject/dmg/530008250/2022-06-22T00:00:50.901Z",
    "@type":"MensgemaaktObject"
    "heeftType":{
        "@type:"Type",
        "@id":"http://stad.gent/id/concept/300033618",
        "heeftVoorkeursterm":{
            "@value":"schilderij"
            },
        "heeftType":{
            "@type":"Type",
            "@id":"cest:Term_objectnaam"
            }
        }
    }
    ```
*   Gebruik de eigenschap "**wordtGeïdentificeerdDoor**" en "**Identificator**" om lokale objectnummers en andere interne identificatienummers te documenteren.

    ```
    {
    "@id":"https://stad.gent/id/mensgemaaktobject/dmg/530008250/2022-06-22T00:00:50.901Z",
    "@type":"MensgemaaktObject"
    "wordtGeïdentificeerdDoor":{
        "@type:"Identificator",
        "@value":"530008250",
        "heeftType":{
            "@type":"Type",
            "@id":"cest:Waarde_objectnummer"
            },
        }
    }isHetzelfdeAls
    ```
* Gebruik de eigenschap "**isHetzelfdeAls**" om je Entiteit te mappen met een equivalente Entiteit in een anderen bron&#x20;

```
"@id":"https://stad.gent/id/mensgemaaktobject/dmg/530008250/2022-06-22T00:00:50.901Z",
"@type":"MensgemaaktObject"
"heeftType":{
    "@type:"Type",
    "@id":"http://vocab.getty.edu/aat/300033618",
    "heeftVoorkeursterm":{
        "@value":"schilderij",
        "@language":"nl"
        },
    "isHetzelfdeAls":{
        "@type:"Type",
        "@id":"http://vocab.getty.edu/aat/300033618",
        "heeftVoorkeursterm":{
            "@value":"painting (visual work) ",
            "@language":"en"
            },
    }
}
```

### 4. Toekenningen

* Classificaties
* Metingen
* Conditiebeoordelingen
* (andere activiteiten)

### 5. Werken, Expressies en Dingen

* Typische eigenschappen voor Werken
* Typische eigenschappen voor Expressies
* Typische eigenschappen voor Dingen

### 6. Historische Actoren

* Geboorte en dood
* Familiebanden
* Posities (ric:Position)
* Bezigheden (ric:Occupation

### 7. Historische Plaatsen

* Historische Toponiemen
* Coordinaten
* Archeologische Contexten
