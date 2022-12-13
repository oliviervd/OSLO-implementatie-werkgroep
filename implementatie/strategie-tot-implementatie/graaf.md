# Graaf

workshop tekening

<figure><img src="../../.gitbook/assets/caggraph.jpeg" alt=""><figcaption><p>workshop whiteboard</p></figcaption></figure>

## Film

### Identification

#### Film Number

vb. F000001 (Object identificationcode)

* ebucore: /ebucore:identifier/dc:identifier
* CAG pattern:&#x20;
  * (Film)-\[wordt geïdentificeerd door]-(Identificatienummer)-\[heeft waarde]-(string)
  * {Film)-\[wordt geïdentificeerd door]-(Identificatienummer)-\[heeft type]-(Concept)-\[heeft naam]-(string)
* OSLO pattern:
  * (ZelfstandigeExpressie)-\[identificator]-(Identificator)-(identificator)-\[GetypeerdeString]
  * (ZelfstandigeExpressie)-\[identificator]-(Identificator)-\[type]-(Type Entiteit)-\[skos:prefLabel]-(TaalString)

#### Film Number Domain

vb. Centrum Agrarische Geschiedenis

EBUCORE pattern

* /

CAG pattern

* {Film)-\[wordt geidentificeerd door]-(Identificatienummer)-\[toegekend door]-(Actor)-\[heeft naam]-(string)

OSLO pattern

* (ZelfstandigeExpressie)-\[identificator]-(Identificator)-\[toegekend door]-(Agent)-\[naam]-(TaalString)

JSON-LD

```json
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

### Commission

### Creation

### Publication

### Description

### Rights

## Film Copy

### Film Copy Number

### Provenance

### Format

### Extent

### Condition

### Rights
