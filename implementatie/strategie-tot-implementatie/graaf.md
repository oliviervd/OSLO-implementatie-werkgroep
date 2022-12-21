---
description: Modellering van een filmopname uit de Rural Film database.
---

# Graaf

Een heel schone film**Workshop tekening**

<figure><img src="../../.gitbook/assets/caggraph.jpeg" alt=""><figcaption><p>workshop whiteboard</p></figcaption></figure>

## Film

### Identificatienummer

| Veld   | Voorbeeld                            | CAG pattern                                                                                                 | OSLO pattern                                                                                                    |
| ------ | ------------------------------------ | ----------------------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------------------- |
| _Type_ | Objectnummer                         | (Film)-\[wordt geïdentificeerd door]-(Identificatienummer)-\[heeft type]-(Concept)-\[heeft naam]-(string)   | (ZelfstandigeExpressie)-\[identificator]-(Identificator)-\[type]-(Type Entiteit)-\[skos:prefLabel]-(TaalString) |
| Waarde | F000001                              | (Film)-\[wordt geïdentificeerd door]-(Identificatienummer)-\[heeft waarde]-(string)                         | (ZelfstandigeExpressie)-\[identificator]-(Identificator)-\[identificator]-(GetypeerdeString)                    |
| _Bron_ | Centrum voor Agrarische Geschiedenis | (Film)-\[wordt geidentificeerd door]-(Identificatienummer)-\[toegekend door]-(Actor)-\[heeft naam]-(string) | (ZelfstandigeExpressie)-\[identificator]-(Identificator)-\[toegekend door]-(Agent)-\[naam]-(TaalString)         |

**JSON-LD sample**

```
{
  @context:"https://data.cagnet.be/doc/osloapplicatieprofiel/context/cinema-rural.jsonld",
  "@type":"ZelfstandigeExpressie",
  "identificator":{
    "@type":"Identificator",
    "identificator":{
      "@type":"GetypeerdeString",
      "@value":"F000001"},
   "type":{
     "@type":"TypeEntiteit",
     "skos:prefLabel":{
         "@type":"TaalString",
         "@value":"Object identificatiecode",
         "@language":"nl"}
      },
    "toegekend door":{
      "@type":"Agent",
      "naam":{
        "@type":"TaalString",
        "@value":"Centrum Agrarische Geschiedenis",
        "@language":"nl"}
    }  
  }
 }
```

### Title

| Veld   | Voorbeeld                  | CAG pattern                                                                     | OSLO pattern                                                                                         |
| ------ | -------------------------- | ------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------- |
| Waarde | Frischer Wind In Streudorf | {Film)-\[heeft als titel]-(titel)-\[heeft waarde]-(string)                      | (ZelfstandigeExpressie)-\[titel]-(TaalObject)-\[inhoud]-(String)                                     |
| _Type_ | main title                 | {Film)-\[heeft als titel]-(titel)\[heeft type]-(Concept)-\[heeft naam]-(string) | (ZelfstandigeExpressie)-\[titel]-(TaalObject)-\[type]-(Type Entiteit)-\[skos:prefLabel]-(TaalString) |
| Taal   | de                         | {Film)-\[heeft als titel]-(titel)-\[heeft taal]-(string)                        | (ZelfstandigeExpressie)-\[titel]-(TaalObject)-(taal)-\[Taalcode]                                     |
|        |                            |                                                                                 |                                                                                                      |

**JSON-LD sample**

```
"{
  ""@context"":""https://data.cagnet.be/doc/osloapplicatieprofiel/context/cinema-rural.jsonld"",
  ""@type"":""ZelfstandigeExpressie"",
  ""titel"":[{
  ""@type"":""Taalobject"",
  ""inhoud"":{
  ""@type"":""String"",
  ""@value"":""Frischer Wind In Streudorf"",
    ""@language"":""de""},
""type"":{
  ""@type"":""TypeEntiteit"",
  ""skos:prefLabel"":{
    ""@type"":""TaalString"",
    ""@value"":""Display title"",
    ""@language"":""en""}
  } 
},
   {""@type"":""Taalobject"",
  ""inhoud"":{
  ""@type"":""String"",
  ""@value"":""Frischer Wind In Streudorf"",
    ""@language"":""de""},
""type"":{
  ""@type"":""TypeEntiteit"",
  ""skos:prefLabel"":{
    ""@type"":""TaalString"",
    ""@value"":""Main title"",
    ""@language"":""en""}
  }
}]"
```

### Commission

