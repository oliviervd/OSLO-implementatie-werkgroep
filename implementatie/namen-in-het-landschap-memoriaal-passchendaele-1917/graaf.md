# Graaf

**Workshop tekening**

{% file src="../../.gitbook/assets/E4895873-C082-431A-A887-A37D3C0A4B37.heic" %}

### **Naam**

| Veld      | Voorbeeld      | MMP197 pattern                                                | OSLO pattern                                    |
| --------- | -------------- | ------------------------------------------------------------- | ----------------------------------------------- |
| firstName | Leonard Edward | (Persoon)-\[heeftNaam]-(Naam)-\[heeftVoornaam]-(Voornaam)     | (oslo:Persoon)-\[oslo:voornaam]-(oslo:String)   |
| lastName  | Stump          | (Persoon)-\[heeftNaam]-(Naam)-\[heeftAchternaam]-(Achternaam) | (oslo:Persoon)-\[oslo:achternaam]-(oslo:String) |
|           |                |                                                               |                                                 |

**JSON-LD sample**

```
{
  "@type": "Persoon",
  "voornaam": {
  "@type": "String",
  "@value": "Leonard Edward"
  }
  "achtenaam": {
    "@type": "String",
    "@value": "Stump"
  } 
 }
```

**Dienstnummer**

| Veld          | Voorbeeld | MMP197 pattern                     | OSLO pattern                                                                |
| ------------- | --------- | ---------------------------------- | --------------------------------------------------------------------------- |
| serviceNumber | 80141     | (Persoon)-\[heeftID]-(GeheelGetal) | (oslo:Persoon)-\[cidoc:P48 has preferred identifier]-(cidoc-E42 Identifier) |
|               |           |                                    |                                                                             |
|               |           |                                    |                                                                             |

**JSON-LD sample**

```
{
  "@type": "Persoon",
    "wordt geïdentificeerd door": {
    "@type": "Identificatienummer",
    "@value": "854254",
    "heeft type": {
      "@type": "Concept",
      "heeft naam":
       {
          "@type": "String",
          "@value": "Stamnummer",
          "@language": "nl"
        },
     }
  }
}
```

### Rang

| Veld | Voorbeeld | MMP197 pattern                                                                                                       | OSLO pattern                                                                                                                                                                        |
| ---- | --------- | -------------------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| rank |           | (Persoon)-\[heeftPositie]-(Position)-\[heeftRang]-(Rang)-\[heeftType]-(Type)-\[heeftNaam]-(Naam)-\[heeftTaal]-(Taal) | (oslo:Persoon)-\[RiC-R054:occupies or occupied]-(RiC:position)-\[cidoc:P2 has type (is type of)]-(cidoc:E55 Type)-\[cidoc:P1 is identified by (identifies)]-(cidoc:E41 Appellation) |
|      | Private   | (Persoon)-\[heeftPositie]-(Position)-\[heeftRang]-(Rang)-\[heeftNaam]-(Naam)-\[heeftTaal]-(Taal)                     | (oslo:Persoon)-\[RiC-R054:occupies or occupied]-(RiC:position)-\[cidoc:P1 is identified by (identifies)]-(cidoc:E41 Appellation)                                                    |
|      |           |                                                                                                                      |                                                                                                                                                                                     |

**JSON-LD sample**

```
{
  "@type": "Persoon",
  "bezet": {
    "@type": "Positie",
    "heeft type":
      {
        "@type": "String",
        "@value": "Rang",
        "@language": "nl"
      }
      
    "is geïdentificeerd door": 
      {
        "@type": "String",
        "@value": "Private"
        "@language": "nl"
     }
  }
}  
```

### Eenheid

