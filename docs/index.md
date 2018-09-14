## GWSW ##
Het Gegevenswoordenboek Stedelijk Water (GWSW) is een [ontologie](https://nl.wikipedia.org/wiki/Ontologie_(informatica)), een speciale datastructuur die systemen (stelsels) en processen op het gebied van Stedelijk Water beschrijft. 
Het GWSW is een open datastandaard volgens het linked data principe die door Stichting RIONED namens de sector is ontwikkeld. 
Het is onderdeel van het Semantisch Web en is gemodelleerd in [RDF/RDFS/OWL-2](https://en.wikipedia.org/wiki/Resource_Description_Framework).

## GWSW Apps ##

Deze website geeft toegang tot de github-repository GWSW van Stichting RIONED, dit betreft: 
* De registratie van [verbetervoorstellen en foutmeldingen](https://github.com/StichtingRIONED/GWSW/issues) aangaande GWSW Apps 
* Documentatie van ontwikkeling van (met name) GWSW Apps 
  - [Evaluatie GWSW Apps](#evaluatie-gwsw-apps)
  	- [Analyse van de werking](#analyse-van-de-werking)

## Evaluatie GWSW Apps ##


### GWSW Nulmeting - Analyse van de werking ###

De juiste interpretatie van de nulmeting-resultaten vraagt kennis van het gehele proces. De GWSW Nulmeting dient alleen door daarin getrainde adviseurs uitgevoerd te worden.
Informatie over de GWSW Nulmeting is te vinden in:

* De soortenboom op de websites data.gwsw.nl (de module GWSW Basis) en, voor conformiteitsklasse MdsPlan, data.gwsw.nl/MdsPlan
* Het document GWSW Nulmeting Beschrijving (download op apps.gwsw.nl)
* Het document GWSW.orox Beschrijving (download op apps.gwsw.nl)
* Deze notitie: GWSW Apps Werkdocument. 

#### Aanpak van de analyse (oktober 2017 - januari 2018) ####

**Inrichting conformiteitsklassen**
Op de websites de kwaliteit van de conformiteitsklassen (bijvoorbeeld data.gwsw.nl/MdsPlan) controleren:
* Zijn alle soorten vermeld?
	- Zijn ze niet te globaal?
	- Zijn ze niet te gedetailleerd?
* Zijn alle kenmerken vermeld?
	- Zijn ze terecht verplicht? ("exact = 1")
	- Zijn ze terecht optioneel?

**Document GWSW Nulmeting Beschrijving controleren:**
* Is het leesbaar voor buitenstaanders?
* Is het volledig?

**De rapportage van de nulmetingen (vooralsnog in platte csv-vorm) controleren:**
* Is het leesbaar voor buitenstaanders?
* Staat er voldoende informatie in om conclusies te kunnen trekken?
* Welke vervolgrapportage (met die conclusies) moet er komen?

**Meting gegevenskwaliteit**
* Vul de GWSW Dataset, upload een GWSW.orox export in combinatie met de cfk
* Doe eerst een "quick-scan" met de GWSW Nulmeting. Als er veel onbekende of te globale typeringen zijn, is de overige kwaliteitsmeting niet betrouwbaar. Breng dan eerst de database voor wat betreft de typering op orde. Daarmee voorkom je dat er twee keer een “zwaar” metingtraject wordt doorlopen. (case Tholen)
* Gebruik de GWSW-Geoserver (via het WFS protocol) om de grafische presentatie te vergelijken met die van het Beheersysteem
* Voer de nulmeting uit en herleid de foutmeldingen:
	- Oorzaak in native database? (dus beheersysteem nodig bij de analyse) = signaal naar beheerder
	- Oorzaak in de exportfunctie Orox ? (opbouw/mapping GWSW.orox bestand onvoldoende)  = signaal naar softwareleverancier (altijd via RIONED)
	- Oorzaak in de nulmeting (foute werking) = signaal naar RIONED
	- Oorzaak in de ontologie (GWSW algemeen of de cfk, bijvoorbeeld: bepaalde types ontbreken nog) = signaal naar RIONED

#### Resultaten van de analyse (januari 2018) ####
Deze analyse is gebaseerd op:
* de verslaggeving van Diet van Wendel (mailing dd najaar 2017) 
* de verslaggeving van Gwendolijn Vugs (notitie dd 20180124, kenmerk N002-1260650GBV-V01-hgm-NL)
* de meldingen van de GWSW Adviseurs (vanaf februari 2018 tot heden)

### Aandachtpunten bij export van GWSW.orox bestand ###
Tips voor leveranciers:
* Verduidelijk de handelingen voor de exportfunctie van GWSW.orox zodat de juiste omzetting van alle gegevens uit de native-database geborgd is.
* Geef in een logbestand op heldere wijze aan welke gegevens zijn omgezet en welke aannames daarbij zijn gedaan. Anders blijven ook automatische "verbeteringen" verborgen.
* Beperk de native database gaandeweg steeds meer conform de GWSW ontologie, begin bijvoorbeeld met voorgeschreven stelseltypes, puttypes, leidingtypes.
- Hulppunt als puttype op termijn verwijderen (Obsurv)
- Randvoorziening specificeren naar bijvoorbeeld Lamellenfilter, Retentievoorziening (Obsurv)
- MechanischRioolstelsel, VrijvervalRioolleiding en Deksel specificeren naar bijvoorbeeld Drukriolering enzovoort. (Kikker)
* Neem ontbrekende kenmerken niet mee in het GWSW.orox bestand, ook niet zonder inhoud. De relatie gwsw:hasAspect niet opnemen. (Kikker)
 Neem puttypes zonder onderscheidende functie op als extra typering (maak ze "multiparent"). Bijvoorbeeld een blinde put is zowel een type gwsw:Inspectieput als gwsw:BlindePut. Idem voor bijvoorbeeld verdekte put. (Obsurv, Kikker)
* Typeer onbekende objectsoorten altijd zo globaal mogelijk, bijvoorbeeld puttype "onbekend" omzetten naar gwsw:Rioolput ipv gwsw:Inspectieput. Dan signaleert de nulmeting het onbekende (te globale) type.
* Neem uitgevoerde maatregelen zoals gwsw:VisueelInspecterenVrijvervalLeiding correct mee in de orox-export. De maatregel heeft de relatie gwsw:hasInput met het object, zie de beschrijving van GWSW.orox. (Kikker: "gwsw:hasInput" ontbreekt, alle maatregelen zijn "inspectie") (Obsurv: maatregelen ontbreken nog) (melding Leendert, 20180702)
* Verwijder de spatie uit het top-concept "Stedelijk gebied" in GWSW.orox versie 1.4, wordt StedelijkGebied. Nog mooier is Rioleringsgebied, heeft dan als deel één óf meer Rioolstelsels. (Kikker, diverse cases, meldingen in sep 2018)
* Prefixes in GWSW.orox versie 1.4, gebruik gwsw: voor gwsw-concepten, gebruik : (blank) voor gemeente-concepten (Kikker, diverse cases, meldingen in sep 2018) 
* Lining komt niet mee in .orox bestand (Kikker, case Haarlemmermeer, melding Rob, 20180910). Lining kan met de relatie "hasPart" aan de leiding worden gekoppeld.
* Ook grote GML-linestring records (met veel punten) toestaan, breekt nu af op 24000 karakters (Kikker, case HHNK_Persleidingen, 20180911)
* Denk aan notatie van quotes in een string-literal, "Naam "met quotes" " kan niet, "Naam \"met quotes\" " kan wel (Kikker, case HHNK_Persleidingen, 20180911).
Tips voor gegevensbeheerders/adviseurs:
* Hanteer, indien het beheersysteem dit al niet verplicht stelt, alleen de GWSW objecttypes. Vooral belangrijk voor de soorten Stelsel, Put en Leiding.
* Toets de vulling van de kenmerken aan de voorwaarden van de conformiteitsklassen (verplichte vulling, grenswaarden)
* Vermijd typeringen zoals "onbekend", vul aan op basis van revisies of inspecties (Kikker)
* Vermijd typeringen zoals "hulppunt", specificeer naar bijvoorb*Beperk de native database gaandeweg steeds meer conform de GWSW ontologie, begin bijvoorbeeld met voorgeschreven stelseltypes, puttypes, leidingtypes.
- Hulppunt als puttype op termijn verwijderen (Obsurv)
- Randvoorziening specificeren naar bijvoorbeeld Lamellenfilter, Retentievoorziening (Obsurv)
- MechanischRioolstelsel, VrijvervalRioolleiding en Deksel specificeren naar bijvoorbeeld Drukriolering enzovoort. (Kikker)
* Neem ontbrekende kenmerken niet mee in het GWSW.orox bestand, ook niet zonder inhoud. De relatie gwsw:hasAspect niet opnemen. (Kikker)
 Neem puttypes zonder onderscheidende functie op als extra typering (maak ze "multiparent"). Bijvoorbeeld een blinde put is zowel een type gwsw:Inspectieput als gwsw:BlindePut. Idem voor bijvoorbeeld verdekte put. (Obsurv, Kikker)
* Typeer onbekende objectsoorten altijd zo globaal mogelijk, bijvoorbeeld puttype "onbekend" omzetten naar gwsw:Rioolput ipv gwsw:Inspectieput. Dan signaleert de nulmeting het onbekende (te globale) type.
* Neem uitgevoerde maatregelen zoals gwsw:VisueelInspecterenVrijvervalLeiding correct mee in de orox-export. De maatregel heeft de relatie gwsw:hasInput met het object, zie de beschrijving van GWSW.orox. (Kikker: "gwsw:hasInput" ontbreekt, alle maatregelen zijn "inspectie") (Obsurv: maatregelen ontbreken nog) (melding Leendert, 20180702)
* Verwijder de spatie uit het top-concept "Stedelijk gebied" in GWSW.orox versie 1.4, wordt StedelijkGebied. Nog mooier is Rioleringsgebied, heeft dan als deel één óf meer Rioolstelsels. (Kikker, diverse cases, meldingen in sep 2018)
* Prefixes in GWSW.orox versie 1.4, gebruik gwsw: voor gwsw-concepten, gebruik : (blank) voor gemeente-concepten (Kikker, diverse cases, meldingen in sep 2018) 
* Lining komt niet mee in .orox bestand (Kikker, case Haarlemmermeer, melding Rob, 20180910). Lining kan met de relatie "hasPart" aan de leiding worden gekoppeld.
* Ook grote GML-linestring records (met veel punten) toestaan, breekt nu af op 24000 karakters (Kikker, case HHNK_Persleidingen, 20180911)
* Denk aan notatie van quotes in een string-literal, "Naam "met quotes" " kan niet, "Naam \"met quotes\" " kan wel (Kikker, case HHNK_Persleidingen, 20180911).
Tips voor gegevensbeheerders/adviseurs:
* Hanteer, indien het beheersysteem dit al niet verplicht stelt, alleen de GWSW objecttypes. Vooral belangrijk voor de soorten Stelsel, Put en Leiding.
* Toets de vulling van de kenmerken aan de voorwaarden van de conformiteitsklassen (verplichte vulling, grenswaarden)
* Vermijd typeringen zoals "onbekend", vul aan op basis van revisies of inspecties (Kikker)
* Vermijd typeringen zoals "hulppunt", specificeer naar bijvoorbeeld t-stuk, ontstoppingsstuk (Obsurv)
* Stem af met de leveranciers hoe speciale constructie conform GWSW beschreven dienen te worden (bijvoorbeeld "doorlaat" in Obsurv (case Zwolle) of "spindelschuif" in Kikker (melding Jafeth, 20180713)
### Aandachtspunten bij upload naar GWSW-Dataset ###
Tip: de foutmeldingen en het vermelde regelnummer ("[line nnn]") zijn niet altijd traceerbaar in het .orox-bestand. Parse het bestand met het beheersysteem voor een aanvullende analyse.
Response: "RDF Parse Error: IRI included an unencoded space: '32' [line 13]" (20171031)
Oorzaak: bug in Obsurv versie 2.0. In IRI bestandsnaam (metagegevens) kan geen spatie voorkomen. (regelnummer van de melding kan dus iets afwijken van die in het .orox bestand)
eeld t-stuk, ontstoppingsstuk (Obsurv)
* Stem af met de leveranciers hoe speciale constructie conform GWSW beschreven dienen te worden (bijvoorbeeld "doorlaat" in Obsurv (case Zwolle) of "spindelschuif" in Kikker (melding Jafeth, 20180713)
### Aandachtspunten bij upload naar GWSW-Dataset ###
Tip: de foutmeldingen en het vermelde regelnummer ("[line nnn]") zijn niet altijd traceerbaar in het .orox-bestand. Parse het bestand met het beheersysteem voor een aanvullende analyse.
Response: "RDF Parse Error: IRI included an unencoded space: '32' [line 13]" (20171031)
Oorzaak: bug in Obsurv versie 2.0. In IRI bestandsnaam (metagegevens) kan geen spatie voorkomen. (regelnummer van de melding kan dus iets afwijken van die in het .orox bestand)

Response: "RDF Parse Error: Expected ':', found '\r' [line nnnn]" (20171031)
Oorzaak: bug in Obsurv versie 2.0. In IRI gwsw-concept ":Buiten gebruik"staan spaties. Concept-IRI moet zijn :LozeLeiding .

Response: "RDF Parse Error: Illegal predicate value: \"xxx\"^^ [line nnn]" (20171031)
Oorzaak: bug in Kikker. In IRI bim-concept Stelsel staan spaties.

Response: "RDF Parse Error: Unexpected end of file" (20171101)
Oorzaak: mogelijke bug in Obsurv, laatste regel is geen afgeronde triple.

Response GWSW Server: "fout bij decoding … geen utf-8 ?" (20171101)
Oorzaak: mogelijke bug in Kikker. GWSW Server is gevoelig voor bestandsformaat, moet UTF-8 zijn (zonder BOM / Signature). Dat geldt ook wanneer er een enkel niet-UTF-8-karakter voorkomt. Dan het bestand expliciet opnieuw opslaan in UTF-8 (lukt nog niet met Notepad++, wel met Visual Studio).

Upload geslaagd, alleen geen putten en leidingen zichtbaar (20180906, Haarlemmermeer)
Oorzaak: In de Kikker-export conform GWSW-OroX versie 1.4 waren de prefixes voor GWSW-concepten en Gemeente-objecten juist gedefinieerd, maar omgedraaid toegepast in het GWSW.orox bestand. 

