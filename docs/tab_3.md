## Aantal voorkomens ##

In de volgende tabel staan de kwaliteitsmaatstaven “Aantal voorkomens”, in hoeverre zijn de relaties tussen concepten consistent. 
Als een kwaliteitsmaatstaf niet is ingevuld, dan is de relatie niet verplicht in de conformiteitsklasse.
In databases voor Stedelijk Water Systemen is de netwerkdefinitie belangrijk, in de conformiteitsklasse MdsPlan wordt hierop gecontroleerd.

### Legenda: Kwaliteit aantal voorkomens ###

Kwaliteitsmaatstaf | Code | Omschrijving
-------------------|------|-------------
laag               | <strong style="color:green">L</strong> | De kwaliteit is niet of nauwelijks van invloed
Neutraal           | **N**                              | De kwaliteit is van invloed
Hoog               | <strong style="color:red">H</strong>   | De kwaliteit is van doorslaggevend belang

### Maatstaven: Kwaliteit aantal voorkomens ###

Subject                | Soort relatie    | Object                  | Aantal | MdsPlan | MdsProj | Hyd
-----------------------|------------------|-------------------------|-----|----|----
Leidingoriëntatie      | heeft als deel   | Beginpunt               | 1      | <strong style="color:red">H</strong>   |  <strong style="color:red">H</strong>   |  <strong style="color:red">H</strong>
Leidingoriëntatie      | heeft als deel   | Eindpunt                | 1      | <strong style="color:red">H</strong>   |  <strong style="color:red">H</strong>   |  <strong style="color:red">H</strong>
Kolkaansluiting        | heeft als deel   | Kolk                    | 1      | <strong style="color:red">H</strong>   |  <strong style="color:green">L</strong> |
Vrijverval rioolstelsel | heeft als deel  | Rioolput                | 1-n    | <strong style="color:red">H</strong>   |  <strong style="color:green">L</strong> |  <strong style="color:red">H</strong>
Vrijverval rioolstelsel | heeft als deel  | Vrijverval rioolleiding | 1-n    | <strong style="color:red">H</strong>   |  <strong style="color:green">L</strong> |  <strong style="color:red">H</strong>
Gescheiden stelsel     | heeft als deel   | Hemelwaterstelsel       | 1      | <strong style="color:green">L</strong> |  <strong style="color:green">L</strong> |  <strong style="color:red">H</strong>
Gescheiden stelsel     | heeft als deel   | Vuilwaterstelsel        | 1      | <strong style="color:green">L</strong> |  <strong style="color:green">L</strong> |  <strong style="color:red">H</strong>
Beginpunt leiding      | heeft verbinding | Put                     | 1      | <strong style="color:red">H</strong>   |                                     |  <strong style="color:red">H</strong> 
Eindpunt leiding       | heeft verbinding | Put                     | 1      | <strong style="color:red">H</strong>   |                                     |  <strong style="color:red">H</strong>
