### Aandachtspunten bij export van GWSW.orox bestand ###
**Tips voor leveranciers:**
* Verduidelijk de handelingen voor de exportfunctie van GWSW.orox zodat de juiste omzetting van alle gegevens uit de native-database geborgd is.
* Geef in een logbestand op heldere wijze aan welke gegevens zijn omgezet en welke aannames daarbij zijn gedaan. Anders blijven ook automatische "verbeteringen" verborgen.
* Beperk de native database gaandeweg steeds meer conform de GWSW ontologie, begin bijvoorbeeld met voorgeschreven stelseltypes, puttypes, leidingtypes.
- Hulppunt als puttype op termijn verwijderen (Obsurv)
- Randvoorziening specificeren naar bijvoorbeeld Lamellenfilter, Retentievoorziening (<span style="color:red">Obsurv</span>)
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

**Tips voor gegevensbeheerders/adviseurs:**
* Hanteer, indien het beheersysteem dit al niet verplicht stelt, alleen de GWSW objecttypes. Vooral belangrijk voor de soorten Stelsel, Put en Leiding.
* Toets de vulling van de kenmerken aan de voorwaarden van de conformiteitsklassen (verplichte vulling, grenswaarden)
* Vermijd typeringen zoals "onbekend", vul aan op basis van revisies of inspecties (Kikker)
* Vermijd typeringen zoals "hulppunt", specificeer naar bijvoorbeeld t-stuk, ontstoppingsstuk (Obsurv)
* Stem af met de leveranciers hoe speciale constructie conform GWSW beschreven dienen te worden (bijvoorbeeld "doorlaat" in Obsurv (case Zwolle) of "spindelschuif" in Kikker (melding Jafeth, 20180713)

### Aandachtspunten bij upload naar GWSW-Dataset ###
Tip: de foutmeldingen en het vermelde regelnummer ("[line nnn]") zijn niet altijd traceerbaar in het .orox-bestand. Parse het bestand met het beheersysteem voor een aanvullende analyse.

Response: "RDF Parse Error: IRI included an unencoded space: '32' [line 13]" (20171031)
_Oorzaak: bug in Obsurv versie 2.0. In IRI bestandsnaam (metagegevens) kan geen spatie voorkomen. (regelnummer van de melding kan dus iets afwijken van die in het .orox bestand)_

Response: "RDF Parse Error: Expected ':', found '\r' [line nnnn]" (20171031)
Oorzaak: bug in Obsurv versie 2.0. In IRI gwsw-concept ":Buiten gebruik"staan spaties. Concept-IRI moet zijn :LozeLeiding .

Response: "RDF Parse Error: Illegal predicate value: \"xxx\"^^ [line nnn]" (20171031)
_Oorzaak: bug in Kikker. In IRI bim-concept Stelsel staan spaties._

Response: "RDF Parse Error: Unexpected end of file" (20171101)
_Oorzaak: mogelijke bug in Obsurv, laatste regel is geen afgeronde triple._

Response GWSW Server: "fout bij decoding … geen utf-8 ?" (20171101)
_Oorzaak: mogelijke bug in Kikker. GWSW Server is gevoelig voor bestandsformaat, moet UTF-8 zijn (zonder BOM / Signature). Dat geldt ook wanneer er een enkel niet-UTF-8-karakter voorkomt. Dan het bestand expliciet opnieuw opslaan in UTF-8 (lukt nog niet met Notepad++, wel met Visual Studio)._

Upload geslaagd, alleen geen putten en leidingen zichtbaar (20180906, Haarlemmermeer)
_Oorzaak: In de Kikker-export conform GWSW-OroX versie 1.4 waren de prefixes voor GWSW-concepten en Gemeente-objecten juist gedefinieerd, maar omgedraaid toegepast in het GWSW.orox bestand._