| Veld | Voorbeeld                             | MMP197 pattern                                                                                                             | OSLO pattern                                                                                                                                                                                              |
| ---- | ------------------------------------- | -------------------------------------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| unit |                                       | (Persoon)-\[heeftPositie]-(Position)-\[heeftEenheid]-(Eenheid)-\[heeftType]-(Type)-\[heeftNaam]-(Naam)-\[heeftTaal]-(Taal) | (oslo:Persoon)-\[RiC-R054:occupies or occupied]-(RiC:position)-\[RiC-E12:exists or existed in]-(RiC-E09:Group)-\[cidoc:P2 has type]-(cidoc:E55 Type)-\[cidoc:P1 is identified by]-(cidoc:E41 Appellation) |
|      | Canadian Infantry, 31st Bn. (Alberta) | (Persoon)-\[heeftPositie]-(Position)-\[heeftEenheid]-(Eenheid)-\[heeftNaam]-(Naam)-\[heeftTaal]-(Taal)                     | (oslo:Persoon)-\[RiC-R054:occupies or occupied]-(RiC:position)-\[RiC-E12:exists or existed in]-(RiC-E09:Group)-\[cidoc:P1 is identified by]-(cidoc:E41 Appellation)                                       |
|      |                                       |                                                                                                                            |                                                                                                                                                                                                           |

**JSON-LD sample**

```
"{
  ""@type"": ""Persoon"",
  ""bezet"": {
    ""@type"": ""Positie"",
    ""bestaat in"": {
      ""@type"": ""Organisatie"",
      ""heeft type"": {
        ""@type"": ""Concept"",
        ""heeft naam"": {
          ""@type"": ""String"",
          ""@value"": ""Bataljon"",
          ""@language"": ""nl""
        }
       ""heeft naam"": {
         ""@type"": ""String"",
         ""@value"": ""Canadian Infantry, 31st Bn. (Alberta)"",
         ""@language"": ""en""
       }
      }
    }
  }
}"

```

### Geboorte

| Veld            | Voorbeeld                                           | MMP197 pattern                                                                                                                      | OSLO pattern                                                                                                                                                     |
| --------------- | --------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| dateOfBirth     | 9-11-1890                                           | (Persoon)-\[heeftGeboorte]-(Geboorte)-\[heeftDatum]-(Datum)                                                                         | (oslo:Persoon)-\[cidoc:P98 was born]-(cidoc:E67:Birth)-\[cidoc:P4:has time-span]-(cidoc:E52:Time-Span)                                                           |
| yearOfBirth     | 1890                                                |                                                                                                                                     |                                                                                                                                                                  |
| placeOfBirth    | Bayswater, Middlesex, Engeland, Verenigd Koninkrijk | (Persoon)-\[heeftGeboorte]-(Geboorte)-\[heeftLocatie]-(Locatie)-\[heeftNaam]-(Naam)-\[heeftTaal]-(Taal)                             | (oslo:Persoon)-\[cidoc:P98 was born]-(cidoc:E67:Birth)-\[cidoc:P7:took place at]-(cidoc:E53:Place)-\[cidoc:P1:is identified by]-(cidoc:E41:Appellation)          |
| placeOfBirthLat | 51.51116                                            | (Persoon)-\[heeftGeboorte]-(Geboorte)-\[heeftLocatie]-(Locatie)-\[heeftCoördinaat]-(Coördinaat)-\[heeftLengtegraad]-(Lengtegraad)   | (oslo:Persoon)-\[cidoc:P98 was born]-(cidoc:E67:Birth)-\[cidoc:P7:took place at]-(cidoc:E53:Place)-\[cidoc:P168 place is defined by]-(cidoc:E94:Space Primitive) |
| placeOfBirthLon | -0.18426                                            | (Persoon)-\[heeftGeboorte]-(Geboorte)-\[heeftLocatie]-(Locatie)-\[heeftCoördinaat]-(Coördinaat)-\[heeftBreedtegraad]-(Breedtegraad) | (oslo:Persoon)-\[cidoc:P98 was born]-(cidoc:E67:Birth)-\[cidoc:P7:took place at]-(cidoc:E53:Place)-\[cidoc:P168 place is defined by]-(cidoc:E94:Space Primitive) |

**JSON-LD sample**