| Veld            | Voorbeeld  | CAG pattern                                                                                 | OSLO pattern                                                                                                                                               |
| --------------- | ---------- | ------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Type            | orderer    | {Film)-\[is besteld door]-(Event)-\[heeftType]-(Concept)-\[heeft naam]-(string)             | (ZelfstandigeExpressie)-\[crm:P92 was brought into existence]-(Activiteit)-\[type]-(Type Entiteit)-\[skos:prefLabel]-(TaalString)                          |
| Familienaam     | Borel      | {Film)-\[is besteld door]-(Event)-\[is opdrachtgever]-(Agent)-\[heeft familienaam]-(string) | (ZelfstandigeExpressie)-\[crm:P92 was brought into existence]-(Activiteit)-\[activiteit]-(Rol)-\[agent]-(Persoon)-\[heeft achternaam]-(TaalString)         |
| Voornaam        | Victor     | {Film)-\[is besteld door]-(Event)-\[is opdrachtgever]-(Agent)-\[heeft voornaam]-(string)    | (ZelfstandigeExpressie)-\[crm:P92 was brought into existence]-(Activiteit)-\[activiteit]-(Rol)-\[agent]-(Persoon)-\[heeft voornaam]-(TaalString)           |
| organisatienaam | Boerenbond | {Film)-\[is besteld door]-(Event)-\[is opdrachtgever]-(Agent)-\[heeft naam]-(string)        | (ZelfstandigeExpressie)-\[crm:P92 was brought into existence]-(Activiteit)-\[activiteit]-(Rol)-\[agent]--(Organisatie)-\[heeft voorkeursnaam]-(TaalString) |
| Rol             | orderer    | {Film)-\[is besteld door]-(Event)-\[is opdrachtgever]-(Agent)-\[heeft type]-(string)        | (ZelfstandigeExpressie)-\[crm:P92 was brought into existence]-(Activiteit)-\[activiteit]-(Rol)-\[type]-(Type Entiteit)-\[skos:prefLabel]-(TaalString)      |

**JSON-LD sample**

```
"{
  ""@context"":""https://data.cagnet.be/doc/osloapplicatieprofiel/context/cinema-rural.jsonld"",
  ""@type"":""ZelfstandigeExpressie"",
  ""creatie"":{
    ""@type"":""Creatie"",
    ""activiteit"":{
      ""@type"":""Rol"",
      ""agent"":{
      ""@type"":""Persoon"",
        ""heeft achternaam"":{
        ""@type"":""Taalstring"",
        ""@value"":""Borel"",
        ""@language"":""nl""},
        ""heeft voornaam"":{
        ""@type"":""Taalstring"",
        ""@value"":""Victor"",
          ""@language"":""nl""}},
      ""rol"":{
      ""@type"":""Type Rol"",
      ""skos:prefLabel"":{
      ""@type"":""Taalstring"",
      ""@value"":""director"",
      ""@language"":""en""}
    }
        }
    }
      
  }"
```

****

### Creation

| Veld       | Voorbeeld | CAG pattern                                                                                                                                           | OSLO pattern                                                                                                         |
| ---------- | --------- | ----------------------------------------------------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------- |
| Achternaam | Nackaerts | {Film)-\[is geregiseerd door]-(Event)-\[is regisseur]-(Agent)-\[heeft familienaam]-(string)                                                           | (ZelfstandigeExpressie)-\[creatie]-(Creatie)-\[activiteit]-(Rol)-\[agent]-(Persoon)-\[heeft achternaam]-(TaalString) |
| Voornaam   | Hein      | {Film)-\[is geregiseerd door]-(Event)-\[is regisseur]-(Agent)-\[heeft voornaam]-(string)                                                              | (ZelfstandigeExpressie)-\[creatie]-(Creatie)-\[activiteit]-(Rol)-\[agent]-(Persoon)-\[heeft voornaam]-(TaalString)   |
| Rol        | Director  | {Film)-\[is geregiseerd door]-(Event)-\[is uitgevoerd door]-(Agent)-\[heeft rol]-(string)-\[heeft als classificatie]-(Concept)-\[heeft naam]-(String) | (ZelfstandigeExpressie)-\[creatie]-(Creatie)-\[activiteit]-(Rol)-\[rol]-(Type Rol)-\[skos:prefLabel]-(TaalString)    |

### Publication

