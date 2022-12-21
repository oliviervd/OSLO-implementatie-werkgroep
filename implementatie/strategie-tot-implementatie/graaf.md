---
description: Modellering van een filmopname uit de Rural Film database.
---

# Graaf

workshop tekening

<figure><img src="../../.gitbook/assets/caggraph.jpeg" alt=""><figcaption><p>workshop whiteboard</p></figcaption></figure>

## Film

### Identification



| Veld | Voorbeeld                                     | CAG pattern                                                                                                 | OSLO pattern                                                                                                    |
| ---- | --------------------------------------------- | ----------------------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------------------- |
| __   | _Type_: Objectnummer                          | (Film)-\[wordt geïdentificeerd door]-(Identificatienummer)-\[heeft type]-(Concept)-\[heeft naam]-(string)   | (ZelfstandigeExpressie)-\[identificator]-(Identificator)-\[type]-(Type Entiteit)-\[skos:prefLabel]-(TaalString) |
| __   | _Waarde_ : F000001                            | (Film)-\[wordt geïdentificeerd door]-(Identificatienummer)-\[heeft waarde]-(string)                         | (ZelfstandigeExpressie)-\[identificator]-(Identificator)-\[identificator]-(GetypeerdeString)                    |
| __   | _Bron_ : Centrum voor Agrarische Geschiedenis | (Film)-\[wordt geidentificeerd door]-(Identificatienummer)-\[toegekend door]-(Actor)-\[heeft naam]-(string) | (ZelfstandigeExpressie)-\[identificator]-(Identificator)-\[toegekend door]-(Agent)-\[naam]-(TaalString)         |

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

| Voorbeeld                            | CAG                                                                             | OSLO                                                                                                 |
| ------------------------------------ | ------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------- |
| Waarde: "Frischer Wind In Streudorf" | {Film)-\[heeft als titel]-(titel)-\[heeft waarde]-(string)                      | (ZelfstandigeExpressie)-\[titel]-(TaalObject)-\[inhoud]-(String)                                     |
| Type: "main title"                   | {Film)-\[heeft als titel]-(titel)\[heeft type]-(Concept)-\[heeft naam]-(string) | (ZelfstandigeExpressie)-\[titel]-(TaalObject)-\[type]-(Type Entiteit)-\[skos:prefLabel]-(TaalString) |
| Taal:"de"                            | {Film)-\[heeft als titel]-(titel)-\[heeft taal]-(string)                        | (ZelfstandigeExpressie)-\[titel]-(TaalObject)-(taal)-\[Taalcode]                                     |
|                                      |                                                                                 |                                                                                                      |

### Commission

| Voorbeeld                   | CAG                                                                                         | OSLO                                                                                                                                                       |
| --------------------------- | ------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Type: order                 | {Film)-\[is besteld door]-(Event)-\[heeftType]-(Concept)-\[heeft naam]-(string)             | (ZelfstandigeExpressie)-\[crm:P92 was brought into existence]-(Activiteit)-\[type]-(Type Entiteit)-\[skos:prefLabel]-(TaalString)                          |
| Familienaam: Borel          | {Film)-\[is besteld door]-(Event)-\[is opdrachtgever]-(Agent)-\[heeft familienaam]-(string) | (ZelfstandigeExpressie)-\[crm:P92 was brought into existence]-(Activiteit)-\[activiteit]-(Rol)-\[agent]-(Persoon)-\[heeft achternaam]-(TaalString)         |
| Voornaam: Victor            | {Film)-\[is besteld door]-(Event)-\[is opdrachtgever]-(Agent)-\[heeft voornaam]-(string)    | (ZelfstandigeExpressie)-\[crm:P92 was brought into existence]-(Activiteit)-\[activiteit]-(Rol)-\[agent]-(Persoon)-\[heeft voornaam]-(TaalString)           |
| organisatienaam: Boerenbond | {Film)-\[is besteld door]-(Event)-\[is opdrachtgever]-(Agent)-\[heeft naam]-(string)        | (ZelfstandigeExpressie)-\[crm:P92 was brought into existence]-(Activiteit)-\[activiteit]-(Rol)-\[agent]--(Organisatie)-\[heeft voorkeursnaam]-(TaalString) |
| Rol: orderer                | {Film)-\[is besteld door]-(Event)-\[is opdrachtgever]-(Agent)-\[heeft type]-(string)        | (ZelfstandigeExpressie)-\[crm:P92 was brought into existence]-(Activiteit)-\[activiteit]-(Rol)-\[type]-(Type Entiteit)-\[skos:prefLabel]-(TaalString)      |

### Creation

| Voorbeeld             | CAG                                                                                                                                                   | OSLO                                                                                                                 |
| --------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------- |
| Achternaam: Nackaerts | {Film)-\[is geregiseerd door]-(Event)-\[is regisseur]-(Agent)-\[heeft familienaam]-(string)                                                           | (ZelfstandigeExpressie)-\[creatie]-(Creatie)-\[activiteit]-(Rol)-\[agent]-(Persoon)-\[heeft achternaam]-(TaalString) |
| Voornaam: Hein        | {Film)-\[is geregiseerd door]-(Event)-\[is regisseur]-(Agent)-\[heeft voornaam]-(string)                                                              | (ZelfstandigeExpressie)-\[creatie]-(Creatie)-\[activiteit]-(Rol)-\[agent]-(Persoon)-\[heeft voornaam]-(TaalString)   |
| Rol: Director         | {Film)-\[is geregiseerd door]-(Event)-\[is uitgevoerd door]-(Agent)-\[heeft rol]-(string)-\[heeft als classificatie]-(Concept)-\[heeft naam]-(String) | (ZelfstandigeExpressie)-\[creatie]-(Creatie)-\[activiteit]-(Rol)-\[rol]-(Type Rol)-\[skos:prefLabel]-(TaalString)    |

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

### Provenance

### Format

### Extent

### Condition

### Rights
