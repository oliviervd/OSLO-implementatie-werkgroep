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

{% hint style="info" %}
live demo: [Comunica](http://query.linkeddatafragments.org/#datasources=https%3A%2F%2Flodi.ilabt.imec.be%2Fsparql%2Fgent\&query=PREFIX%20cidoc%3A%20%3Chttp%3A%2F%2Fwww.cidoc-crm.org%2Fcidoc-crm%2F%3E%0ASELECT%20DISTINCT%20%3Ftitle%20%3Fbeschrijving%20FROM%20%3Chttp%3A%2F%2Fstad.gent%2Fldes%2Fdmg%3E%20%0AWHERE%20%7B%20%0A%20%20%3Fobject%20cidoc%3AP102\_has\_title%20%3Ftitle.%20%0A%20%20FILTER%20\(regex\(%3Ftitle%2C%20%22NOVA%22%2C%20%22i%22\)\).%0A%20%20%3Fobject%20cidoc%3AP3\_has\_note%20%3Fbeschrijving%20%0A%7D%20%0A%0ALIMIT%20100\&httpProxy=http%3A%2F%2Fproxy.linkeddatafragments.org%2F)&#x20;

live demo: [Virtuoso](https://stad.gent/sparql?default-graph-uri=\&query=PREFIX+cidoc%3A+%3Chttp%3A%2F%2Fwww.cidoc-crm.org%2Fcidoc-crm%2F%3E%0D%0ASELECT+DISTINCT+%3Ftitle+%3Fbeschrijving+FROM+%3Chttp%3A%2F%2Fstad.gent%2Fldes%2Fdmg%3E+%0D%0AWHERE+%7B+%0D%0A++%3Fobject+cidoc%3AP102\_has\_title+%3Ftitle.+%0D%0A++FILTER+%28regex%28%3Ftitle%2C+%22NOVA%22%2C+%22i%22%29%29.%0D%0A++%3Fobject+cidoc%3AP3\_has\_note+%3Fbeschrijving+%0D%0A%7D+%0D%0A%0D%0ALIMIT+100\&format=text%2Fhtml\&timeout=0\&debug=on) (triple store stad Gent)
{% endhint %}