| Veld                         | Voorbeeld                                               | CAG pattern                                                                                   | OSLO pattern                                                                                                                                  |
| ---------------------------- | ------------------------------------------------------- | --------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------------------------------------------------- |
| Type: production             |                                                         |                                                                                               |                                                                                                                                               |
| Producer Persoon familienaam | Vantomme                                                | {Film)-\[is geproduceerd door]-(Event)-\[is producent]-(Agent)-\[heeft familienaam]-(string)  | (ZelfstandigeExpressie)-\[publicatieexpressie]-(Publicatie)-\[is uitgevoerd door]-(Persoon)-\[heeft achternaam]-(TaalString)                  |
| Producer Persoon voornaam    | Eric                                                    | {Film)-\[is geproduceerd door]-(Event)-\[is producent]-(Agent)-\[heeft voornaam]-(string)     | (ZelfstandigeExpressie)-\[publicatieexpressie]-(Publicatie)-\[is uitgevoerd door]-(Persoon)-\[heeft voornaam]-(TaalString)                    |
| Producer Organisatie naam    | Aan- en Verkoopsgenootschap van de Belgische Boerenbond | {Film)-\[is geproduceerd door]-(Event)-\[is producent]-(Agent)-\[heeft naam]-(string)         | (ZelfstandigeExpressie)-\[publicatieexpressie]-(Publicatie)-\[is uitgevoerd door]-(Organisatie)-\[heeft voorkeursnaam]-(TaalString)           |
| Producer Rol                 | producer                                                | {Film)-\[is geproduceerd door]-(Event)-\[is producent]-(Agent)-\[heeft rol]-(string)          | (ZelfstandigeExperssie)-\[publicatieexpressie]-(Publicatie)-\[is uitgevoerd door]-(Organisatie)-\[rol]-(TypeRol)-(heeft waarde)-\[TaalString] |
| productieland                | België                                                  | {Film)-\[heeft als productieplaats]-(productieplaats)-\[heeft waarde]-(string)                | (ZelfstandigeExpressie)-\[creatie]-(Locatie)-\[naam]-(TaalString)                                                                             |
| productiejaar                | 1963                                                    | {Film)-\[wordt gemaakt door]-(Event)\[heeft tijdspanne]-(tijdspanne)-\[heeft waarde]-(string) |                                                                                                                                               |
| Search Date                  | 1960-1963                                               | {Film)-\[wordt gemaakt door]-(Event)\[heeft type]-(concept)-\[heeft naam]-(string)            | (ZelfstandigeExpressie)-(expressie)-\[ExpressieCreatie]-\[tijd]-(Periode)                                                                     |

### Description

| Veld                 | Voorbeeld               | CAG pattern                                                                           | OSLO pattern                                                                 |
| -------------------- | ----------------------- | ------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------- |
| Description          | Een heel schone film    | {Film)-\[wordt beschreven door]-(tekst)\[heeft waarde]-(string)                       | (ZelfstandigeExpressie)-\[beschrijving]-(Beschrijving)-\[tekst]-(TaalString) |
| Description Language | NL                      | {Film)-\[wordt beschreven door]-(tekst)\[heeft taal]-(string)                         | (ZelfstandigeExpressie)-\[beschrijving]-(Beschrijving)-\[taal]-(TaalCode)    |
| Abstract             | A very beautyfull movie | {Film)-\[wordt beschreven door]-(tekst)\[heeft type]-(Concept)-\[heeft naam]-(string) | (ZelfstandigeExpressie)-\[beschrijving]-(Beschrijving)-\[tekst]-(TaalString) |
| Abstract Language    | EN                      | {Film)-\[wordt beschreven door]-(tekst)\[heeft taal]-(string)                         | (ZelfstandigeExpressie)-\[beschrijving]-(Beschrijving)-\[taal]-(TaalCode)    |

### Rights

## Film Copy

### Film Copy Number

| Veld        | Voorbeeld | CAG pattern                                                                                           | OSLO pattern                                                                                                                |
| ----------- | --------- | ----------------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------------------------------- |
| Filmcopy id | 3282      | {Film)-\[heeft als drager]-(Filmkopie)-\[wordt geïdentificeerd door]-(ID-nr)-\[heeft waarde]-(string) | (ZelfstandigeExpressie)-\[drager]-(Mensgemaakt Object)-\[identificator]-(Identificator)-\[identificator]-(GetypeerdeString) |

**JSON-LD sample**

