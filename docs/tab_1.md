## Bladerobjecten ##
In tabel 1 staan de kwaliteitsmaatstaven “Typering objecten” per conformiteitsklasse. Als een kwaliteitsmaatstaf niet is ingevuld, dan komt het concept niet voor in de desbetreffende conformiteitsklasse.

Legenda kwaliteitsmaatstaven in Tabel 1

Kwaliteitsmaatstaf     | Code    | Omschrijving
-----------------------|---------|-------------
Fout                   | F       | Het object is onvoldoende getypeerd
Goed                   | G       | De typering van het object is voldoende

Tabel 1
Naam concept                       | Supertype                    | MdsPlan | MdsProj
-----------------------------------|------------------------------|---------|--------
Stelsel                            | Fysiek object                | <span style="color:red">F</span>    | <span style="color:red">F</span> 
Rioolstelsel                       | Stelsel                      | <span style="color:red">F</span>    | <span style="color:red">F</span> 
Vrijverval rioolstelsel            | Rioolstelsel                 | <span style="color:red">F</span>    | <span style="color:red">F</span> 
Gemengd stelsel                    | Vrijverval rioolstelsel      | <span style="color:green">G</span>  | <span style="color:green">G</span> 
Verbeterd gemengd stelsel          | Gemengd stelsel              | <span style="color:green">G</span>  | <span style="color:green">G</span> 
Hemelwaterstelsel                  | Vrijverval rioolstelsel      | <span style="color:green">G</span>  | <span style="color:green">G</span> 
Vuilwaterstelsel                   | Vrijverval rioolstelsel      | <span style="color:green">G</span>  | <span style="color:green">G</span> 
Onderbemaling                      | Vrijverval rioolstelsel      | <span style="color:red">F</span>    | <span style="color:red">F</span> 
Mechanisch rioolstelsel            | Rioolstelsel                 | <span style="color:red">F</span>    | <span style="color:red">F</span> 
Drukriolering                      | Mechanisch rioolstelsel      | <span style="color:green">G</span>  | <span style="color:green">G</span> 
Vacuümriolering                    | Mechanisch rioolstelsel      | <span style="color:green">G</span>  | <span style="color:green">G</span> 
Mechanisch drainagestelsel         | Drainagestelsel
Vrijverval drainagestelsel         | Drainagestelsel 
Transportstelsel                   | Stelsel                      | <span style="color:red">F</span>    | <span style="color:red">F</span> 
Persleidingsysteem                 | Transportstelsel             | <span style="color:green">G</span>  | <span style="color:green">G</span> 
Vrijverval transportstelsel        | Transportstelsel             | <span style="color:green">G</span>  | <span style="color:green">G</span> 
Put                                | Fysiek object                | <span style="color:red">F</span>    | <span style="color:red">F</span> 
Aansluitput                        | Put 
Drainageput                        | Put 
Filterput                          | Put 
Slokop                             | Put 
Beerput                            | Put                          | <span style="color:green">G</span>  | <span style="color:green">G</span> 
Infiltratieput                     | Put 
Kolk                               | Put                          | <span style="color:green">G</span>  | <span style="color:green">G</span> 
Trottoirkolk                       | Kolk                         | <span style="color:green">G</span>  | <span style="color:green">G</span> 
Straatkolk                         | Kolk                         | <span style="color:green">G</span>  | <span style="color:green">G</span> 
Infiltratiekolk                    | Kolk                         | <span style="color:green">G</span>  | <span style="color:green">G</span> 
Gecombineerde straat- trottoirkolk | Kolk                         | <span style="color:green">G</span>  | <span style="color:green">G</span> 
Bijzondere putconstructie          | Rioolput                     | <span style="color:green">G</span>  | <span style="color:green">G</span> 
Aansluitput                        | Put 
Doorspoelput                       | Rioolput                     | <span style="color:green">G</span>  | <span style="color:green">G</span> 
Inspectieput                       | Rioolput                     | <span style="color:green">G</span>  | <span style="color:green">G</span> 
Kruisingsput                       | Rioolput                     | <span style="color:green">G</span>  | <span style="color:green">G</span> 
Zinkerput                          | Rioolput 
Stuwput                            | Rioolput                     | <span style="color:green">G</span>  | <span style="color:green">G</span> 
Lozingsput                         | Rioolput                     | <span style="color:green">G</span>  | <span style="color:green">G</span> 
Overstortput                       | Rioolput                     | <span style="color:red">F</span>    | <span style="color:green">G</span> 
Externe overstortput               | Overstortput                 | <span style="color:green">G</span>  | <span style="color:green">G</span> 
Interne overstortput               | Overstortput                 | <span style="color:green">G</span>  | <span style="color:green">G</span> 
Verdekte put                       | Rioolput                     | <span style="color:green">G</span> 
Pompput                            | Rioolput                     | <span style="color:red">F</span>    | <span style="color:red">F</span> 
Pompunit                           | Pompput                      | <span style="color:green">G</span>  | <span style="color:green">G</span> 
Vacuümpompstation                  | Pompput                      | <span style="color:green">G</span>  | <span style="color:green">G</span> 
Leiding                            | Fysiek object                | <span style="color:red">F</span>    | <span style="color:red">F</span> 
Drain                              | Leiding                      | <span style="color:green">G</span>  | <span style="color:green">G</span> 
Duiker                             | Leiding 
Mantelbuis                         | Leiding 
Aansluitleiding                    | Rioolleiding                 | <span style="color:green">G</span>  | <span style="color:green">G</span> 
Kolkaansluitleiding                | Aansluitleiding              | <span style="color:green">G</span>  | <span style="color:green">G</span> 
Perceelaansluitleiding             | Aansluitleiding              | <span style="color:green">G</span>  | <span style="color:green">G</span> 
Mechanische rioolleiding           | Rioolleiding                 | <span style="color:red">F</span>    | <span style="color:red">F</span> 
Drukleiding                        | Mechanische rioolleiding     | <span style="color:green">G</span>  | <span style="color:green">G</span> 
Vacuümleiding                      | Mechanische rioolleiding     | <span style="color:green">G</span>  | <span style="color:green">G</span> 
Vrijverval rioolleiding            | Leiding                      | <span style="color:red">F</span>    | <span style="color:green">G</span> 
Bergbezinkleiding                  | Vrijverval rioolleiding      | <span style="color:green">G</span>  | <span style="color:green">G</span> 
Bergingsleiding                    | Vrijverval rioolleiding      | <span style="color:green">G</span>  | <span style="color:green">G</span> 
Gemengd riool                      | Vrijverval rioolleiding      | <span style="color:green">G</span>  | <span style="color:green">G</span> 
Hemelwaterriool                    | Vrijverval rioolleiding      | <span style="color:green">G</span>  | <span style="color:green">G</span> 
Infiltratieriool                   | Vrijverval rioolleiding      | <span style="color:green">G</span>  | <span style="color:green">G</span> 
Overstortleiding                   | Vrijverval rioolleiding      | <span style="color:green">G</span>  | <span style="color:green">G</span> 
Stuwrioolleiding                   | Vrijverval rioolleiding      | <span style="color:green">G</span>  | <span style="color:green">G</span> 
Vuilwaterriool                     | Vrijverval rioolleiding      | <span style="color:green">G</span>  | <span style="color:green">G</span> 
Zinker                             | Vrijverval rioolleiding      | <span style="color:green">G</span>  | <span style="color:green">G</span> 
Transportleiding                   | Leiding                      | <span style="color:red">F</span>    | <span style="color:red">F</span> 
Mechanische transportleiding       | Transportleiding             | <span style="color:red">F</span>    | <span style="color:red">F</span> 
Persleiding                        | Mechanische transportleiding | <span style="color:green">G</span>  | <span style="color:green">G</span> 
Spoelleiding                       | Mechanische transportleiding | <span style="color:green">G</span>  | <span style="color:green">G</span> 
Vrijverval transportleiding        | Transportleiding             | <span style="color:red">F</span>    | <span style="color:red">F</span> 
Transportrioolleiding              | Vrijverval transportleiding  | <span style="color:green">G</span>  | <span style="color:green">G</span> 
Goot                               | Open leiding 
Reservoir                          | Fysiek object                | <span style="color:red">F</span>    | <span style="color:red">F</span> 
Bergbezinkbassin                   | Reservoir                    | <span style="color:green">G</span>  | <span style="color:green">G</span> 
Bergingsbassin                     | Reservoir                    | <span style="color:green">G</span>  | <span style="color:green">G</span> 
Bergingsvijver                     | Reservoir                    | <span style="color:green">G</span>  | <span style="color:green">G</span> 
Bezinkbassin                       | Reservoir                    | <span style="color:green">G</span>  | <span style="color:green">G</span> 
Infiltratiereservoir               | Reservoir                    | <span style="color:red">F</span>    | <span style="color:red">F</span> 
Infiltratiebassin                  | Infiltratiereservoir         | <span style="color:green">G</span>  | <span style="color:green">G</span> 
Infiltratiegreppel                 | Infiltratiereservoir 
Infiltratieveld                    | Infiltratiereservoir 
Wadi                               | Infiltratiereservoir         | <span style="color:green">G</span>  | <span style="color:green">G</span> 
Vacuümopslagtank                   | Reservoir                    | <span style="color:green">G</span> 
Zuiveringsreservoir                | Reservoir                    | <span style="color:red">F</span>    | <span style="color:red">F</span> 
Helofytenfilter                    | Zuiveringsreservoir          | <span style="color:green">G</span>  | <span style="color:green">G</span> 
IBA                                | Zuiveringsreservoir          | <span style="color:green">G</span>  | <span style="color:green">G</span> 
Septictank                         | Zuiveringsreservoir          | <span style="color:green">G</span>  | <span style="color:green">G</span> 