```
{
  "@type": "Persoon",
  "werd geboren": {
    "@type": "Geboorte",
      "had tijdsspanne": {
        "heeft naam": {
        "@type": "String",
        "@value": "geboortedatum",
        "@language": "nl"
      },
      "heeft begindatum": {
        "@type": "String",
        "@value": "9-11-1890"
      },
      "heeft einddatum": {
        "@type": "String",
        "@value": "9-11-1890"
      }
    }
  }
 "was aanwezig bij": {
  "@type": ""Geboorte",
  "vond plaats op": {
    "@type": "Plaats",
    "op een plaats binnen": {
      "@type": "Space Primitive",
      "@value"": "51.51116,-0.18426"
      }
    "heeft type": {
      "@type": "Concept",
      "heeft naam": {
        "@type": "String",
        "@value": "Bayswater, Middlesex, Engeland, Verenigd Koninkrijk",
        "@language": "en"
}



```

### Dood

| Veld                      | Voorbeeld                 | MMP197 pattern                                                                                                                                             | OSLO pattern                                                                                                                                                                   |
| ------------------------- | ------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| dateOfDeath               | 6-11-1917                 | (Persoon)-\[sterft]-(Sterfte)-\[heeftDatum]-(Datum)                                                                                                        | (oslo:Persoon)-\[cidoc:P100:died in]-(cidoc:E69:Death)-\[cidoc:P4:has time-span (is time-span of)]-(cidoc:E52:Time-Span)                                                       |
| causeOfDeath              | Killed in action (K.I.A.) | (Persoon)-\[sterft]-(Sterfte)-\[heeftType]-(Type)-\[heeftNaam]-(Naam)-\[heeftTaal]-(Taal)                                                                  | (oslo:Persoon)-\[cidoc:P100:died in]-(cidoc:E69:Death)-\[cidoc:P2 has type]-(cidoc:E55 Type)-\[cidoc:P1 is identified by]-(cidoc:E41 Appellation)                              |
| exactCoordinateOfDeath    | 28.D.6.b.90.60            | (Persoon)-\[heeftSterfte]-(Sterfte)-\[heeftPlaats]-(Plaats)-\[heeftID]-(ID)                                                                                | (oslo:Persoon)-\[cidoc:P100:was death of (died in)]-(cidoc:E69:Death)-\[cidoc:P7:took place at]-(cidoc:E53:Place)-\[cidoc:P48 has preferred identifier]-(cidoc-E42 Identifier) |
| exactCoordinateOfDeathLat | 5.089.979                 | (Persoon)-\[heeftSterfte]-(Sterfte)-\[heeftPlaats]-(Plaats)-\[heeftCoördinaat]-(Coördinaat)-\[heeftLengtegraad]-(Lengtegraad)                              | (oslo:Persoon)-\[cidoc:P100:died in]-(cidoc:E69:Death)-\[cidoc:P7:took place at]-(cidoc:E53:Place)-\[cidoc:P168 place is defined by]-(cidoc:E94:Space Primitive)               |
| exactCoordinateOfDeathLon | 302.133                   | (Persoon)-\[heeftSterfte]-(Sterfte)-\[heeftPlaats]-(Plaats)-\[isOnderdeelVan]-(Plaats)-\[heeftCoördinaat]-(Coördinaat)-\[heeftBreedtegraad]-(Breedtegraad) | (oslo:Persoon)-\[cidoc:P100:died in]-(cidoc:E69:Death)-\[cidoc:P7:took place at]-(cidoc:E53:Place)-\[cidoc:P168 place is defined by]-(cidoc:E94:Space Primitive)               |
|                           |                           |                                                                                                                                                            |                                                                                                                                                                                |
|                           |                           |                                                                                                                                                            |                                                                                                                                                                                |

**JSON-LD sample**

```
{
  "@type": "Persoon",
  "stierf in": {
    "@type": "Overlijden",
      "had tijdsspanne": {
        "heeft naam": {
        "@type": "String",
        "@value": "sterfdatum",
        "@language": "nl"
      },
      "heeft begindatum": {
        "@type": "String",
        "@value": "6/11/1917"
      },
      "heeft einddatum": {
        "@type": "String",
        "@value": "6/11/1917"
      }
    }
    "heeft type": {
      "@type": "Concept",
      "heeft naam": {
        "@type": "String",
        "@value": "Killed in Action (K.I.A.)",
        "@language": "en"
      }
    }
   "wordt geïdentificeerd door": {
      "@type": "Concept",
      "heeft naam": {
        "@type": "String",
        "@value": "coordinate of death"
        "@language": "en"
      },
        "wordt geïdentificeerd door": {
          "@type": "String",
          "@value": "28.D.6.b.90.60"
        }
      }
     "heeft type": {
      "@type": "Plaats",
      "op een plaats binnen": {
        "@type": "Space Primitive",
        "@value": "51.51116,-0.18426"
      }
    }
  }
}
```

