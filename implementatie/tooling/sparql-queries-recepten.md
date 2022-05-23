---
description: recepten voor het bevragen van OSLO datasets;
---

# SPARQL queries (recepten)

## SPARQL Queries ikv. Cultural Data Lab (CoGhent)

### zoeken op substring in een titel.&#x20;

onderstaande query bevraagt de event stream van het Design Museum Gent voor het ophalen van alle objecten waar NOVA voorkomt als deel van de titel.&#x20;

```
PREFIX cidoc: <http://www.cidoc-crm.org/cidoc-crm/>
SELECT DISTINCT ?title ?beschrijving FROM <http://stad.gent/ldes/dmg> 
WHERE { 
  ?object cidoc:P102_has_title ?title.  # haal alle objecten op met waarde titel.
  FILTER (regex(?title, "NOVA", "i")) # filter in deze titels naar titels met substring NOVA.
  ?object cidoc:P3_has_note ?beschrijving # haal de beschrijving op van deze werken. 
} 

LIMIT 100
```



