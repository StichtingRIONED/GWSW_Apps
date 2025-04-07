# GWSW Apps

<style>
  .symbolSmall{width:20px;height:20px;margin-right:1em;vertical-align:middle}
  .symbol{width:30px;height:30px;margin-right:1em;vertical-align:middle}
</style>

# Inleiding

Stichting RIONED is initiatiefnemer en eigenaar van dit GitHub-project, Eric Oosterom is de verantwoordelijk projectmanager. 

Vragen over deze website en het GWSW kunt u stellen via gwsw@rioned.org. 

# Details GWSW Apps

## Aandachtspunten export OroX-bestand

Deze analyse is gebaseerd op:
* de verslaggeving van Diet van Wendel (mailing dd najaar 2017) 
* de verslaggeving van Gwendolijn Vugs (notitie dd 20180124, kenmerk N002-1260650GBV-V01-hgm-NL)
* de meldingen van de GWSW Adviseurs (vanaf februari 2018 tot heden)

### Tips voor leveranciers:

* De hoofdriolering en aansluitingen zo veel mogelijk scheiden, ook de erfafscheidingsputten in dataset_Aansluitingen zetten (het netwerk = hoofdriolering) (20240226/mv).
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
* Neem puttypes zonder onderscheidende functie op als extra typering (maak ze "multiparent"). Bijvoorbeeld een blinde put is zowel een type gwsw:Inspectieput als gwsw:BlindePut. 
Idem voor bijvoorbeeld verdekte put. (<span style="color:red">Obsurv, Kikker</span>)
* Typeer onbekende objectsoorten altijd zo globaal mogelijk, bijvoorbeeld puttype "onbekend" omzetten naar gwsw:Rioolput ipv gwsw:Inspectieput. Dan signaleert de nulmeting het 
onbekende (te globale) type.
* Neem uitgevoerde maatregelen zoals gwsw:VisueelInspecterenVrijvervalLeiding correct mee in de orox-export. De maatregel heeft de relatie gwsw:hasInput met het object, 
zie de beschrijving van GWSW.orox. (<span style="color:red">Kikker</span>: "gwsw:hasInput" ontbreekt, alle maatregelen zijn "inspectie") (<span style="color:red">Obsurv</span>: maatregelen ontbreken nog) (melding Leendert, 20180702)
* Verwijder de spatie uit het top-concept "Stedelijk gebied" in GWSW.orox versie 1.4, wordt StedelijkGebied. Nog mooier is Rioleringsgebied, 
heeft dan als deel één óf meer Rioolstelsels. (<span style="color:red">Kikker</span>, diverse cases, meldingen in sep 2018)
* Prefixes in GWSW.orox versie 1.4, gebruik gwsw: voor gwsw-concepten, gebruik : (blank) voor gemeente-concepten (<span style="color:red">Kikker</span>, diverse cases, meldingen in sep 2018) 
* Lining komt niet mee in .orox bestand (<span style="color:red">Kikker</span>, case Haarlemmermeer, melding Rob, 20180910). Lining kan met de relatie "hasPart" aan de leiding worden gekoppeld.
* Ook grote GML-linestring records (met veel punten) toestaan, breekt nu af op 24000 karakters (<span style="color:red">Kikker</span>, case HHNK_Persleidingen, 20180911)
* Denk aan notatie van quotes in een string-literal, "Naam "met quotes" " kan niet, "Naam \\"met quotes\\" " kan wel (<span style="color:red">Kikker</span>, case HHNK_Persleidingen, 20180911).

