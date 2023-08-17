---
description: Modellering van poppcollectie Theater Taptoe en immaterieel erfgoedpraktijken.
---

# Graaf

<figure><img src="../../.gitbook/assets/HvA_mapping.jpg" alt="workshop whiteboard"><figcaption><p>workshop whiteboard</p></figcaption></figure>

## **Beschrijving object**

### **Bewaarinstelling**

| Veld                 | Voorbeeld      | HvA pattern | OSLO pattern                                                   |
| -------------------- | -------------- | ----------- | -------------------------------------------------------------- |
| Instellingsnaam (BA) | Huis van Alijn |             | (Mensgemaakt Object)-\[beheerder]-(Agent)-\[naam]-(TaalString) |
|                      |                |             |                                                                |
|                      |                |             |                                                                |

**JSON-LD sample**

```
{"@context":["./cultureel-erfgoed-event-ap.jsonld","./cultureel-erfgoed-object-ap.jsonld"],
"@type":"MensgemaaktObject",
 "beheerder":[{
   "@type": "Agent",
   "naam":"Huis van Alijn",
   "identificator": {
     "@type":"Identificator",
     "identificator":{
                "@type":"Getypeerde String",
                "@value":"https://www.wikidata.org/entity/Q2358158"
                                        }
                                }
                        }]
}
 
```

### **Collectie**

| Veld           | Voorbeeld  | HvA pattern | OSLO sample                                                                           |
| -------------- | ---------- | ----------- | ------------------------------------------------------------------------------------- |
| Collectie (CL) | Poppenspel |             | (MensgemaaktObject)-\[maakt deel uit van]-(Gecureerde collectie)-\[naam]-(TaalString) |
|                |            |             |                                                                                       |
|                |            |             |                                                                                       |

**JSON-LD sample**

```
{""@context"":[""./cultureel-erfgoed-event-ap.jsonld"",""./cultureel-erfgoed-object-ap.jsonld""],
""@type"":""MensgemaaktObject"",
 ""maakt deel uit van"":{
   ""@type"": ""GecureerdeCollectie"",
   ""naam"":""Poppenspel""
 }
}
```

### **Objectnummer**

| Veld              | Voorbeeld    | HvA pattern | OSLO sample                                                                     |
| ----------------- | ------------ | ----------- | ------------------------------------------------------------------------------- |
| Objectnummer (IN) | 2021-029-193 |             | (MensgemaaktObject)-\[identificator]-(Identificator)-\[naam]-(GetypeerdeString) |
|                   |              |             |                                                                                 |
|                   |              |             |                                                                                 |

**JSON-LD sample**

```
{""@context"":[""./cultureel-erfgoed-event-ap.jsonld"",""./cultureel-erfgoed-object-ap.jsonld""],
""@type"":""MensgemaaktObject"",
""identificator"":{
    ""@type"":""Identificator"",
     ""identificator"":{
        ""@type"":""Getypeerde String"",
        ""@value"":""2022-029-193""
        }
    }
}
```

### **Huidige standplaats**

| Veld                         | Voorbeeld                          | HvA pattern | OSLO sample                                                                                                                              |
| ---------------------------- | ---------------------------------- | ----------- | ---------------------------------------------------------------------------------------------------------------------------------------- |
| Huidige standplaatsnaam (2A) | Ghe\_B\_04\_07\_03\_b/ALIJN\_01056 |             | (MensgemaaktObject)-\[verhuis]-(Verhuis)-\[verhuist naar]-(Locatie)-\[identificator]-(Identificator)-\[identificator]-(GetypeerdeString) |
| Uitvoerder (2R)              | ldemaertelaer                      |             | " (MensgemaaktObject)-\[verhuis]-(Verhuis)-\[uitgevoerd door]-(Agent)-\[naam]-(TaalString) "                                             |
|                              |                                    |             |                                                                                                                                          |

**JSON-LD sample**

```
{""@context"":[""./cultureel-erfgoed-event-ap.jsonld"",""./cultureel-erfgoed-object-ap.jsonld""],
""@type"":""MensgemaaktObject"",
 ""verhuisd"": [{
   ""@type"":""Verhuis"",
   ""verhuist naar"":{
     ""@type"": ""Locatie"",
     ""identificator"":{
       ""@type"":""Identificator"",
       ""identificator"":{
                 ""@type"":""Getypeerde String"",
                 ""@value"":""Ghe_B_04_07_03_b/ALIJN_01056""
       }
     },
    ""uitgevoerd door"":{
      ""@type"": ""Agent"",
      ""naam"":{
          ""@type"":""TaalString"",
          ""@value"":""ldemaertelaer""
            }
       }  
     }
 }]
}

```

### **Objectnaam**

