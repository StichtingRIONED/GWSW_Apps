# Evaluatie Nulmeting #
## Analyse van de werking ##
De juiste interpretatie van de nulmeting-resultaten vraagt kennis van het gehele proces. De GWSW Nulmeting dient alleen door daarin getrainde adviseurs uitgevoerd te worden.
Informatie over de GWSW Nulmeting is te vinden in:

* De soortenboom op de websites data.gwsw.nl (de module GWSW Basis) en, voor conformiteitsklasse MdsPlan, data.gwsw.nl/MdsPlan
* Het document GWSW Nulmeting Beschrijving (download op apps.gwsw.nl)
* Het document GWSW.orox Beschrijving (download op apps.gwsw.nl)
* Deze notitie: GWSW Apps Werkdocument. 

### Aanpak van de analyse ###
(oktober 2017 - januari 2018)

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

### Resultaten van de analyse ###
(januari 2018)
 
Deze analyse is gebaseerd op:
* de verslaggeving van Diet van Wendel (mailing dd najaar 2017) 
* de verslaggeving van Gwendolijn Vugs (notitie dd 20180124, kenmerk N002-1260650GBV-V01-hgm-NL)
* de meldingen van de GWSW Adviseurs (vanaf februari 2018 tot heden)
