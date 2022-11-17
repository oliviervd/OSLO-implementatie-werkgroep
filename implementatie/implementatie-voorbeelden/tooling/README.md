---
description: samenvatting van gebruikte tools voor het implementeren van OSLO
---

# Tooling



volgende pagina's bieden een overzicht van de verschillende mogelijke technologieen die gebruikt kunnen worden voor het implementeren van OSLO. Hierbij vertrekt het vanuit bestaande implementatiecases in het Vlaamse Erfgoedveld.&#x20;

* _Collectie van de Gentenaar_ (Stad Gent); [implementatie van OSLO via publicatie van Linked Data Event Streams](ldes-linked-data-event-stream.md).&#x20;





toolkit met tools die relevant zijn voor het implementeren van OSLO alsook sommige stappen zoals beschreven in de [strategie](../../).&#x20;

In de systeemarchitectuur van Coghent wordt de collectiedata bij de bron via de legacy API van een collectiebeheersysteem (Adlib) uitgelezen. Een ETL pipeline extraheert elke dag de laatste versie van de data en transcodeert de data aan de hand van een mapping (OSLO) naar linked data en wordt vervolgens in een databank geladen. Op deze databank draait de LDES service waarlangs gebruikers data kunnen opvragen of applicaties kunnen bouwen.
