# JSON-LD sample

## Film&#x20;

### Identification

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

```
{
  "@context":"https://data.cagnet.be/doc/osloapplicatieprofiel/context/cinema-rural.jsonld",
  "@type":"ZelfstandigeExpressie",
  "titel":[{
  "@type":"Taalobject",
  "inhoud":{
  "@type":"String",
  "@value":"Frischer Wind In Streudorf",
    "@language":"de"},
"type":{
  "@type":"TypeEntiteit",
  "skos:prefLabel":{
    "@type":"TaalString",
    "@value":"Display title",
    "@language":"en"}
  } 
},
   {"@type":"Taalobject",
  "inhoud":{
  "@type":"String",
  "@value":"Frischer Wind In Streudorf",
    "@language":"de"},
"type":{
  "@type":"TypeEntiteit",
  "skos:prefLabel":{
    "@type":"TaalString",
    "@value":"Main title",
    "@language":"en"}
  }
}]
```

### Commission

### Creation

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

### Description

### Rights

### Film Copy

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

### Film Copy Number

### Provenance

### Format

### Extent

### Condition

### Rights