```
{
  "@context":"https://data.cagnet.be/doc/osloapplicatieprofiel/context/cinema-rural.jsonld",
  "@type":"ZelfstandigeExpressie",
  "drager":{
    "@type":"Mensgemaakt Object",
    "identificator":{
      "@type":"Identificator",
      "identificator":{
        "@type":"GetypeerdeString",
        "@value":"3282"},
      "type":{
        "@type":"Type Entiteit",
        "skos:prefLabel":{
          "@type":"TaalString",
          "@value":"Filmcopy id"},
        "toegekend door":{
          "@type":"Agent",
          "naam":{
            "@type":"Taalstring",
            "@value":"Centrum Agrarische Geschiedenis"
          }
        }
        }
      }
    }
}
```

### Rights

### Provenance

| Veld             | Voorbeeld                             | CAG pattern                                                                                                               | OSLO pattern                                                                                                                            |
| ---------------- | ------------------------------------- | ------------------------------------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------------------------------------------- |
| Inventory Number | G9584bF                               | {Filmkopie)-\[wordt geidentificeerd door]-(Identificatiecode)\[heeft waarde]-(string)                                     |                                                                                                                                         |
| Institution      | Cinematek                             | {Film)-\[heeft als drager]-(Filmkopie)-\[wordt bewaard door]-(Organisatie)-\[heeft naam]-(string)                         | (ZelfstandigeExpressie)-\[drager]-(Mensgemaakt Object)-\[beheerder]-(Agent)-\[naam]-(TaalString)                                        |
| Repository       | A very beautyfull movie               | {Film)-\[wordt beschreven door]-(tekst)\[heeft type]-(Concept)-\[heeft naam]-(string)                                     | (ZelfstandigeExpressie)-\[beschrijving]-(Beschrijving)-\[tekst]-(TaalString)                                                            |
| Collection       | Filmcollectie Ministerie van Landbouw | {Film)-\[heeft als drager]-(Filmkopie)-\[is deel van]-(Collectie)-\[heeft naam]-(string)                                  | (ZelfstandigeExpressie)-\[drager]-(Mensgemaakt Object)-\[isOnderdeelVan]-(GecureerdeCollectie)-\[titel]-(TaalString)                    |
| Owner            | FOD Economie                          | {Film)-\[heeft als drager]-(Filmkopie)-\[is deel van]-(Collectie)-\[is eigendom van]-(organisatie)-\[heeft naam]-(string) | (ZelfstandigeExpressie)-\[drager]-(Mensgemaakt Object)-\[isOnderdeelVan]-(GecureerdeCollectie)-\[eigenaar]-(Agent)-\[naam]-(TaalString) |

**JSON-LD sample**

```
{
  "@context":"https://data.cagnet.be/doc/osloapplicatieprofiel/context/cinema-rural.jsonld",
  "@type":"ZelfstandigeExpressie",
  "drager":{
    "@type":"Mensgemaakt Object",
    "beheerder":{
      "@type":"Agent",
      "naam":{
        "@type":"TaalString",
        "@value":"Cinematek",
        "@language":"nl"}
      },
    "isOnderdeelVan":{
      "@type":"GecureerdeCollectie",
      "titel":{
        "@type":"TaalString",
        "@value":"Filmcollectie Ministerie van Landbouw",
        "@language":"nl"},
      "curator":{
        "@type":"Agent",
        "naam":{
          "@type":"TaalString",
          "@value":"Cinematek",
          "@language":"nl"}
        },
      "eigenaar":{
        "@type":"Agent",
        "naam":{
          "@type":"TaalString",
          "@value": "FOD Economie",
          "@language":"nl"}
      }
      }
      }
}
```

### Rights

### Format

| Veld           | Voorbeeld | CAG pattern                                                             | OSLO pattern |
| -------------- | --------- | ----------------------------------------------------------------------- | ------------ |
| Carrier Type   | film      | {Filmkopie)-\[heeft als classificatie]-(Concept)-\[heeft naam]-(string) |              |
| Carrier Format | 8 mm      | {Filmkopie)-\[heeft als classificatie]-(Concept)-\[heeft naam]-(string) |              |

### Rights

### Extent

### Condition

| Veld           | Voorbeeld | CAG pattern                                                                                            | OSLO pattern       |
| -------------- | --------- | ------------------------------------------------------------------------------------------------------ | ------------------ |
| Condition      |           | {Filmkopie)-\[heeft conditie]-(Conditie)-\[heeft naam]-(string)                                        | slecht             |
| Condition Note |           | {Filmkopie)-\[heeft conditie]-(Conditie)-\[heeft beschrijving]-(Beschrijving)=\[heeft waarde]-(string) | er zit een vlek op |
|                |           |                                                                                                        |                    |

### Rights
