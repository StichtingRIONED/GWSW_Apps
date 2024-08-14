# Werking HydX-download van GWSW-Apps

De basis voor deze applicaties vormen queries op https://github.com/StichtingRIONED/gwsw_queries/blob/main/apps/Hyd . 
Deze queries lezen de relevante gegevens uit de GWSW-Datasets. 
Om deze queries te kunnen lezen is enige kennis van SPARQL noodzakelijk.
Inzicht in de werking van deze queries is noodzakelijk om de werking van de HydX-download in de basis te begrijpen. 
Dit document licht alleen de aanvullende bewerkingen van de query-resultaten toe.

## Gegevens knooppunten
Zie ook de query op https://github.com/StichtingRIONED/gwsw_queries/blob/main/apps/Hyd/Hyd_Knooppunt.rq 

Compartimenten worden als knooppunten meegenomen, voor elk compartiment in de dataset zijn gegevens zoals afmetingen nodig.

De volgende gegevens van compartimenten worden zo nodig wel overgenomen van het compositieopbject (de put of het bouwwerk):
- Materiaal
- Maaiveldschematisering
- Bergend oppervlak
- Hoogte (vanaf versie 1.6 bestaat het kenmerk HoogteCompartiment, dat gegeven wordt bij voorkeur gebruikt)