| Veld            | Voorbeeld | HvA pattern | OSLO sample                                                                                                                                                                         |
| --------------- | --------- | ----------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Objectnaam (OB) | Stokpop   |             | "(Mensgemaakt Object)-\[type]-(Type Entiteit)-\[naam]-(String) indien gelinkt aan erkende thesaurus: (Mensgemaakt Object)-\[type]-(Type Entiteit)-\[identificator]-(Identificator)" |
|                 |           |             |                                                                                                                                                                                     |
|                 |           |             |                                                                                                                                                                                     |

**JSON-LD sample**

```
{""@context"":[""./cultureel-erfgoed-event-ap.jsonld"",""./cultureel-erfgoed-object-ap.jsonld""],
""@type"":""MensgemaaktObject"",
 ""type"":[{
   ""@type"":""TypeEntiteit"",
   ""naam"":{
     ""@type"":""TaalString"",
     ""@value"":""stokpop"",
     ""@language"":""nl""
                        },
   ""identificator"":{
     ""@type"":""Identificator"",
     ""@id"":""http://vocab.getty.edu/page/aat/300226128""
                                 }
                 }]
}
```

### **Titel (+beschrijving)**

<table><thead><tr><th width="110">Veld</th><th width="414">Voorbeeld</th><th width="130">HvA pattern</th><th>OSLO sample</th></tr></thead><tbody><tr><td>Titel (TI)</td><td>Stokpop met masker en rode lingerie</td><td></td><td>(MensgemaaktObject)-[draagt]-(ZelfstandigeExpressie)-[titel]-(TaalString)</td></tr><tr><td>Titel (TI)</td><td></td><td></td><td>(MensgemaaktObject)-[draagt]-(ZelfstandigeExpressie)-[titel]-(TaalString)</td></tr><tr><td>Beschrijving (BE)</td><td>Don G. is een muziekvoorstelling van Theater Taptoe uit 2006. Als artistiek leider legt Freek Neirynck voornamelijk de focus op teksttheater. Na zijn vertrek in 2003 nemen Luk De Bruyker en Dirk De Strooper de artistieke leiding over. In die periode wordt alsmaar meer voor muziektheater gekozen, deels uit interesse, deels onder druk van toenmalig minister van cultuur Bert Anciaux die wil dat Taptoe zich herbront. Don G. is de eerste in een lange reeks samenwerkingen met blazersensemble I Solisti del Vento. Het stuk Don G. is een bewerking van de opera Don Giovanni van Wolfgang Amadeus Mozart. Het stuk wordt ingekort en de locatie verplaatst naar het Venetië van Casanova en Pulcinella, met de personages Don Giovanni en Leporello.</td><td></td><td>(MensgemaaktObject)-[draagt]-(ZelfstandigeExpressie)-[beschrijving]-(TaalString)</td></tr></tbody></table>

**JSON-LD sample**

```
{""@context"":[""./cultureel-erfgoed-event-ap.jsonld"",""./cultureel-erfgoed-object-ap.jsonld""],
  ""@type"":""Mensgemaakt Object"",
         ""draagt"":[{
                 ""@type"":""ZelfstandigeExpressie"",
                          ""titel"":[{
                            ""@type"":""Taalstring"",
                            ""@value"":""Stokpop met masker en rode lingerie"",
              ""@language"":""nl""
                            }],
                    ""beschrijving"":[{
                    ""@type"":""Taalstring"",
                ""@value"":""Don G. is een muziekvoorstelling van Theater Taptoe uit 2006. Alsartistiek leider legt Freek Neirynck voornamelijk de focus op teksttheater. Na zijn vertrek in 2003 nemen Luk De Bruyker en Dirk De Strooper de artistieke                         leiding over. In die periode wordt alsmaar meer voor muziektheater gekozen, deels uit interesse, deels onder druk van toenmalig minister van cultuur Bert Anciaux die wil dat Taptoe zich herbront. Don G. is de eerste in een lange reeks samenwerkingen met blazersensemble I Solisti del Vento. Het stuk Don G. is een bewerking van de opera Don Giovanni van Wolfgang Amadeus Mozart. Het stuk wordt ingekort en de locatie verplaatst naar het Venetië van Casanova en Pulcinella, met de personages Don Giovanni en Leporello."",
                   ""@language"":""nl""
}]
    }]
}


```

**Vervaardiger**

