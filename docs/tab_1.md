## Bladerobjecten ##
In tabel 1 staan de kwaliteitsmaatstaven “Typering objecten” per conformiteitsklasse. Als een kwaliteitsmaatstaf niet is ingevuld, dan komt het concept niet voor in de desbetreffende conformiteitsklasse.

Legenda kwaliteitsmaatstaven in Tabel 1

Kwaliteitsmaatstaf     | Code    | Omschrijving
-----------------------|---------|-------------
Fout                   | F       | Het object is onvoldoende getypeerd
Goed                   | G       | De typering van het object is voldoende

Tabel 1
Naam concept                       | Supertype                    | Kwaliteitsmaatstaf |
                                   |                              | MdsPlan | MdsProj
-----------------------------------|------------------------------|---------|-----------
Stelsel                            | Fysiek object                | F  | F
Rioolstelsel                       | Stelsel                      | F  | F
Vrijverval rioolstelsel            | Rioolstelsel                 | F  | F
Gemengd stelsel                    | Vrijverval rioolstelsel      | G  | G
Verbeterd gemengd stelsel          | Gemengd stelsel              | G  | G
Hemelwaterstelsel                  | Vrijverval rioolstelsel      | G  | G
Vuilwaterstelsel                   | Vrijverval rioolstelsel      | G  | G
Onderbemaling                      | Vrijverval rioolstelsel      | F  | F
Mechanisch rioolstelsel            | Rioolstelsel                 | F  | F
Drukriolering                      | Mechanisch rioolstelsel      | G  | G
Vacuümriolering                    | Mechanisch rioolstelsel      | G  | G
Mechanisch drainagestelsel         | Drainagestelsel | |
Vrijverval drainagestelsel         | Drainagestelsel | |
Transportstelsel                   | Stelsel                      | F  | F
Persleidingsysteem                 | Transportstelsel             | G  | G
Vrijverval transportstelsel        | Transportstelsel             | G  | G
Put                                | Fysiek object                | F  | F
Aansluitput                        | Put | |
Drainageput                        | Put | |
Filterput                          | Put | |
Slokop                             | Put | |
Beerput                            | Put                          | G  | G
Infiltratieput                     | Put | |
Kolk                               | Put                          | G  | G
Trottoirkolk                       | Kolk                         | G  | G
Straatkolk                         | Kolk                         | G  | G
Infiltratiekolk                    | Kolk                         | G  | G
Gecombineerde straat- trottoirkolk | Kolk                         | G  | G
Bijzondere putconstructie          | Rioolput                     | G  | G
Aansluitput                        | Put | |
Doorspoelput                       | Rioolput                     | G  | G
Inspectieput                       | Rioolput                     | G  | G
Kruisingsput                       | Rioolput                     | G  | G
Zinkerput                          | Rioolput | |
Stuwput                            | Rioolput                     | G  | G
Lozingsput                         | Rioolput                     | G  | G
Overstortput                       | Rioolput                     | F  | G
Externe overstortput               | Overstortput                 | G  | G
Interne overstortput               | Overstortput                 | G  | G
Verdekte put                       | Rioolput                     | G  |
Pompput                            | Rioolput                     | F  | F
Pompunit                           | Pompput                      | G  | G
Vacuümpompstation                  | Pompput                      | G  | G
Leiding                            | Fysiek object                | F  | F
Drain                              | Leiding                      | G  | G
Duiker                             | Leiding | |
Mantelbuis                         | Leiding | |
Aansluitleiding                    | Rioolleiding                 | G  | G
Kolkaansluitleiding                | Aansluitleiding              | G  | G
Perceelaansluitleiding             | Aansluitleiding              | G  | G
Mechanische rioolleiding           | Rioolleiding                 | F  | F
Drukleiding                        | Mechanische rioolleiding     | G  | G
Vacuümleiding                      | Mechanische rioolleiding     | G  | G
Vrijverval rioolleiding            | Leiding                      | F  | G
Bergbezinkleiding                  | Vrijverval rioolleiding      | G  | G
Bergingsleiding                    | Vrijverval rioolleiding      | G  | G
Gemengd riool                      | Vrijverval rioolleiding      | G  | G
Hemelwaterriool                    | Vrijverval rioolleiding      | G  | G
Infiltratieriool                   | Vrijverval rioolleiding      | G  | G
Overstortleiding                   | Vrijverval rioolleiding      | G  | G
Stuwrioolleiding                   | Vrijverval rioolleiding      | G  | G
Vuilwaterriool                     | Vrijverval rioolleiding      | G  | G
Zinker                             | Vrijverval rioolleiding      | G  | G
Transportleiding                   | Leiding                      | F  | F
Mechanische transportleiding       | Transportleiding             | F  | F
Persleiding                        | Mechanische transportleiding | G  | G
Spoelleiding                       | Mechanische transportleiding | G  | G
Vrijverval transportleiding        | Transportleiding             | F  | F
Transportrioolleiding              | Vrijverval transportleiding  | G  | G
Goot                               | Open leiding | |
Reservoir                          | Fysiek object                | F  | F
Bergbezinkbassin                   | Reservoir                    | G  | G
Bergingsbassin                     | Reservoir                    | G  | G
Bergingsvijver                     | Reservoir                    | G  | G
Bezinkbassin                       | Reservoir                    | G  | G
Infiltratiereservoir               | Reservoir                    | F  | F
Infiltratiebassin                  | Infiltratiereservoir         | G  | G
Infiltratiegreppel                 | Infiltratiereservoir | |
Infiltratieveld                    | Infiltratiereservoir | |
Wadi                               | Infiltratiereservoir         | G  | G
Vacuümopslagtank                   | Reservoir                    | G |
Zuiveringsreservoir                | Reservoir                    | F  | F
Helofytenfilter                    | Zuiveringsreservoir          | G  | G
IBA                                | Zuiveringsreservoir          | G  | G
Septictank                         | Zuiveringsreservoir          | G  | G
