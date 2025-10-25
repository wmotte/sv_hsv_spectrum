# SV-HSV Restauratie Spectrum
### Automatische generatie van Statenvertaling-varianten met taalmodellen

🌐 **[Bekijk de interactieve demo](https://wmotte.github.io/sv_hsv_spectrum/)**
🌐 **[Zie ook - voor kanttekeningen - de pilotstudie)[https://wmotte.github.io/sv1657_pilot/]**

📄 **[Motivatie.pdf](Motivatie.pdf)**

## Over dit project

Dit repository laat zien hoe moderne taalmodellen kunnen worden ingezet om systematisch verschillende restauratievarianten van de Statenvertaling te genereren. In plaats van jarenlange handmatige arbeid door commissies, kunnen we nu in enkele dagen het volledige spectrum van SV naar HSV in kaart brengen - inclusief experimentele varianten zoals een "HSV 2.0".

**Kerngegevens:**
- 400 euro aan taalmodelkosten
- Enkele weken verwerkingstijd
- Volledige SV in meerdere restauratievarianten
- Transparant, reproduceerbaar proces

## Context: Het debat rond Statenvertaling 2027

In september 2025 werd het project "Statenvertaling 2027" aangekondigd, een initiatief van het Nederlands-Vlaams Bijbelgenootschap om de Statenvertaling te moderniseren. Dit leidde tot een intensief debat in reformatorische kringen over:

### 1. **Vertaalprincipes**
De Gereformeerde Bijbelstichting (GBS) stelde dat SV2027 "afwijkt van de vertaalprincipes van de Statenvertalers" en te doeltaalgericht zou zijn geworden. De vraag: *wanneer mag een herziening zich nog Statenvertaling noemen?*

### 2. **Noodzaak en urgentie**
Uit onderzoek van het Hoornbeeck College (2023) bleek dat nog maar 50% van de jongeren de Statenvertaling leest. De taalafstand neemt toe. De vraag: *hoever moet je gaan om de tekst toegankelijk te houden?*

### 3. **Veelvoud aan edities**
Met de komst van SV2027 ontstaan er vier verschillende SV-edities naast elkaar (GBS-editie, HSV, herziene GBS, SV2027). De vraag: *leidt dit niet tot versnippering in plaats van eenheid?*

### 4. **Transparantie en tempo**
De begeleidingscommissie van SV2027 is anoniem, de definitieve keuzes zijn nog onduidelijk. De GBS werkt zorgvuldig maar traag. De vraag: *komt een oplossing wel op tijd?*

## Het tijdperk van abundance

We bevinden ons in een fundamenteel ander tijdperk. Wat vroeger maanden kostte aan vertaalarbeid en theologisch overleg, kan nu in uren worden geexploreerd. Niet als vervanging van menselijke oordeelsvorming, maar als **verkenningsinstrument**.

### Wat dit project laat zien:

1. **Systematische variatie**: In plaats van een "fase A/B/C" kunnen we het hele spectrum genereren en visualiseren
2. **Transparante argumentatie**: Elke wijziging wordt gedocumenteerd met type, motivering en linguistische grondslag
3. **Reproduceerbaar proces**: Het volledige prompt staat in deze repository - iedereen kan het zelf uitvoeren
4. **Toegankelijk**: Voor 400 euro en een paar weken werk kan elke geinteresseerde de restauratie herhalen

### Wat dit project NIET is:

- **Geen vervanging** van theologisch en kerkelijk beraad
- **Geen definitieve editie** maar een verkenning van mogelijkheden  
- **Geen claim** dat AI "beter" is dan menselijke vertalers
- **Geen standpunt** in het SV2027-debat, maar een hulpmiddel voor alle partijen

## Implicaties voor het debat

### Voor de GBS
Wanneer taalkundig onderhoud zo toegankelijk wordt, verschuift de vraag van "kunnen we dit opbrengen?" naar "durven we te kiezen?". De GBS-methodologie (alleen woorden die misverstaan worden) kan nu snel op de hele SV worden toegepast en getoetst.

### Voor SV2027  
Het transparantieprobleem (anonieme commissie, onduidelijke criteria) kan worden geadresseerd. Algoritmes kunnen immers geen autoriteit claimen - alleen argumenten geven. Dit dwingt tot explicitering.

### Voor de HSV
Een "HSV 2.0" die rekening houdt met 15 jaar taalverandering sinds 2010 - verschijning HSV - wordt nu exploreerbaar. Is er ruimte voor "onderhoud van de herziening"?

### Voor scholen en gemeenten
In plaats van te wachten op een definitieve editie, kunnen meerdere varianten naast elkaar worden bestudeerd. Welke past het beste bij onze gemeente, onze leerlingen?

## Ethische overwegingen

Dit project roept terechte vragen op:

**"Horen computers zich met de Bijbel te bemoeien?"**  
Taalmodellen doen niets anders dan statistiek op tekst. Ze "begrijpen" niet, maar herkennen patronen. Net zoals een concordantie geen theologie bedrijft, maar wel nuttig is. De vraag is niet of we technologie inzetten, maar hoe.

**"Vervangen we hiermee niet de menselijke component?"**  
Integendeel. Door varianten systematisch te genereren, wordt de menselijke keuze (welke wijziging is wenselijk?) juist *zichtbaarder*. We vervangen niet, we expliciteren.

**"Is dit niet gevaarlijk snel?"**  
Snelheid is pas gevaarlijk bij ondoordachte implementatie. Deze tool versnelt exploratie, niet besluitvorming. Het kerkelijk beraad blijft onmisbaar - maar kan nu beter geinformeerd zijn.

## Technische details

### Hoofdproces: Tekstvariantgeneratie

- **Input**: Parallelle SV- en HSV-teksten per vers (SV: 1886-editie)
- **Output**: 4-6 restauratievarianten met gedocumenteerde edits
- **Model**: Claude Sonnet 4.5 (of equivalent)
- **Methodologie**: Zie `prompt/PROMPT.md` voor het volledige systeem-prompt

### Additioneel: Virtuele neerlandicus voor taalkundige feedback

Naast het generatieproces is er een **tweede fase** ontwikkeld: een gespecialiseerd taalmodel dat fungeert als "virtuele neerlandicus" voor taalkundige kwaliteitsbeoordeling.

**Functie:**
- Beoordeelt gegenereerde varianten op **taalkundige kwaliteit** (grammatica, idioom, consistentie, register, interpunctie)
- Werkt **voorbereidend**: levert gestructureerde feedback voordat menselijke redacteuren het werk beoordelen
- Geeft **geen theologische of inhoudelijke kritiek** - uitsluitend linguïstische analyse
- Respecteert het registerniveau per variant (van klassiek-formeel tot hedendaags-natuurlijk)

**Output:**
- JSON-bestand met bevindingen per vers en per variant
- Driedeling: kritiek (moet aangepast) / waarschuwing (suboptimaal) / suggestie (kan beter)
- Inclusief concrete voorstellen en toelichting
- Ook positieve punten: wat is taalkundig goed opgelost?

**Prompt:** Zie `prompt_virt_nl/PROMPT.md` voor het volledige systeem-prompt van de virtuele neerlandicus

Dit twee-fasenproces (generatie + taalkundige review) zorgt voor systematische kwaliteitscontrole voordat revisoren hun oordeel geven. De AI doet het voorbereidende taalkundige spitwerk; de inhoudelijke en theologische verantwoordelijkheid blijft menselijk.

De standalone HTML-viewer (`docs/index.html`) toont enkele voorbeelden van de output met interactieve weergave van wijzigingen en argumentaties.

## Gebruik

1. **Exploreren**: Open `docs/index.html` in je browser voor voorbeelden
2. **Reproduceren**: Gebruik het prompt uit `prompt/PROMPT.md` met je eigen tekstselecties  
3. **Aanpassen**: Wijzig de percentages of toevoegingscriteria naar eigen inzicht

## Open vragen aan de gemeenschap

1. Welke restauratievariant(en) zouden het meest dienstbaar zijn?
2. Hoe kunnen we dit proces inbedden in kerkelijke besluitvorming?
3. Welke rol kan/moet transparante AI hebben in Bijbelvertaalwerk?
4. Zou een "living translation" met regelmatig taalkundig onderhoud wenselijk zijn?

## Tot slot: Een nederige bijdrage

Dit project claimt geen theologische autoriteit. Het is een technisch instrument, geboren uit fascinatie voor de snijvlakken tussen taal, traditie en technologie. Of het nuttig is, bepaalt de gemeenschap.

Moge het gesprek dat dit oproept - over betrouwbaarheid, toegankelijkheid, eenheid en vernieuwing - bijdragen aan het bewaren van Gods Woord voor de volgende generatie.

---

## Contact

**W.M. (Wim) Otte**  
Predikant, Interkerkelijk Dovenpastoraat  
Onderzoeker, UMC Utrecht  
📧 w.m.otte@umcutrecht.nl

*"Want dit is wel het eerste, dat hun de woorden Gods zijn toebetrouwd" (Romeinen 3:2b (SV))*