### Bio

| Veld                  | Voorbeeld                               | MMP197 pattern                                                                                                                   | OSLO pattern                                                                                                                                                                                        |
| --------------------- | --------------------------------------- | -------------------------------------------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| age                   | 26                                      |                                                                                                                                  |                                                                                                                                                                                                     |
| dateOfEnlistment      | 18-2-1915                               | (Persoon)-\[namDeelAan]-(Evenement)-\[heeftDatum]-(Datum)                                                                        | (oslo: Persoon)-\[RiC-R058i: is or was participant in]-(cidoc:E14 Event)-\[RiC-R068i is associated with date]-(RiC-E19 Single Date)                                                                 |
| placeOfEnlistment     | Calgary, Alberta                        | (Persoon)-\[namDeelAan]-(Evenement)-\[vondPlaatsOp]-(Plaats)                                                                     | (oslo: Persoon)-\[RiC-R058i: is or was participant in]-(cidoc:E14 Event)-\[cidoc:P7 took place at]-(E53 Place)-\[cidoc:P1 is identified by]-(cidoc:E41 Appellation)                                 |
| placeOfEnlistmentLat  | 5.105.011                               | (Persoon)-\[namDeelAan]-(Evenement)-\[vondPlaatsOp]-(Plaats)-\[heeftCoördinaat]-(Coördinaat)-\[heeftLengtegraad]-(Lengtegraad)   | (oslo: Persoon)-\[RiC-R058i: is or was participant in]-(cidoc:E14 Event)-\[cidoc:P7 took place at]-(E53 Place)-\[cidoc:P171:at some place within]-(cidoc:E94:Space Primitive)                       |
| placeOfEnlistmentLon  | -11.408.529                             | (Persoon)-\[namDeelAan]-(Evenement)-\[vondPlaatsOp]-(Plaats)-\[heeftCoördinaat]-(Coördinaat)-\[heeftBreedtegraad]-(Breedtegraad) | (oslo: Persoon)-\[RiC-R058i: is or was participant in]-(cidoc:E14 Event)-\[cidoc:P7 took place at]-(E53 Place)-\[cidoc:P171:at some place within]-(cidoc:E94:Space Primitive)                       |
| country               | Canada                                  | (Persoon)-\[namDeelAan]-(Evenement)-\[vondPlaatsOp]-(Plaats)-\[ValtOnder]-(Plaats)                                               | (oslo: Persoon)-\[RiC-R058i: is or was participant in]-(cidoc:E14 Event)-\[cidoc:P7 took place at]-(E53 Place)-\[P89 falls within]-(E53 Place)-\[cidoc:P1 is identified by]-(cidoc:E41 Appellation) |
| lastKnownResidence    | 811 Wakehurst St. Flin Flon, MB R8A 9K6 | (Persoon)-\[heeftVerblijfplaats]-(Verblijfplaats)-\[heeftAdres]-(Adres)                                                          | (oslo: Persoon)-\[cidoc:P74 has current or former residence]-(cidoc:E53 Place)-\[cidoc:P1 is identified by]-(cidoc:E41 Appellation)                                                                 |
| lastKnownResidenceLat | 5.105.011                               | (Persoon)-\[heeftVerblijfplaats]-(Verblijfplaats)-\[heeftVerbandMet]-(Plaats)-\[heeftCoördinaat]-(Coördinaat)                    | (oslo: Persoon)-\[cidoc:P74 has current or former residence]-(cidoc:E53 Place)-\[cidoc:P48 has preferred identifier]-(cidoc-E42 Identifier)                                                         |
| lastKnownResidenceLon | -11.408.529                             | (Persoon)-\[heeftVerblijfplaats]-(Verblijfplaats)-\[heeftVerbandMet]-(Plaats)-\[heeftCoördinaat]-(Coördinaat)                    | (oslo: Persoon)-\[cidoc:P74 has current or former residence]-(cidoc:E53 Place)-\[cidoc:P48 has preferred identifier]-(cidoc-E42 Identifier)                                                         |
| profession            | Hotel clerk                             | (Persoon)-\[heeftBeroep]-(Beroep)-\[heeftNaam]-(Naam)                                                                            | (oslo: Persoon)-\[schema:heeftBeroep]-(schema:Beroep)-\[cidoc:P1 is identified by (identifies)]-(cidoc:E41 Appellation)                                                                             |
| religion              | Church of England                       | (Persoon)-\[heeftReligie]-(Religie)-\[heeftNaam]-(Naam)                                                                          | /                                                                                                                                                                                                   |

