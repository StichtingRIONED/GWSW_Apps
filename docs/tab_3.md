## Aantal voorkomens ##

In de volgende tabel staan de kwaliteitsmaatstaven “Aantal voorkomens”, in hoeverre zijn de relaties tussen concepten consistent. 
Als een kwaliteitsmaatstaf niet is ingevuld, dan is de relatie niet verplicht in de conformiteitsklasse.
In databases voor Stedelijk Water Systemen is de netwerkdefinitie belangrijk, in de conformiteitsklasse MdsPlan wordt hierop gecontroleerd.

### Legenda: Kwaliteit aantal voorkomens ###

Kwaliteitsmaatstaf | Code    | Omschrijving
-------------------|---------|-------------
laag               | <span style="color:green">L</span> | De kwaliteit is niet of nauwelijks van invloed
Neutraal           | **N**                              | De kwaliteit is van invloed
Hoog               | <span style="color:red">H</span>   | De kwaliteit is van doorslaggevend belang

### Maatstaven: Kwaliteit aantal voorkomens ###

Subject                | Soort relatie    | Object                  | Aantal | MdsPlan | MdsProj
-----------------------|------------------|-------------------------|--------|---------|--------
Leidingoriëntatie      | heeft als deel   | Beginpunt               | 1      | <span style="color:red">H</span>   |  <span style="color:red">H</span>
Leidingoriëntatie      | heeft als deel   | Eindpunt                | 1      | <span style="color:red">H</span>   |  <span style="color:red">H</span>
Kolkaansluiting        | heeft als deel   | Kolk                    | 1      | <span style="color:red">H</span>   |  <span style="color:green">L</span>
Vrijverval rioolstelsel | heeft als deel  | Rioolput                | 1-n    | <span style="color:red">H</span>   |  <span style="color:green">L</span>
Vrijverval rioolstelsel | heeft als deel  | Vrijverval rioolleiding | 1-n    | <span style="color:red">H</span>   |  <span style="color:green">L</span>
Gescheiden stelsel     | heeft als deel   | Hemelwaterstelsel       | 1      | <span style="color:green">L</span> |  <span style="color:green">L</span>
Gescheiden stelsel     | heeft als deel   | Vuilwaterstelsel        | 1      | <span style="color:green">L</span> |  <span style="color:green">L</span>
Beginpunt leiding      | heeft verbinding | Put                     | 1      | <span style="color:red">H</span>
Eindpunt leiding       | heeft verbinding | Put                     | 1      | <span style="color:red">H</span>