### Tips voor gegevensbeheerders/adviseurs:
* Hanteer, indien het beheersysteem dit al niet verplicht stelt, alleen de GWSW objecttypes. Vooral belangrijk voor de soorten Stelsel, Put en Leiding.
* Toets de vulling van de kenmerken aan de voorwaarden van de conformiteitsklassen (verplichte vulling, grenswaarden)
* Vermijd typeringen zoals "onbekend", vul aan op basis van revisies of inspecties (<span style="color:red">Kikker</span>)
* Vermijd typeringen zoals "hulppunt", specificeer naar bijvoorbeeld t-stuk, ontstoppingsstuk (<span style="color:red">Obsurv</span>)
* Stem af met de leveranciers hoe speciale constructie conform GWSW beschreven dienen te worden (bijvoorbeeld "doorlaat" in <span style="color:red">Obsurv</span> (case Zwolle) of 
"spindelschuif" in <span style="color:red">Kikker</span> (melding Jafeth, 20180713)

## Aandachtspunten upload OroX-bestand

Deze analyse is gebaseerd op:
* de verslaggeving van Diet van Wendel (mailing dd najaar 2017) 
* de verslaggeving van Gwendolijn Vugs (notitie dd 20180124, kenmerk N002-1260650GBV-V01-hgm-NL)
* de meldingen van de GWSW Adviseurs (vanaf februari 2018 tot heden)

### Geconstateerd tijdens upload GWSW.orox

Tip: de foutmeldingen en het vermelde regelnummer ("[line nnn]") zijn niet altijd traceerbaar in het .orox-bestand. Parse het bestand met het beheersysteem voor een aanvullende analyse.

Response: "RDF Parse Error: IRI included an unencoded space: '32' [line 13]" (20171031)
<span style="color:blue">_Oorzaak: bug in Obsurv versie 2.0. In IRI bestandsnaam (metagegevens) kan geen spatie voorkomen. (regelnummer van de melding kan dus iets afwijken van 
die in het .orox bestand)_</span>

Response: "RDF Parse Error: Expected ':', found '\r' [line nnnn]" (20171031)
<span style="color:blue">_Oorzaak: bug in Obsurv versie 2.0. In IRI gwsw-concept ":Buiten gebruik"staan spaties. Concept-IRI moet zijn :LozeLeiding._</span>

Response: "RDF Parse Error: Illegal predicate value: \"xxx\"^^ [line nnn]" (20171031)
<span style="color:blue">_Oorzaak: bug in Kikker. In IRI bim-concept Stelsel staan spaties._</span>

Response: "RDF Parse Error: Unexpected end of file" (20171101)
<span style="color:blue">_Oorzaak: mogelijke bug in Obsurv, laatste regel is geen afgeronde triple._</span>

Response GWSW Server: "fout bij decoding … geen utf-8 ?" (20171101)
<span style="color:blue">_Oorzaak: mogelijke bug in Kikker. GWSW Server is gevoelig voor bestandsformaat, moet UTF-8 zijn (zonder BOM / Signature). Dat geldt ook wanneer er een 
enkel niet-UTF-8-karakter voorkomt. Dan het bestand expliciet opnieuw opslaan in UTF-8 (lukt nog niet met Notepad++, wel met Visual Studio)._</span>

Upload geslaagd, alleen geen putten en leidingen zichtbaar (20180906, Haarlemmermeer)
<span style="color:blue">_Oorzaak: In de Kikker-export conform GWSW-OroX versie 1.4 waren de prefixes voor GWSW-concepten en Gemeente-objecten juist gedefinieerd, maar omgedraaid 
toegepast in het GWSW.orox bestand._</span>

## Evaluatie Nulmeting

De juiste interpretatie van de nulmeting-resultaten vraagt kennis van het gehele proces. De GWSW Nulmeting dient alleen door daarin getrainde adviseurs uitgevoerd te worden. 
Algemene informatie over de GWSW Nulmeting is te vinden in:
* Het document GWSW Nulmeting Beschrijving (download op [apps.gwsw.nl](https://apps.gwsw.nl) )

### Procedure meting gegevenskwaliteit
* Vul de GWSW Dataset: upload een GWSW.orox export
* Start de nulmeting: toets de dataset aan de gekozen conformiteitsklasse, bijvoorbeeld "MdsPlan" 
* Voer de nulmeting uit en analyseer de resultaten
* Doe eerst een "quick-scan". Als er veel onbekende of te globale typeringen zijn, is de overige kwaliteitsmeting niet betrouwbaar. Breng dan eerst de database voor wat betreft 
de typering op orde. Daarmee voorkom je dat er twee keer een “zwaar” metingtraject wordt doorlopen. (ervaring met case Tholen)
* Gebruik de GWSW-Geoserver (via het WFS protocol) om de grafische presentatie te vergelijken met die van het Beheersysteem
* Voer de nulmeting opnieuw uit en herleid de foutmeldingen:
	- Oorzaak in native database? (dus beheersysteem nodig bij de analyse) = melden bij beheerder
	- Oorzaak in de exportfunctie Orox ? (opbouw/mapping GWSW.orox bestand onvoldoende)  = melden bij softwareleverancier (altijd via RIONED)
	- Oorzaak in de nulmeting (foute werking) = melden bij RIONED
	- Oorzaak in de ontologie (GWSW algemeen of de CFK, bijvoorbeeld: bepaalde types ontbreken nog) = melden bij RIONED

### Eerdere analyse van de werking
(oktober 2017 - januari 2018)

**Inrichting conformiteitsklassen**
Op de websites de kwaliteit van de conformiteitsklassen (bijvoorbeeld [MdsPlan](https://apps.gwsw.nl/MdsPlan)) controleren:
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

# Gegevensgebruiksniveaus

Gegevensgebruiksniveaus zijn bedoeld als handvat voor beheerders en applicatieleveranciers van beheersoftware. Een gegevensgebruiksniveau definieert de gegevensbehoefte van de beheerder in relatie tot een bepaalde toepassing. Het is een beschrijving van objecttypen en de eigenschappen (kenmerken) voor diverse beheeraspecten.

De (technische) restricties op objecttypen, relaties, kenmerken en waardentypen, noodzakelijk voor een goede werking van (GWSW-) toepassingen worden conformiteitsklassen genoemd. Zie hiervoor [Hoofdstuk 4](#h4).

## Ontwerp

De opdracht aan de werkgroep was om per gegevensgebruiksniveau een lijst te hebben, waarmee de gegevens, in bijvoorbeeld een rioolbeheerpakket, getoetst kunnen worden op (de mate van) volledigheid, betrouwbaarheid en nauwkeurigheid. 
Als eerste zijn door de werkgroep de volgende gegevensgebruiksniveaus gedefinieerd:

| Niveaunaam | Omschrijving                                                                                                                                    |
|------------|-------------------------------------------------------------------------------------------------------------------------------------------------|
| Ligging    | Ligging en globale objectinformatie van hoofdriolering (fysieke objecten op hoofdlijnen, voor bijvoorbeeld in PDOK)                             |
| Modelleren | Hydraulisch modelleren (hydraulisch relevante fysieke objecten, meer detail)                                                                    |
| RibX       | Reiniging en inspectie vrijverval riolering (fysieke objecten, waar beheer op nodig is)                                                         |
| Prognoses  | Afvalwaterprognoses, ontwikkelingen in de afvalwaterketen (beperkte hoeveelheid fysieke objecten, globaal niveau: gebieden, systemen, stelsels) |
| Volledig   | Alle stedelijk water objecten, de gecombineerde gebruiksniveaus                                                                                 |

Vervolgens is voor elk gegevensgebruiksniveau een lijst van benodigde fysieke objecten en benodigde kenmerken opgesteld. 
Eind september 2023 zijn deze lijsten opgeleverd aan Stichting RIONED. Deze zijn te vinden in de [spreadsheet met overzicht gebruiksniveaus](conformiteitsklassen/Vergelijking%20app-wg.xlsx). 

De spreadsheet bevat de inhoud van de vijf nieuwe gegevensgebruiksniveaus in het GWSW. Per gegevensgebruiksniveau is een markering opgenomen:

Bij de voorkomens van fysieke objecten:  

| code | omschrijving                                                                                   |
|------|------------------------------------------------------------------------------------------------|
| g    | Het objecttype (de klasse) is relevant, valt binnen het gegevensgebruiksniveau                 |
| f    | Het objecttype valt binnen het gegevensgebruiksniveau maar is te abstract, gebruik een subtype |
| -    | Het objecttype is niet relevant, valt buiten het gegevensgebruiksniveau                        |

Bij de eigenschappen (kenmerken) van fysieke objecten:

| code | omschrijving                                                                     |
|------|----------------------------------------------------------------------------------|
| g    | Het kenmerk is noodzakelijk binnen het gegevensgebruiksniveau (moet bekend zijn) |
| o    | Het kenmerk is optioneel binnen het gegevensgebruiksniveau (kan bekend zijn)     |
| -    | Het kenmerk is niet relevant, valt buiten het gegevensgebruiksniveau             |

## Eisenlijst

Met [GWSW Apps](https://apps.gwsw.nl/item_publish_cfk) kan - bijvoorbeeld door een rioolbeheerder - van het vigerende GWSW datamodel automatisch een eisenlijst voor onder andere softwareleveranciers worden samengesteld.
Deze lijst wordt samengesteld op basis van de door de persoon gekozen (één of meerdere) gegevensgebruiksniveaus.  

Als de beheerder met de rioleringsgegevens bijvoorbeeld een hydraulische doorrekening wil laten maken en ook een fatsoenlijke gegevenspresentatie voor PDOK wil leveren, 
dan kiest deze persoon voor de gebruiksniveaus *Modelleren* en *Ligging*.

Bij de aanbesteding of inkoop van een (nieuw) beheerpakket of andersoortige applicatie kan de opdrachtgever verwijzen naar de gegevensgebruiksniveaus als specificatie van de eisen waar de applicatie aan dient te voldoen. De leverancier zal dat dan moeten (kunnen) aantonen.

Daarnaast maken de gegevensgebruiksniveaus onderdeel uit van de applicatietoetsing.

## Techniek

### Notatie in datamodel

Het GWSW-datamodel wordt voor de gegevensgebruiksnviveaus gefilterd op de CoF-code (collection of facts). Zie ook 
[details deelmodellen](https://stichtingrioned.github.io/GWSW_Ontologie_RDF/#details-deelmodellen). De volgende tabel bevat de gehanteerde CoF'en per gebruiksniveau.

Met zogenaamde CFK-notaties wordt (binnen het filter op CoF'en) de gebruiksniveau-definitie verder aangescherpt, 
de notatie kan bijvoorbeeld markeren dat het objecttype niet relevant is of te abstract is.
De CFK-notatie staat in het GWSW-datamodel, zie ook [validity context](https://stichtingrioned.github.io/GWSW_Ontologie_RDF/#validity-context).

| Niveaunaam | CoF                 | CFK-nr |
|------------|---------------------|--------|
| Ligging    | TOP MDS BAS         | 10     |
| Modelleren | TOP HYD             | 11     |
| RibX       | TOP MDS             | 12     |
| Prognoses  | TOP DMO             | 13     |
| Volledig   | TOP MDS BAS HYD DMO | 14     |

# Conformiteitsklassen (CFKen)

Waar gegevensgebruiksniveaus vooral de beschrijving en eigenschappen van fysieke objecten definiëren passend bij het gebruik van de gegevens voor (beheer-)toepassingen, geven conformiteitsklassen (CFKs) de technische restricties daarvan binnen (GWSW-)toepassingen.
Kort gezegd: Gegevensgebruiksniveaus bepalen **of** het object of het kenmerk in de gegevens zit en Conformiteitsklassen bepalen **hoe** (met welke kwaliteit) het object of kenmerk in de gegevens zit.

Die "kwaliteit" zijn de eisen die gesteld worden aan kenmerken en relaties, noodzakelijk voor een goede werking van (GWSW-)toepassingen.

## Kenmerken
In de volgende tabel staan de kwaliteitsmaatstaven voor de kenmerken. Als een kwaliteitsmaatstaf niet is ingevuld, dan is het kenmerk niet verplicht in de conformiteitsklasse. 

### Legenda: Kwaliteit kenmerken

Kwaliteitsmaatstaf | Code                                   | Omschrijving
-------------------|----------------------------------------|-----------------------------------------------
laag               | <strong style="color:green">L</strong> | De kwaliteit is niet of nauwelijks van invloed
Neutraal           | **N**                                  | De kwaliteit is van invloed
Hoog               | <strong style="color:red">H</strong>   | De kwaliteit is van doorslaggevend belang

### Maatstaven: Kwaliteit kenmerken

Concept       | Kenmerk                          | Nauwkeurigheid               | MdsPlan | MdsProj | Hyd
--------------|----------------------------------|------------------------------|----|----|----
Kenmerk       | Wijze van inwinning              | Waarde in collectie
Kenmerk       | Datum inwinning                  |                              
Put           | Materiaal put                    | Waarde in collectie          | <strong style="color:red">H</strong>   | <strong style="color:red">H</strong>   | <strong style="color:red">H</strong>  
Put           | Horizontale afmetingen           | 300 <= Waarde <= 4000 mm     | **N**                                  | **N**                                  | <strong style="color:red">H</strong> 
Put           | Hoogte put                       | 500 <= Waarde <= 4000 mm     | **N** 
Put           | Vorm put                         | Waarde in collectie          | **N**                                  | **N**                                  | <strong style="color:red">H</strong>  
Put           | Lengte putdeel                   |                              
Put           | Putoriëntatie / Positie / X      | -7000 <= Waarde <= 300000 m  | **N**                                  | **N**                                  | <strong style="color:red">H</strong> 
Put           | Putoriëntatie / Positie / Y      | 289000 <= Waarde <= 629000 m | **N**                                  | **N**                                  | <strong style="color:red">H</strong> 
Put           | Maaiveld put                     | -20 <= Waarde <= 300 m       | **N**                                  |                                        | <strong style="color:red">H</strong> 
Put           | Z-coördinaat                     | -20 <= Waarde <= 300 m       
Put           | Maaiveldschematisering           | Waarde in collectie          |                                        |                                        | <strong style="color:red">H</strong> 
Put           | Bergend oppervlak                |                              |                                        |                                        | <strong style="color:red">H</strong> 
Put           | Grondwaterniveau                 |                              |                                        |                                        | **N** 
Put           | Afvoerend oppervlak              |                              |                                        |                                        | <strong style="color:red">H</strong>
Deksel        | Vorm deksel                      | Waarde in collectie           
Deksel        | Materiaal deksel                 | Waarde in collectie
Deksel        | Dekseloriëntatie (niveau)        | -20 <= Waarde <= 300 m       | **N** 
Deksel        | Breedte deksel                   |                              
Deksel        | Lengte deksel                    |                              
Put/Lei       | Einddatum                        |                              
Put/Lei       | Begindatum                       |                              | <strong style="color:green">L</strong> | <strong style="color:green">L</strong> 
Put/Lei       | Datum maatregel                  |                              
Bouwwerk      | Bouwwerkoriëntatie / Positie / X | -7000 <= Waarde <= 300000 m  | **N**                                  | **N**                                  | <strong style="color:red">H</strong> 
Bouwwerk      | Bouwwerkoriëntatie / Positie / Y | 289000 <= Waarde <= 629000 m | **N**                                  | **N**                                  | <strong style="color:red">H</strong> 
Bouwwerk      | Materiaal bouwwerk               | Waarde in collectie          | <strong style="color:red">H</strong>   | <strong style="color:red">H</strong>   | <strong style="color:red">H</strong>  
Bouwwerk      | Breedte bouwwerk                 |                              | **N**                                  | **N**                                  | <strong style="color:red">H</strong> 
Bouwwerk      | Lengte bouwwerk                  |                              | **N**                                  | **N**                                  | **N**                                  
Bouwwerk      | Hoogte bouwwerk                  |                              | **N** 
Compart.      | Onderdeeloriëntatie              |                              |                                        |                                        | <strong style="color:red">H</strong> 
Compart.      | Breedte compartiment             |                              |                                        |                                        | <strong style="color:red">H</strong> 
Compart.      | Lengte compartiment              |                              |                                        |                                        | **N**                               
Compart.      | Hoogte compartiment              |                              |        
Compart.      | Vorm compartiment                | Waarde in collectie          |                                        |                                        | <strong style="color:red">H</strong>  
Compart.      | Afvoerend oppervlak              |                              |                                        |                                        | **N**
Leiding       | Leidingoriëntatie / Positie / X  | -7000 <= Waarde <= 300000 m  | **N**                                  | **N**                                  | <strong style="color:red">H</strong> 
Leiding       | Leidingoriëntatie / Positie / Y  | 289000 <= Waarde <= 629000 m | **N**                                  | **N**                                  | <strong style="color:red">H</strong> 
Leiding       | Leidingoriëntatie begin/eind     |                              | <strong style="color:red">H</strong>   | <strong style="color:red">H</strong>   | <strong style="color:red">H</strong> 
Leiding       | Maaiveld beginpunt leiding       | -20 <= Waarde <= 300 m       
Leiding       | Maaiveld eindpunt leiding        | -20 <= Waarde <= 300 m       
Leiding       | B.o.b. beginpunt leiding         | -20 <= Waarde <= 300 m       | <strong style="color:red">H</strong>   | <strong style="color:red">H</strong>   | <strong style="color:red">H</strong> 
Leiding       | B.o.b. eindpunt leiding          | -20 <= Waarde <= 300 m       | <strong style="color:red">H</strong>   | <strong style="color:red">H</strong>   | <strong style="color:red">H</strong> 
Leiding       | Lengte leiding                   | 1 <= Waarde <= 75 m          | <strong style="color:red">H</strong>   | <strong style="color:red">H</strong>   | <strong style="color:red">H</strong>  
Leiding       | Lengte buisdeel                  |                              
Leiding       | Materiaal leiding                | Waarde in collectie          | <strong style="color:red">H</strong>   | <strong style="color:red">H</strong>   | <strong style="color:red">H</strong> 
Leiding       | Wanddikte                        |                              |                                        |                                        | **N** 
Leiding       | SDR waarde (kunststof leiding)   |                              |                                        |                                        | <strong style="color:red">H</strong>
Leiding       | Hoogte leiding                   | 63 <= Waarde <= 4000 mm      | **N**                                  | **N**                                  | <strong style="color:red">H</strong> 
Leiding       | Breedte leiding                  | 63 <= Waarde <= 4000 mm      | **N**                                  | **N**                                  | <strong style="color:red">H</strong> 
Leiding       | Vorm leiding                     | Waarde in collectie          | **N**                                  | **N**                                  | <strong style="color:red">H</strong> 
Leiding       | Verbindingstype                  | Waarde in collectie
Leiding       | Afvoerend oppervlak              |                              |                                        |                                        | <strong style="color:red">H</strong>
Lining        | Soort lining                     | Waarde in collectie          |                                        |                                        | <strong style="color:red">H</strong> 
Lining        | Materiaal lining                 | Waarde in collectie          |                                        |                                        | <strong style="color:red">H</strong> 
Project       | Projectreferentie opdrachtgever  |                              | **N**                                  | <strong style="color:red">H</strong> 
Project       | Projectreferentie opdrachtnemer  |                              | **N**                                  | <strong style="color:red">H</strong> 
Straat        | Verhardingstype                  | Waarde in collectie
Ovs.drempel   | Onderdeeloriëntatie              |                              |                                        |                                        | <strong style="color:red">H</strong> 
Ovs.drempel   | Drempelniveau                    | -20 <= Waarde <= 300 m       |                                        |                                        | <strong style="color:red">H</strong> 
Ovs.drempel   | Drempelbreedte                   |                              |                                        | <strong style="color:red">H</strong> 
Ovs.drempel   | Afvoercoëfficient                |                              |                                        | <strong style="color:red">H</strong> 
Ovs.drempel   | Stromingsrichting                | Waarde in collectie          |                                        |                                        | <strong style="color:red">H</strong> 
Stuwmuur      | Onderdeeloriëntatie              |                              |                                        |                                        | <strong style="color:red">H</strong> 
Stuwmuur      | Drempelniveau                    | -20 <= Waarde <= 300 m       |                                        |                                        | <strong style="color:red">H</strong> 
Stuwmuur      | Drempelbreedte                   |                              |                                        | <strong style="color:red">H</strong> 
Stuwmuur      | Afvoercoëfficient                |                              |                                        | <strong style="color:red">H</strong> 
Stuwmuur      | Stromingsrichting                | Waarde in collectie          |                                        |                                        | <strong style="color:red">H</strong> 
Doorlaat      | Onderdeeloriëntatie              |                              |                                        |                                        | <strong style="color:red">H</strong> 
Doorlaat      | Doorlaatniveau                   |                              |                                        |                                        | <strong style="color:red">H</strong> 
Doorlaat      | Contractiecoëfficient doorlaat   |                              |                                        |                                        | <strong style="color:red">H</strong> 
Doorlaat      | Maximale capaciteit doorlaat     |                              |                                        |                                        | <strong style="color:red">H</strong> 
Doorlaat      | Stromingsrichting                | Waarde in collectie          |                                        |                                        | <strong style="color:red">H</strong> 
Doorlaat      | Breedte opening                  |                              |                                        |                                        | <strong style="color:red">H</strong> 
Doorlaat      | Hoogte opening                   |                              |                                        |                                        | **N**
Doorlaat      | Vorm opening                     | Waarde in collectie          |                                        |                                        | <strong style="color:red">H</strong>  
Pomp          | Onderdeeloriëntatie              |                              |                                        |                                        | <strong style="color:red">H</strong> 
Pomp          | Pompcapaciteit                   |                              |                                        |                                        | <strong style="color:red">H</strong> 
Pomp          | Aanslagniveau benedenstrooms     |                              |                                        |                                        | **N** 
Pomp          | Afslagniveau benedenstrooms      |                              |                                        |                                        | **N**
Pomp          | Aanslagniveau bovenstrooms       |                              |                                        |                                        | **N**
Pomp          | Afslagniveau bovenstrooms        |                              |                                        |                                        | **N**
Uitl.constr.  | Uitlaat (punt)                   |                              |                                        |                                        | <strong style="color:red">H</strong> 
Hulpstuk      | Hulpstukoriëntatie               |                              |                                        |                                        | <strong style="color:red">H</strong> 

## Relaties

In de volgende tabel staan de kwaliteitsmaatstaven “Relaties” (ookwel: Äantal voorkomens" genoemd), in hoeverre zijn de relaties tussen concepten consistent. 
Als een kwaliteitsmaatstaf niet is ingevuld, dan is de relatie niet verplicht in de conformiteitsklasse.
In databases voor Stedelijk Water Systemen is de netwerkdefinitie belangrijk, in de conformiteitsklassen MdsProj en Hyd wordt hierop gecontroleerd.

### Legenda: Kwaliteit relaties

Kwaliteitsmaatstaf | Code                                   | Omschrijving
-------------------|----------------------------------------|-----------------------------------------------
laag               | <strong style="color:green">L</strong> | De kwaliteit is niet of nauwelijks van invloed
Neutraal           | **N**                                  | De kwaliteit is van invloed
Hoog               | <strong style="color:red">H</strong>   | De kwaliteit is van doorslaggevend belang

### Maatstaven: Kwaliteit relaties

Subject                 | Soort relatie    | Object                  | Aantal | MdsPlan                                | MdsProj                                | Hyd
------------------------|------------------|-------------------------|--------|----------------------------------------|----------------------------------------|-------------------------------------
Leidingoriëntatie       | heeft als deel   | Beginpunt               | 1      | <strong style="color:red">H</strong>   | <strong style="color:red">H</strong>   | <strong style="color:red">H</strong>
Leidingoriëntatie       | heeft als deel   | Eindpunt                | 1      | <strong style="color:red">H</strong>   | <strong style="color:red">H</strong>   | <strong style="color:red">H</strong>
Kolkaansluiting         | heeft als deel   | Kolk                    | 1      | <strong style="color:red">H</strong>   | <strong style="color:green">L</strong> |
Vrijverval rioolstelsel | heeft als deel   | Rioolput                | 1-n    | <strong style="color:red">H</strong>   | <strong style="color:green">L</strong> | **N**
Vrijverval rioolstelsel | heeft als deel   | Vrijverval rioolleiding | 1-n    | <strong style="color:red">H</strong>   | <strong style="color:green">L</strong> | **N**
Gescheiden stelsel      | heeft als deel   | Hemelwaterstelsel       | 1      | <strong style="color:green">L</strong> | <strong style="color:green">L</strong> | **N**
Gescheiden stelsel      | heeft als deel   | Vuilwaterstelsel        | 1      | <strong style="color:green">L</strong> | <strong style="color:green">L</strong> | **N**
Beginpunt leiding       | heeft verbinding | Put                     | 1      | <strong style="color:red">H</strong>   |                                        | <strong style="color:red">H</strong>
Eindpunt leiding        | heeft verbinding | Put                     | 1      | <strong style="color:red">H</strong>   |                                        | <strong style="color:red">H</strong>