### JSON-LD sample

<pre><code>{
  "@type": "Persoon",
  "is of was deelnemer in": {
    "@type": "Evenement",
    "wordt geassocieerd met de datum": {
      "@type":"Enkele datum",
      "@value":"18/02/1915"      
    }
  }
   "vond plaats te (getuige)": {
      "@type": "Plaats",
      "heeft naam": {
        "@type": "String",
        "@value": "Calgary, Alberta",
        "@language": "nl"
      }
    }
   "is of was deelnemer in": {
    "@type": "Evenement",
    "vond plaats te (getuige)": {
      "@type": "Plaats",
      "op een plaats binnen": {
        "@type": "Space Primitive",
        "@value": "50.905137, 3.024806"
      }
    }
  }
   "is of was deelnemer in": {
    "@type": "Evenement",
    "vond plaats te (getuige)": {
      "@type": "Plaats",      
      "valt onder": {
        "@type": "Plaats",
        "heeft naam": {
          "@type": "String",
          "@value": "Canada",
          "@language": "nl"
        }
      }
    }
  }
  "heeft huidige of voormalige woonplaats": {
    "@type": "Plaats",
    "heeft naam": {
      "@type": "String",
      "@value": "811 Wakehurst St. Flin Flon, MB R8A 9K6",
      "@language": "nl"
    }
    "op een plaats binnen": {
      "@type": "Space Primitive",
      "@value": "5.105.011, -11.408.529"
    }
  }
}

<strong>/{
</strong>  "@type": "Persoon",
  "heeft huidige of voormalige woonplaats": {
    "@type": "Plaats",
    "op een plaats binnen": {
      "@type": "Space Primitive",
      "@value": "5.105.011, -11.408.529"
    }
  }
}
</code></pre>

### Herdenking

| Veld     | Voorbeeld                   | MMP197 pattern                                                                                                              | OSLO pattern                                                                                                                                                                                                                                                                                                                             |
| -------- | --------------------------- | --------------------------------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| memorial | (type)                      | (Persoon)-\[wordtHerdachtIn]-(Herdenking)-\[heeftVeruiterlijkingIn]-(Object)-\[heeftType]-(Type)                            | (oslo:Persoon)-\[cidoc:P129 is subject of]-(cidoc:E5 Event)-\[cidoc:P20 had specific purpose]-(cidoc:E65 Creation)-\[cidoc:P94 has created]-(cidoc:E28 Conceptual Object)-\[cidoc:P108 has produced (was produced by)]-(cidoc:E22 Human-Made Object)-\[cidoc:P2 has type]-(cidoc:E55 Type)                                               |
| (naam)   | Ypres (Menin Gate) Memorial | (Persoon)-\[wordtHerdachtIn]-(Herdenking)-\[heeftVeruiterlijkingIn]-(Object)-\[heeftNaam]-(Naam)                            | (oslo:Persoon)-\[cidoc:P129 is subject of]-(cidoc:E5 Event)-\[cidoc:P20 had specific purpose]-(cidoc:E65 Creation)-\[cidoc:P94 has created]-(cidoc:E28 Conceptual Object)-\[cidoc:P108 has produced (was produced by)]-(cidoc:E22 Human-Made Object)-\[cidoc:P1 is identified by (identifies)]-(cidoc:E41 Appellation)                   |
| panel    | (type)                      | (Persoon)-\[wordtHerdachtIn]-(Herdenking)-\[heeftVeruiterlijkingIn]-(Object)-\[isOnderdeelVan]-(Object)-\[heeftType]-(Type) | (oslo:Persoon)-\[cidoc:P129 is subject of]-(cidoc:E5 Event)-\[cidoc:P20 had specific purpose]-(cidoc:E65 Creation)-\[cidoc:P94 has created]-(cidoc:E28 Conceptual Object)-\[cidoc:P108 has produced (was produced by)]-(cidoc:E22 Human-Made Object)-\[P46 is composed of]-(E22 Human-Made Object)-\[cidoc:P2 has type]-(cidoc:E55 Type) |