<table><thead><tr><th width="174">Veld</th><th width="166">Voorbeeld</th><th width="118">HvA pattern</th><th>OSLO sample</th></tr></thead><tbody><tr><td>Vervaardiger (VV)</td><td>De Strooper, Dirk</td><td></td><td>(MensgemaaktObject)-[draagt]-(ZelfstandigeExpressie)-[productie]-(Productie)-[uitgevoerd door]-(Agent)-[naam]-(String)</td></tr><tr><td>Rol (FU)</td><td>ontwerper</td><td></td><td>(MensgemaaktObject)-[draagt]-(ZelfstandigeExpressie)-[productie]-(Productie)-[uitgevoerd door]-(Agent)-[type]-(Type Entiteit)-[identificator]-(Identificator)-[identificator]-(String)</td></tr><tr><td>Vervaardiger (VV)</td><td>De Bruyker, Luk</td><td></td><td>(MensgemaaktObject)-[draagt]-(ZelfstandigeExpressie)-[productie]-(Productie)-[uitgevoerd door]-(Agent)-[naam]-(String)</td></tr><tr><td>Rol (FU)</td><td>ontwerper</td><td></td><td>(MensgemaaktObject)-[draagt]-(ZelfstandigeExpressie)-[productie]-(Productie)-[uitgevoerd door]-(Agent)-[type]-(Type Entiteit)-[identificator]-(Identificator)-[identificator]-(String)</td></tr><tr><td>Plaats (VP)</td><td>Gent</td><td></td><td>(MensgemaaktObject)-[draagt]-(ZelfstandigeExpressie)-[productie]-(Productie)-[plaats]-(Locatie)-[identificator]-(Identificator)</td></tr><tr><td>Datering van (DS)</td><td>2008</td><td></td><td>(MensgemaaktObject)-[draagt]-(ZelfstandigeExpressie)-[productie]-(Productie)-[tijd]-(Periode)</td></tr><tr><td>Precisie (DR)</td><td></td><td></td><td>?</td></tr><tr><td>Datering van (DS)</td><td></td><td></td><td>(MensgemaaktObject)-[draagt]-(ZelfstandigeExpressie)-[productie]-(Productie)-[tijd]-(Periode)</td></tr><tr><td>Precisie (DR)</td><td></td><td></td><td>?</td></tr></tbody></table>

**JSON-LD sample**

```
{""@context"":[""./cultureel-erfgoed-event-ap.jsonld"",""./cultureel-erfgoed-object-ap.jsonld""],
  ""@type"":""MensGemaaktObject"",
   ""draagt"":{
 ""@type"":""ZelfstandigeExpressie"",
""productie"":{
 ""@type"":""Productie"",
""uitgevoerd door"":{
         ""@type"":""Agent"",
""@id"":""http://www.wikidata.org/entity/Q47208588"",
""naam"":""De Bruyker, Luk""
}
}
}
}
```

## **Beschrijving immaterieel erfgoedpraktijk**

Geen velden in Adlib maar belangrijke elementen in Immaterieel erfgoedluik.



| Veld                | Voorbeeld                             | HvA pattern | OSLO pattern                                                                                                               |
| ------------------- | ------------------------------------- | ----------- | -------------------------------------------------------------------------------------------------------------------------- |
| Associatie praktijk | Poppenspel                            |             | (Mensgemaakt Object)-\[wordt gedragen door]-(Zelfstandige Expressie)-\[realiseert]-(Conceptueel Ding)-\[naam]-(TaalString) |
| ICE praktijk        | Figurentheater                        |             | (Zelfstandige expressie)-\[realiseert]-(Conceptueel Ding)-\[type]-(Type Entiteit)                                          |
| Specifiek ICE item  | Het figurentheater van Theater Taptoe |             | (Zelfstandige expressie)-\[realiseert]-(Conceptueel Ding)-\[naam]-(TaalString)                                             |
| Werk                | Don Juan                              |             | (Zelfstandige expressie)-\[realiseert]-(Werk)-\[titel])-(TaalString)                                                       |
| Expressie           | Don G.                                |             | (MensgemaaktObject)-\[is geassocieerd met]-(Zelfstandige expressie)-\[titel]-(TaalString)                                  |
| Voorstelling        | Don G. première, 2008                 |             | (Zelfstandige expressie)-\[uitgevoerde versie]-(Voorstelling)-\[naam]-(TaalString)                                         |

**JSON-LD pattern**

```
{""@context"":[""./cultureel-erfgoed-event-ap.jsonld"",""./cultureel-erfgoed-object-ap.jsonld""],
""@type"":""ZelfstandigeExpressie"",
 ""titel"":{
   ""@type"":""TaalString"",
   ""@value"":""Don G."",
   ""@language"":""nl""
 },
 ""realiseert"":[{
   ""@type"":""ConceptueelDing"",
   ""type"":{
     ""@type"":""TypeEntiteit"",
   	 ""naam"":{
   		""@type"":""TaalString"",
   		""@value"":""ICE Item""}
 	},
   ""naam"":{
   		""@type"":""TaalString"",
   		""@value"":""Figurentheater van Theater Taptoe""}

 },{
   ""@type"":""Werk"",
   ""titel"":{
   ""@type"":""TaalString"",
   ""@value"":""Don Juan""
   }
 }],
 ""uitgevoerde versie"":{
   ""@type"":""Voorstelling"",
   	""naam"":{
   		""@type"":""TaalString"",
      	""@value"":""Première Don G. 2008"",
      	""@language"":""nl""}
 }
}
```
