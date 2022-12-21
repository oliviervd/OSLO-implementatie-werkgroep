---
description: Modellering van een filmopname uit de Rural Film database.
---

# Graaf

**Workshop tekening**

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

****

### Creation

| Voorbeeld             | CAG                                                                                                                                                   | OSLO                                                                                                                 |
| --------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------- |
| Achternaam: Nackaerts | {Film)-\[is geregiseerd door]-(Event)-\[is regisseur]-(Agent)-\[heeft familienaam]-(string)                                                           | (ZelfstandigeExpressie)-\[creatie]-(Creatie)-\[activiteit]-(Rol)-\[agent]-(Persoon)-\[heeft achternaam]-(TaalString) |
| Voornaam: Hein        | {Film)-\[is geregiseerd door]-(Event)-\[is regisseur]-(Agent)-\[heeft voornaam]-(string)                                                              | (ZelfstandigeExpressie)-\[creatie]-(Creatie)-\[activiteit]-(Rol)-\[agent]-(Persoon)-\[heeft voornaam]-(TaalString)   |
| Rol: Director         | {Film)-\[is geregiseerd door]-(Event)-\[is uitgevoerd door]-(Agent)-\[heeft rol]-(string)-\[heeft als classificatie]-(Concept)-\[heeft naam]-(String) | (ZelfstandigeExpressie)-\[creatie]-(Creatie)-\[activiteit]-(Rol)-\[rol]-(Type Rol)-\[skos:prefLabel]-(TaalString)    |

**JSON-LD sample**

```
{
  "@context":"https://data.cagnet.be/doc/osloapplicatieprofiel/context/cinema-rural.jsonld",
  "@type":"ZelfstandigeExpressie",
  "creatie":{
    "@type":"Creatie",
    "activiteit":{
      "@type":"Rol",
      "agent":{
      "@type":"Persoon",
        "heeft achternaam":{
        "@type":"Taalstring",
        "@value":"Borel",
        "@language":"nl"},
        "heeft voornaam":{
        "@type":"Taalstring",
        "@value":"Victor",
          "@language":"nl"}},
      "rol":{
      "@type":"Type Rol",
      "skos:prefLabel":{
      "@type":"Taalstring",
      "@value":"director",
      "@language":"en"}
    }
        }
    }
      
  }
```

### Publication

| Voorbeeld        | CAG                                                                                           | OSLO                                                                                                                                          |
| ---------------- | --------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------------------------------------------------- |
| Type: production |                                                                                               |                                                                                                                                               |
| Familienaam      | {Film)-\[is geproduceerd door]-(Event)-\[is producent]-(Agent)-\[heeft familienaam]-(string)  | (ZelfstandigeExpressie)-\[publicatieexpressie]-(Publicatie)-\[is uitgevoerd door]-(Persoon)-\[heeft achternaam]-(TaalString)                  |
| Voornaam         | {Film)-\[is geproduceerd door]-(Event)-\[is producent]-(Agent)-\[heeft voornaam]-(string)     | (ZelfstandigeExpressie)-\[publicatieexpressie]-(Publicatie)-\[is uitgevoerd door]-(Persoon)-\[heeft voornaam]-(TaalString)                    |
| Organisatienaam  | {Film)-\[is geproduceerd door]-(Event)-\[is producent]-(Agent)-\[heeft naam]-(string)         | (ZelfstandigeExpressie)-\[publicatieexpressie]-(Publicatie)-\[is uitgevoerd door]-(Organisatie)-\[heeft voorkeursnaam]-(TaalString)           |
| Rol              | {Film)-\[is geproduceerd door]-(Event)-\[is producent]-(Agent)-\[heeft rol]-(string)          | (ZelfstandigeExperssie)-\[publicatieexpressie]-(Publicatie)-\[is uitgevoerd door]-(Organisatie)-\[rol]-(TypeRol)-(heeft waarde)-\[TaalString] |
| productieland    | {Film)-\[heeft als productieplaats]-(productieplaats)-\[heeft waarde]-(string)                |                                                                                                                                               |
| productiejaar    | {Film)-\[wordt gemaakt door]-(Event)\[heeft tijdspanne]-(tijdspanne)-\[heeft waarde]-(string) |                                                                                                                                               |

### Description

| CAG                                                                                   | OSLO                                                                         |   |
| ------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------- | - |
| {Film)-\[wordt beschreven door]-(tekst)\[heeft waarde]-(string)                       | (ZelfstandigeExpressie)-\[beschrijving]-(Beschrijving)-\[tekst]-(TaalString) |   |
| {Film)-\[wordt beschreven door]-(tekst)\[heeft taal]-(string)                         | (ZelfstandigeExpressie)-\[beschrijving]-(Beschrijving)-\[taal]-(TaalCode)    |   |
| {Film)-\[wordt beschreven door]-(tekst)\[heeft type]-(Concept)-\[heeft naam]-(string) |                                                                              |   |

### Rights

## Film Copy

### Film Copy Number

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

### Provenance

**JSON-LD sample**

```
"{
  ""@context"":""https://data.cagnet.be/doc/osloapplicatieprofiel/context/cinema-rural.jsonld"",
  ""@type"":""ZelfstandigeExpressie"",
  ""drager"":{
    ""@type"":""Mensgemaakt Object"",
    ""beheerder"":{
      ""@type"":""Agent"",
      ""naam"":{
        ""@type"":""TaalString"",
        ""@value"":""Cinematek"",
        ""@language"":""nl""}
      },
    ""isOnderdeelVan"":{
      ""@type"":""GecureerdeCollectie"",
      ""titel"":{
        ""@type"":""TaalString"",
        ""@value"":""Filmcollectie Ministerie van Landbouw"",
        ""@language"":""nl""},
      ""curator"":{
        ""@type"":""Agent"",
        ""naam"":{
          ""@type"":""TaalString"",
          ""@value"":""Cinematek"",
          ""@language"":""nl""}
        },
      ""eigenaar"":{
        ""@type"":""Agent"",
        ""naam"":{
          ""@type"":""TaalString"",
          ""@value"": ""FOD Economie"",
          ""@language"":""nl""}
      }
      }
      }
}"
```

###

### Format

### Extent

### Condition

### Rights