**JSON-LD sample**

```
{
  "@type": "Persoon",
  "was onderwerp van": {
    "@type": "Evenement",
    "had een specifiek doel": {
      "@type": "Creatie",
      "heeft gecreëerd": {
        "@type": "Conceptueel object",
        "heeft geproduceerd": {
          "@type": "Mensgemaakt object",
          "is onderdeel van": {
            "@type": "Mensgemaakt object",
            "heeft type": {
              "@type": "String",
              "@value": "Memorial",
              "@language": "en"
            }
            "heeft naam": {
              "@type": "String",
              "@value": "Ypres (Menin Gate) Memorial",
              "@language": "en"
            }
          }
          "heeft naam": {
            "@type": "Concept",
            "heeft naam": {
              "@type": "String",
              "@value": "16B"
            }
          }
        }
      }
    }
  }
}
```

### Begraving



| Veld     | Voorbeeld         | MMP197 pattern                                                                                                                             | OSLO pattern                                                                                                                                                                                                                                                                   |
| -------- | ----------------- | ------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| cemetery | (type)            | (Persoon)-\[wordtHerdachtIn]-(Evenement)-\[heeftVerbandMet]-(Plaats)-\[valtOnder]-(Plaats)-\[heeftType]-(Type)                             | (oslo:Persoon)-\[cidoc:P12 was present at]-(cidoc:E5 Event)-\[cidoc:P7 took place at]-(cidoc:E53 Place)-\[cidoc:P89 falls within]-(cidoc:E53 Place)-\[cidoc:P2 has type]-(cidoc:E55 Type)                                                                                      |
| (naam)   | Tyne Cot Cemetery | (Persoon)-\[wordtHerdachtIn]-(Evenement)-\[heeftVerbandMet]-(Plaats)-\[valtOnder]-(Plaats)-\[heeftNaam]-(Naam)                             | (oslo:Persoon)-\[cidoc:P12 was present at]-(cidoc:E5 Event)-\[cidoc:P7 took place at]-(cidoc:E53 Place)-\[cidoc:P89 falls within]-(cidoc:E53 Place)-\[cidoc:P1 is identified by]-(cidoc:E41 Appellation)                                                                       |
| plot     | (type)            | (Persoon)-\[wordtHerdachtIn]-(Evenement)-\[heeftVerbandMet]-(Plaats)-\[heeftNaam]-(Naam)-\[bestaatUit]-(Identificator)-\[heeftType]-(Type) | (oslo:Persoon)-\[cidoc:P12 was present at]-(cidoc:E5 Event)-\[cidoc:P7 took place at]-(cidoc:E53 Place)-\[cidoc:P1 is identified by]-(E41 Appellation)-\[P106 is composed of]-(E42 Identifier)-\[cidoc:P1 is identified by]-(cidoc:E41 Appellation)                            |
| (naam)   | XIII              | (Persoon)-\[wordtHerdachtIn]-(Evenement)-\[heeftVerbandMet]-(Plaats)-\[heeftNaam]-(Naam)-\[bestaatUit]-(Identificator)-\[heeftType]-(Type) | (oslo:Persoon)-\[cidoc:P12 was present at]-(cidoc:E5 Event)-\[cidoc:P7 took place at]-(cidoc:E53 Place)-\[cidoc:P1 is identified by]-(E41 Appellation)-\[P106 is composed of]-(E42 Identifier)-\[P2 has type]-(E55 Type)                                                       |
| row      | (type)            | (Persoon)-\[wordtHerdachtIn]-(Evenement)-\[heeftVerbandMet]-(Plaats)-\[heeftNaam]-(Naam)-\[bestaatUit]-(Identificator)-\[heeftType]-(Type) | (oslo:Persoon)-\[cidoc:P12 was present at]-(cidoc:E5 Event)-\[cidoc:P7 took place at]-(cidoc:E53 Place)-\[cidoc:P1 is identified by]-(E41 Appellation)-\[P106 is composed of]-(E42 Identifier)-\[cidoc:P1 is identified by]-(cidoc:E41 Appellation)                            |
| (naam)   | G                 | (Persoon)-\[wordtHerdachtIn]-(Evenement)-\[heeftVerbandMet]-(Ding)-\[IsOnderdeelVan]-(Ding)-\[heeftNaam]-(Naam)-\[heeftTaal]-(Taal)        | (oslo:Persoon)-\[cidoc:P129 is subject of]-(cidoc:E5 Event)-\[cidoc:P12 occurred in the presence of]-(cidoc:E22 Human-Made Object)-\[cidoc:P46 is composed of (forms part of)]-(cidoc:E22 Human-Made Object)-\[cidoc:P1 is identified by (identifies)]-(cidoc:E41 Appellation) |
| grave    | (type)            | (Persoon)-\[wordtHerdachtIn]-(Evenement)-\[heeftVerbandMet]-(Ding)-\[heeftType]-(Type)-\[heeftNaam]-(Naam)-\[heeftTaal]-(Taal)             | (oslo:Persoon)-\[cidoc:P129 is subject of]-(cidoc:E5 Event)-\[cidoc:P12 occurred in the presence of]-(cidoc:E22 Human-Made Object)-\[cidoc:P2 has type (is type of)]-(cidoc:E55 Type)-\[cidoc:P1 is identified by (identifies)]-(cidoc:E41 Appellation)                        |
| (naam)   | 6                 | (Persoon)-\[wordtHerdachtIn]-(Evenement)-\[heeftVerbandMet]-(Ding)-\[heeftNaam]-(Naam)-\[heeftTaal]-(Taal)                                 | (oslo:Persoon)-\[cidoc:P129 is subject of]-(cidoc:E5 Event)-\[cidoc:P12 occurred in the presence of]-(cidoc:E22 Human-Made Object)-\[cidoc:P1 is identified by (identifies)]-(cidoc:E41 Appellation)                                                                           |

