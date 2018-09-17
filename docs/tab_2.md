## Kenmerken ##
In tabel 2 staan de kwaliteitsmaatstaven voor de kenmerken. Als een kwaliteitsmaatstaf niet is ingevuld, dan is het kenmerk niet verplicht in de conformiteitsklasse. 

### Legenda kwaliteitsmaatstaven tabellen 2 en 3 ###

Kwaliteitsmaatstaf | Code    | Omschrijving
-------------------|---------|-------------
laag               | <span style="color:green">L</span> | De kwaliteit is niet of nauwelijks van invloed
Neutraal           | **N**                              | De kwaliteit is van invloed
Hoog               | <span style="color:red">H</span>   | De kwaliteit is van doorslaggevend belang

### Tabel 2: Kwaliteitsmaatstaf en voorkomens kenmerken ###

Concept       | Kenmerk                             | Nauwkeurigheid               |              | MdsPlan | MdsProj
--------------|-------------------------------------|------------------------------|--------------|---------|----------
Kenmerk       | Wijze van inwinning                 | Waarde in collectie
Kenmerk       | Datum inwinning                     |                              | Datatype
Lining        | Soort lining                        | Waarde in collectie          |
Lining        | Materiaal lining                    | Waarde in collectie          |
Put           | Breedte put                         | 300 <= Waarde <= 4000 mm     | Datatype     | **N**       | **N** 
Put           | Hoogte put                          | 500 <= Waarde <= 4000 mm     | Datatype     | **N** 
Deksel        | Vorm deksel                         | Waarde in collectie           
Deksel        | Materiaal deksel                    | Waarde in collectie
Deksel        | Dekseloriëntatie (niveau)           | -20 <= Waarde <= 300 m       | Datatype     | **N** 
Leiding       | Hoogte leiding                      | 63 <= Waarde <= 4000 mm      | Datatype     | **N**       | **N** 
Leiding       | Breedte leiding                     | 63 <= Waarde <= 4000 mm      | Datatype     | **N**       | **N** 
Put/Lei       | Einddatum                           |                              | Datatype
Put/Lei       | Begindatum                          |                              | Datatype     | <span style="color:green">L</span> | <span style="color:green">L</span> 
Leiding       | Wanddikte                           |                              | Datatype
Put           | Lengte putdeel                      |                              | Datatype
Deksel        | Breedte deksel                      |                              | Datatype
Deksel        | Lengte deksel                       |                              | Datatype
Put           | Materiaal put                       | Waarde in collectie          |              | <span style="color:red">H</span>   | <span style="color:red">H</span> 
Put           | Lengte put                          | 300 <= Waarde <= 4000 mm     | Datatype     | **N**       | **N** 
Put/Lei       | Datum maatregel                     |                              | Datatype
Leiding       | Lengte leiding                      | 1 <= Waarde <= 75 m          | Datatype     | <span style="color:red">H</span>   | <span style="color:red">H</span> 
Leiding       | Lengte buisdeel                     |                              | Datatype
Put           | Maaiveld put                        | -20 <= Waarde <= 300 m       | Datatype     | **N** 
Leiding       | Maaiveld beginpunt leiding          | -20 <= Waarde <= 300 m       | Datatype
Leiding       | Maaiveld eindpunt leiding           | -20 <= Waarde <= 300 m       | Datatype
Put           | Putoriëntatie / Positie / X         | -7000 <= Waarde <= 300000 m  | Datatype     | **N**       | **N** 
Put           | Putoriëntatie / Positie / Y         | 289000 <= Waarde <= 629000 m
Put           | Z-coördinaat                        | -20 <= Waarde <= 300 m       | Datatype
Project       | Projectreferentie                   |                              | Datatype     | <span style="color:red">H</span>   | <span style="color:red">H</span> 
              | opdrachtgever                       |                                                                                                                                                                                       
Project       | Projectreferentie                   |                              | Datatype     | <span style="color:red">H</span>   | <span style="color:red">H</span> 
              | opdrachtnemer                       |                                                                                                                                                                                       
Leiding       | Leidingoriëntatie                   |                              | Datatype     | <span style="color:red">H</span>   | <span style="color:red">H</span> 
              | Beginpunt / Positie Beginpunt       |                                                                                                
			  | Eindpunt / Positie Eindpunt         |                                                                                              
Leiding       | B.o.b. beginpunt leiding            | -20 <= Waarde <= 300 m       | Datatype     | <span style="color:red">H</span>   | <span style="color:red">H</span> 
Leiding       | B.o.b. eindpunt leiding             | -20 <= Waarde <= 300 m       | Datatype     | <span style="color:red">H</span>   | <span style="color:red">H</span> 
Leiding       | Materiaal leiding                   | Waarde in collectie          |              | <span style="color:red">H</span>   | <span style="color:red">H</span> 
Leiding       | Vorm leiding                        | Waarde in collectie          |              | **N**       | **N** 
Leiding       | Verhardingstype                     | Waarde in collectie
Put           | Vorm put                            | Waarde in collectie          |              | **N**       | **N** 
Leiding       | Verbindingstype                     | Waarde in collectie



In tabel 3 staan de kwaliteitsmaatstaven “Consistentie” (over de relaties tussen instanties). Als een kwaliteitsmaatstaf niet is ingevuld, dan is de relatie niet verplicht in de conformiteitsklasse.
In databases voor Stedelijk Water Systemen is de netwerkdefinitie belangrijk, in de conformiteitsklasse MdsPlan wordt hierop gecontroleerd.

### Tabel 3: Consistentie - verplichte voorkomens ###

Subject                | Soort relatie    | Object                  | Aantal | MdsPlan | MdsProj
-----------------------|------------------|-------------------------|--------|---------|--------
Leidingoriëntatie      | heeft als deel   | Beginpunt               | 1      | <span style="color:red">H</span>   |  <span style="color:red">H</span>
Leidingoriëntatie      | heeft als deel   | Eindpunt                | 1      | <span style="color:red">H</span>   |  <span style="color:red">H</span>
Kolkaansluiting        | heeft als deel   | Kolk                    | 1      | <span style="color:red">H</span>   |  <span style="color:green">L</span>
Vrijverval rioolstelsel | heeft als deel   | Rioolput                | 1-n    | <span style="color:red">H</span>   |  <span style="color:green">L</span>
Vrijverval rioolstelsel | heeft als deel   | Vrijverval rioolleiding | 1-n    | <span style="color:red">H</span>   |  <span style="color:green">L</span>
Gescheiden stelsel     | heeft als deel   | Hemelwaterstelsel       | 1      | <span style="color:green">L</span> |  <span style="color:green">L</span>
Gescheiden stelsel     | heeft als deel   | Vuilwaterstelsel        | 1      | <span style="color:green">L</span> |  <span style="color:green">L</span>
Beginpunt leiding      | heeft verbinding | Put                     | 1      | <span style="color:red">H</span>
Eindpunt leiding       | heeft verbinding | Put                     | 1      | <span style="color:red">H</span>
