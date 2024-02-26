# Aandachtspunten bij export van GWSW.orox bestand #

Deze analyse is gebaseerd op:
* de verslaggeving van Diet van Wendel (mailing dd najaar 2017) 
* de verslaggeving van Gwendolijn Vugs (notitie dd 20180124, kenmerk N002-1260650GBV-V01-hgm-NL)
* de meldingen van de GWSW Adviseurs (vanaf februari 2018 tot heden)

## Tips voor leveranciers: ##

* In het OroX-bestand de gestapelde kenmerken "unblanken" (geef ze een URI). Dan wordt SHACL rapport beter bruikbaar, de focusNode is herleidbaar (20240226/mv).
* In het OroX-bestand bij relining de begindatum-lining meegeven, niet de begindatum-leiding aanpassen (20240226/mv).
* In het OroX-bestand ook bij putten (niet alleen bij leidingen) het stelsel benoemen (gwsw:isPartOf) (case Heusden, Almere, ...) (20240209/mv).
* Verduidelijk de handelingen voor de exportfunctie van GWSW.orox zodat de juiste omzetting van alle gegevens uit de native-database geborgd is.
* Geef in een logbestand op heldere wijze aan welke gegevens zijn omgezet en welke aannames daarbij zijn gedaan. Anders blijven ook automatische "verbeteringen" verborgen.
* Beperk de native database gaandeweg steeds meer conform de GWSW ontologie, begin bijvoorbeeld met voorgeschreven stelseltypes, puttypes, leidingtypes.
- Hulppunt als puttype op termijn verwijderen (<span style="color:red">Obsurv</span>)
- Randvoorziening specificeren naar bijvoorbeeld Lamellenfilter, Retentievoorziening (<span style="color:red">Obsurv</span>)
- MechanischRioolstelsel, VrijvervalRioolleiding en Deksel specificeren naar bijvoorbeeld Drukriolering enzovoort. (<span style="color:red">Kikker</span>)
* Neem ontbrekende kenmerken niet mee in het GWSW.orox bestand, ook niet zonder inhoud. De relatie gwsw:hasAspect niet opnemen. (<span style="color:red">Kikker</span>)
* Neem puttypes zonder onderscheidende functie op als extra typering (maak ze "multiparent"). Bijvoorbeeld een blinde put is zowel een type gwsw:Inspectieput als gwsw:BlindePut. Idem voor bijvoorbeeld verdekte put. (<span style="color:red">Obsurv, Kikker</span>)
* Typeer onbekende objectsoorten altijd zo globaal mogelijk, bijvoorbeeld puttype "onbekend" omzetten naar gwsw:Rioolput ipv gwsw:Inspectieput. Dan signaleert de nulmeting het onbekende (te globale) type.
* Neem uitgevoerde maatregelen zoals gwsw:VisueelInspecterenVrijvervalLeiding correct mee in de orox-export. De maatregel heeft de relatie gwsw:hasInput met het object, zie de beschrijving van GWSW.orox. (<span style="color:red">Kikker</span>: "gwsw:hasInput" ontbreekt, alle maatregelen zijn "inspectie") (<span style="color:red">Obsurv</span>: maatregelen ontbreken nog) (melding Leendert, 20180702)
* Verwijder de spatie uit het top-concept "Stedelijk gebied" in GWSW.orox versie 1.4, wordt StedelijkGebied. Nog mooier is Rioleringsgebied, heeft dan als deel één óf meer Rioolstelsels. (<span style="color:red">Kikker</span>, diverse cases, meldingen in sep 2018)
* Prefixes in GWSW.orox versie 1.4, gebruik gwsw: voor gwsw-concepten, gebruik : (blank) voor gemeente-concepten (<span style="color:red">Kikker</span>, diverse cases, meldingen in sep 2018) 
* Lining komt niet mee in .orox bestand (<span style="color:red">Kikker</span>, case Haarlemmermeer, melding Rob, 20180910). Lining kan met de relatie "hasPart" aan de leiding worden gekoppeld.
* Ook grote GML-linestring records (met veel punten) toestaan, breekt nu af op 24000 karakters (<span style="color:red">Kikker</span>, case HHNK_Persleidingen, 20180911)
* Denk aan notatie van quotes in een string-literal, "Naam "met quotes" " kan niet, "Naam \\"met quotes\\" " kan wel (<span style="color:red">Kikker</span>, case HHNK_Persleidingen, 20180911).

## Tips voor gegevensbeheerders/adviseurs: ##
* Hanteer, indien het beheersysteem dit al niet verplicht stelt, alleen de GWSW objecttypes. Vooral belangrijk voor de soorten Stelsel, Put en Leiding.
* Toets de vulling van de kenmerken aan de voorwaarden van de conformiteitsklassen (verplichte vulling, grenswaarden)
* Vermijd typeringen zoals "onbekend", vul aan op basis van revisies of inspecties (<span style="color:red">Kikker</span>)
* Vermijd typeringen zoals "hulppunt", specificeer naar bijvoorbeeld t-stuk, ontstoppingsstuk (<span style="color:red">Obsurv</span>)
* Stem af met de leveranciers hoe speciale constructie conform GWSW beschreven dienen te worden (bijvoorbeeld "doorlaat" in <span style="color:red">Obsurv</span> (case Zwolle) of "spindelschuif" in <span style="color:red">Kikker</span> (melding Jafeth, 20180713)