**JSON-LD sample**

```
{
  "@type": "Persoon",
  "was aanwezig bij": {
    "@type": "Evenement",
    "heeft type": "Begraving",
    "vond plaats op": {
      "@type": "Plaats",
      "heeft type": {
       "@type": "Concept",
        "heeft naam": {
          "@type": "String",
          "@value": "Begraafplaats",
          "@language": "nl"
        }
      }
       "heeft naam": {
        "@type": "Concept",
        "heeft naam": {
          "@type": "String",
          "@value": "Tyne Cot Cemetery",
          "@language": "en"
        }
      }
      
        "@type": "Graf",
        "wordt geïdentificeerd door": {
          "@type": "Identificatienummer",
          "is samengesteld uit": [
            {
              "@type": "Concept",
              "heeft naam": {
                "@type": "String",
                "@value": "Plot",
                "@language": "en"
              },
              "wordt geïdentificeerd door": {
                "@type": "String",
                "@value": "XXII"
              }
            },
            {
              "@type": "Concept",
              "heeft naam": {
                "@type": "String",
                "@value": "Row",
                "@language": "en"
              },
              "wordt geïdentificeerd door": {
                "@type": "String",
                "@value": "G"
              }
            },
            {
              "@type": "Concept",
              "heeft naam": {
                "@type": "String",
                "@value": "Grave",
                "@language": "en"
              },
              "wordt geïdentificeerd door": {
                "@type": "String",
                "@value": "2"
              }
            }
          ]
        }
      }
    }
  }
}
```





