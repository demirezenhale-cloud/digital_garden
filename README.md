# LEARNING LOG 
### Markdown als hulpmiddel

Om mijn learning log overzichtelijk bij te houden, gebruik ik de officiële Markdown-handleiding van GitHub.

**Bron:** [GitHub – Markdown-handleiding](https://docs.github.com/en/get-started/writing-on-github/getting-started-with-writing-and-formatting-on-github/basic-writing-and-formatting-syntax)

## **Sprint 1 Week 3  ( 25 November Donderdag )**

### **Wat heb ik vandaag voor mijn website gedaan?**

### Grid voor een groot scherm

#### Wat wilde ik?

Op een groot scherm wilde ik mijn kaarten in een zigzag zetten, net als het pad in mijn schets van Opdracht 21: kaart 1 links, kaart 2 rechts, kaart 3 links, enzovoort.

#### Hoe heb ik het gedaan?

Ik heb een media query gebruikt. Daardoor geldt het grid alleen op een groot scherm (vanaf `48em`). Op een telefoon blijven de kaarten gewoon onder elkaar staan (**mobile first**).

In de media query heb ik van de section een grid gemaakt met 12 even brede kolommen. Daarna heb ik met `nth-of-type` gekozen waar de kaarten staan:

- De oneven kaarten: van lijn 1 tot 8.
- De even kaarten: van lijn 6 tot 13.

```css
@media (min-width: 48em) {
  main section {
    display: grid;
    grid-template-columns: repeat(12, 1fr);
  }

  main article:nth-of-type(odd) {
    grid-column: 1 / 8;
  }

  main article:nth-of-type(even) {
    grid-column: 6 / 13;
  }
}
```

#### Welk probleem kwam ik tegen?

Op papier had ik 6 kolommen gekozen. Maar in de code kwamen twee kaarten dan naast elkaar op één rij te staan, en was de zigzag weg. Toen ik de kaarten een paar kolommen liet delen, werden ze te breed. Daarom ben ik overgestapt op 12 smallere kolommen.Omdat de kaarten de kolommen tussen lijn 6 en 8 delen, passen ze niet naast elkaar en krijgt elke kaart een eigen rij.

#### Resultaat
Op een groot scherm staan de kaarten nu in een zigzag en op een telefoon onder elkaar.
Ik heb geleerd dat een schets een plan is: als iets in de code niet werkt, mag je het plan aanpassen.


## **Sprint 1 Week 3 Les 2 ( 25 November Woensdag )**

Wat heb ik geleerd? Ontwerpprincipes: vorm, lay-out en grid (Ontwerptheorie)

Maandag heb ik mijn Digital Garden responsive gemaakt. Mijn website werkt nu op een telefoon en op een laptop, en hij is leesbaar. Maar een website die "werkt" is nog niet hetzelfde als een website die "er goed uitziet en makkelijk te begrijpen is". In de les van vandaag heb ik geleerd waarom een pagina soms rommelig en soms meteen duidelijk is. Dat is geen toeval: ontwerpers gebruiken bepaalde principes. Die principes maken een pagina niet alleen mooier, ze zorgen er ook voor dat gebruikers de pagina makkelijker kunnen gebruiken en er meer betrokken bij zijn.

De les bestond uit drie grote onderwerpen: vorm, lay-out en stramien (grid). Ik zie ze als drie treden van klein naar groot. Eerst heb ik geleerd hoe ons brein losse vormen ziet, daarna hoe we die vormen op een pagina ordenen, en als laatste het onzichtbare skelet dat alles netjes bij elkaar houdt.

**1. Vorm: hoe ziet ons brein vormen? (Gestalt)**

Onze ogen zien eigenlijk alleen kleuren, lijnen en punten. Toch zien we geen chaos, maar letters, knoppen, vlakken en gezichten. Dat doet ons brein. Het brein ordent losse onderdelen automatisch tot één geheel. Dit idee heet Gestalt. Het is een Duits woord en betekent ongeveer "hele vorm".
De docent liet dit op een heel eenvoudige manier zien: met alleen een paar verticale lijnen. De lijnen waren steeds hetzelfde, alleen hun plek veranderde. Toch zagen we elke keer iets anders. Daardoor begreep ik: hoe we een element zien, hangt minder af van hoe het eruitziet, en meer van waar het staat en hoe het zich verhoudt tot de elementen eromheen.

Dit zijn de gestaltprincipes die ik heb geleerd:

- Symmetrie: Als je een lijn door het midden trekt, zijn de twee kanten elkaars spiegelbeeld. Symmetrische ontwerpen voelen rustig, ordelijk en een beetje statisch.

- Balans: Balans betekent dat er aan beide kanten evenveel "visueel gewicht" is. Eerst dacht ik dat alles symmetrisch moest zijn voor balans, maar dat klopt niet. De docent liet drie lijnen van verschillende lengte zien en het geheel zag er toch in balans uit. Een groot element aan de ene kant en twee kleine elementen aan de andere kant kunnen dus ook in evenwicht zijn. Dat heet asymmetrische balans, en het ziet er meestal levendiger uit dan symmetrie.

- Nabijheid: Dingen die dicht bij elkaar staan, ziet ons brein als een groep. Dingen die ver uit elkaar staan, zien we als losse onderdelen. Op het web is dit heel belangrijk: een kop moet dicht bij zijn eigen tekst staan en verder van het volgende onderdeel. Anders weet de gebruiker niet welke kop bij welke tekst hoort.

- Gelijkheid: Dingen die op elkaar lijken (dezelfde kleur, vorm of grootte) zien we ook als een groep. Als alle links op een pagina dezelfde kleur hebben, herkent de gebruiker ze allemaal zodra hij er één kent.

- Gemeenschappelijkheid: Dingen die binnen hetzelfde kader, vlak of dezelfde achtergrondkleur staan, lijken bij elkaar te horen. Daarom lezen we de afbeelding, de kop en de knop in een kaart als "één ding".

- Continuïteit: Het oog wil een lijn of een pad volgen. Als we twee lijnen zien die elkaar kruisen, zien we geen vier korte stukjes, maar twee lange, doorlopende lijnen.

- Closure / afsluiting: Ook als een vorm niet helemaal gesloten is, ziet ons brein hem als gesloten. Toen de docent een horizontale lijn boven de verticale lijnen zette, zagen we ineens kolommen en deuren.

- Ingevulde hiaat: Dit lijkt veel op afsluiting. De docent liet alleen de drie hoeken van een driehoek zien, maar iedereen zag een driehoek. Ons brein vult de ontbrekende stukken zelf in.

- Vorm / restvorm: Dit vind ik het interessantste principe. De ruimte rond een vorm vormt zelf ook een vorm. Toen de docent de lijnen in paren zette, werd de ruimte tussen de paren ook een vorm. Het citaat van Josef Albers in de slides gaat hier ook over: in modern ontwerp krijgen de "negatieve" elementen, dus de lege ruimtes, een actieve rol. Mijn conclusie: witruimte is geen verspilde ruimte, maar een onderdeel van het ontwerp.

**2. Lay-out: elementen ordenen als een verhaal**

De zin die ik het best heb onthouden: "Een lay-out is een ordening van elementen die samen een verhaal vertellen." Een lay-out maken is dus niet zomaar elementen op een pagina zetten. Je bouwt een volgorde met een begin, een midden en een einde.

Bij lay-out heb ik drie woorden geleerd:

- Ordening: Elementen in logische groepen en in een volgorde zetten.

- Hiërarchie: Het oog van de gebruiker over de pagina leiden, in de volgorde van belangrijkheid. Het belangrijkste moet je als eerste zien, het minst belangrijke als laatste. Dat doe je met drie middelen: positie (wat bovenaan en links staat, lees je eerst), maat (wat groot is, zie je eerst) en kleur (wat donker of fel is, valt op).

- Flow: De route die het oog over de pagina volgt. De docent zette genummerde cirkels van 1 tot 7 op een website (Eames Pavilions) en liet zien in welke volgorde het oog de pagina leest. Eerst kijken we naar de grote foto, dan naar de grote titel en pas als laatste naar de kleine teksten. In een goed ontwerp is die volgorde geen toeval, maar door de ontwerper gepland.

**3. Stramien: het onzichtbare skelet - grid**

Een stramien is een grid. Net als het skelet van een gebouw zie je het als gebruiker niet, maar alles is erop gebaseerd. Een grid bestaat uit drie dingen: kolommen, vaste maten / verhoudingen en zichtlijnen: de onzichtbare lijnen waarop elementen worden uitgelijnd. Een grid geeft een ontwerp structuur en consistentie. Daardoor wordt de pagina één geheel en is hij makkelijker te begrijpen voor de gebruiker.

Eerst dacht ik dat een grid de ontwerper beperkt. Maar het idee van Charles Eames in de slides zegt precies het tegenovergestelde: juist de strengheid van het systeem maakt het mogelijk om de ruimte vrij te gebruiken. Zo begrijp ik het: als de regels vastliggen, hoef je niet bij elk element lang na te denken over "waar zet ik dit neer?", en houd je meer energie over voor creativiteit.

Verhoudingen

Een grid bestaat niet alleen uit lijnen, maar ook uit de verhoudingen tussen maten. De architect Le Corbusier ontwikkelde een systeem van verhoudingen dat gebaseerd is op de maten van het menselijk lichaam: de Modulor. Sommige ontwerpers gebruiken de gulden snede. Het belangrijkste is dat de maten niet willekeurig zijn, maar bij elkaar passen.

Soorten grids

Ik heb vier soorten grids geleerd:

- Modular grid: met kolommen én rijen, zoals ruitjespapier. Het is consistent, maar laat ook ruimte voor creativiteit. Je ziet het vaak bij posters en galerijen.
- Column grid: alleen verticale kolommen. Het verbetert de leesbaarheid en de hiërarchie en werkt goed op verschillende schermformaten. Dit is het grid dat op het web het meest wordt gebruikt.
- Hierarchical grid: een vrijer grid dat de gebruiker met een duidelijke visuele flow door het ontwerp leidt.
- Baseline grid: horizontale lijnen waarop de tekst staat. Het zorgt voor netjes uitgelijnde tekst en een goede leesbaarheid.

Het meest gebruikte grid op het web is het grid met 12 kolommen, omdat 12 deelbaar is door 2, 3, 4 en 6. Dat maakt het heel flexibel. De ruimte tussen de kolommen heet gutter of gap. In CSS schrijf je dat ook echt met de eigenschap gap. De ruimte aan de rand van de pagina zijn de marges, dus margin.

Mobiel en desktop : Dezelfde inhoud kan op een telefoon en op een laptop in een ander grid staan. Op een telefoon is er meestal één kolom en staat alles onder elkaar. Op een laptop zijn er meer kolommen en kunnen elementen naast elkaar staan. In een voorbeeld uit de les stond het menu op desktop als lijst aan de linkerkant, en op mobiel was het een klein menu-icoon (☰) geworden. Dit past precies bij het idee "mobile-first" uit onze coderichtlijnen: begin met één kolom en voeg kolommen toe als het scherm breder wordt.

Spelen met het grid : Als laatste zei de docent: "play the grid". Een grid is een regel, maar je kunt die regel soms bewust breken. In sommige experimentele tijdschriften en websites lopen teksten buiten de kolommen of zijn ze heel groot. Om dat goed te laten werken, moet je het grid eerst goed begrijpen. Een regel breken zonder hem te kennen geeft chaos; een regel bewust breken kan juist een sterk ontwerp opleveren.

De laatste slide van de les vatte alles samen in drie punten. Volgens mij is dit het belangrijkste deel:

Contrast → maak je met maat en kleur. Wat anders is, moet er ook anders uitzien. In CSS: font-size, color, background-color.
Witruimte → maak je met marges en gaps. Groepen worden gescheiden door ruimte en de pagina krijgt lucht. In CSS: margin, padding, gap.
Hiërarchie → maak je met positie, maat en kleur. Het oog moet eerst het belangrijkste zien. In CSS: de volgorde in de HTML, font-size, font-weight, color. Contrast en hiërarchie lijken veel op elkaar, omdat ze allebei maat en kleur gebruiken. Ik leg het verschil voor mezelf zo uit: contrast zegt "dit is anders!", hiërarchie zegt "eerst dit, dan dat".

### **Opdracht 18–21: Opdracht en resultaat** 

In deze opdrachten moesten we onze schets steeds opnieuw bekijken, en elke keer maar op één ding letten: eerst witruimte, daarna hiërarchie en als laatste het grid.

Wat heb ik gedaan?
Ik heb mijn ontwerp getekend als een telefoonscherm. Bovenaan staat een bord met de titel en een START-knop. Daaronder loopt een weg met genummerde kaarten, links en rechts, met bomen en bankjes eromheen. De schets is niet op echt telefoonformaat, maar het gaat om de indeling.

Feedback van mijn klasgenoot:
Mijn klasgenoot heeft de witruimte anders verdeeld, zodat de pagina minder vol is. Voor de hiërarchie zei ze dat ik op de koppen moet letten: de titel moet duidelijk het grootst zijn, zodat je meteen ziet wat het belangrijkst is.

Grid:
Voor een groot scherm heb ik gekozen voor een grid met 6 kolommen. De titel staat in het midden, de kaarten staan om en om links en rechts, en de footer loopt over de hele breedte. Zo kan ik deze tekening later direct in mijn CSS gebruiken. 

Hieronder staat mijn desktop-schets met het grid.

## **Sprint 1 Week 3 ( 24 November Dinsdag )**

### **Practicum Everything images**

### **Wat heb ik vandaag voor mijn website gedaan?**

Vandaag heb ik de lay-out van mijn website gemaakt: de header, de START-knop en de acht kaarten in een zigzag.

Ik heb hiervoor **CSS Grid** en **Flexbox** gebruikt. 

#### 1. De header met Grid

**Grid** is een lay-outsysteem met rijen en kolommen, zoals een onzichtbare tabel.

Ik heb de header verdeeld in drie kolommen:

```css
header {
  display: grid;
  grid-template-columns: auto 1fr auto;
}
```

- `auto` = zo breed als de inhoud.
- `1fr` = neemt de overgebleven ruimte in.
- De middelste kolom zorgt voor ruimte tussen de elementen.

Daarna heb ik de elementen een plek gegeven:

| Element | CSS | Resultaat |
|---|---|---|
| Zon/maan | `justify-self: start` | Linksboven |
| Navigatie | `grid-column: 3` | Rechtsboven |
| Titel en ondertitel | `grid-column: 1 / -1` | Over de hele breedte |
| START | `grid-column: 1 / -1` en `justify-self: center` | In het midden |

**Wat betekent `grid-column: 1 / -1`?**

Het element loopt van de eerste tot de laatste kolomlijn. `-1` betekent de laatste lijn.

#### 2. Elementen centreren

Ik heb twee manieren geleerd om iets te centreren:

| CSS | Betekenis |
|---|---|
| `text-align: center` | Centreert de tekst |
| `justify-self: center` | Centreert het element zelf |

#### 3. De START-knop

```html
<a href="#stop-1">Start!</a>
```

Ik gebruik een `<a>` en geen `<button>`, omdat de bezoeker naar een andere plek op dezelfde pagina gaat.

`#stop-1` verwijst naar het element met `id="stop-1"`.

**Een fout die ik maakte:**

Ik was het `#` vergeten en schreef `href="stop-1"`.

Daardoor zocht de browser naar een andere pagina en kreeg ik de foutmelding `Cannot GET /stop-1`.

Ik heb geleerd dat het `#` belangrijk is voor een link binnen dezelfde pagina.

#### 4. Main in het midden zetten

Eerst gebruikte ik `max-width: 1100px` en `margin: 0 auto`.

Daarna heb ik dit aangepast, omdat ik geen margin wilde gebruiken om elementen te positioneren.

```css
body {
  display: grid;
  grid-template-rows: auto 1fr auto;
}

main {
  width: min(100% - 2rem, 60rem);
  justify-self: center;
}
```

- `body` gebruikt Grid voor de header, main en footer.
- `justify-self: center` zet main in het midden.
- `min()` kiest de kleinste van twee waarden.
- Op een klein scherm past main zich aan.
- Op een groot scherm wordt main maximaal `60rem` breed.

#### 5. De kaarten met Flexbox

**Flexbox** is een lay-outsysteem waarmee je elementen in één richting kunt plaatsen.

```css
main section {
  display: flex;
  flex-direction: column;
  gap: 2rem;
}
```

- `display: flex` activeert Flexbox.
- `flex-direction: column` plaatst de kaarten onder elkaar.
- `gap` maakt ruimte tussen de kaarten zonder margin.

#### 6. Het ontwerp van de kaarten

```css
main article {
  background-color: var(--stop-background);
  border: 0.15rem solid var(--stop-border);
  border-radius: 0.75rem;
  padding: 1.5rem;
  width: 85%;
}
```

Elke stop is een kaart.

In het lichte thema zijn de kaarten wit en in het donkere thema donkerblauw.

Ik gebruik **custom properties** voor de kleuren. Daardoor veranderen de kleuren automatisch met het thema.

#### 7. De zigzag maken

Ik wilde dat de acht kaarten afwisselend links en rechts staan, zoals een route op een kaart.

```css
main article:nth-of-type(odd) {
  align-self: flex-start;
}

main article:nth-of-type(even) {
  align-self: flex-end;
}
```

| CSS | Betekenis |
|---|---|
| `:nth-of-type(odd)` | Oneven artikelen: 1, 3, 5, 7 |
| `:nth-of-type(even)` | Even artikelen: 2, 4, 6, 8 |
| `align-self: flex-start` | Links |
| `align-self: flex-end` | Rechts |

**Waarom `nth-of-type` en niet `nth-child`?**

`nth-child` telt alle kinderen mee, bijvoorbeeld ook een `h2`.

`nth-of-type` telt alleen elementen van hetzelfde type. Daardoor blijft de zigzag goed werken.

#### 8. De 3D-nummers

Ik heb nummers toegevoegd aan de acht kaarten.

De nummers staan niet direct in de HTML. CSS maakt ze met een **counter** (teller).

| CSS | Functie |
|---|---|
| `counter-reset: stop` | Begint de teller bij 0 |
| `counter-increment: stop` | Telt bij elke kaart 1 op |
| `content: counter(stop)` | Laat het nummer zien |

Voor het 3D-effect gebruik ik meerdere `text-shadow`-lagen.

Elke schaduw verschuift een klein stukje naar rechts en beneden. Zo lijkt het nummer meer diepte te hebben.

Het nummer blijft tekst en is geen afbeelding.

#### 9. Responsive design – Mobile First

Ik heb eerst de lay-out voor een klein scherm gemaakt.

Daarna heb ik een media query toegevoegd voor grotere schermen.

```css
@media (min-width: 48em) {
  main article {
    width: 50%;
  }
}
```

- Op een klein scherm zijn de kaarten `85%` breed.
- Vanaf `48em` worden de kaarten `50%` breed.
- Daardoor is de zigzag op grotere schermen duidelijker.

Dit heet **Mobile First**: eerst ontwerpen voor kleine schermen en daarna uitbreiden voor grotere schermen.

#### Wat heb ik vandaag geleerd?

- Grid gebruik ik voor een lay-out met rijen en kolommen.
- Flexbox gebruik ik om elementen in één richting te plaatsen.
- Met `gap` maak ik ruimte zonder margin.
- Met `justify-self` en `align-self` kan ik elementen positioneren.
- Met `nth-of-type()` kan ik een zigzag maken.
- Met CSS counters kan ik automatisch nummers toevoegen.
- Met media queries maak ik mijn website responsive.
- Een kleine fout in een custom property, bijvoorbeeld `##142a52` in plaats van `#142a52`, kan meerdere onderdelen beïnvloeden.
- Bij het knippen en plakken van code moet ik controleren of er geen oude code achterblijft.

#### Bronnen en hulpmiddelen

- [MDN Web Docs](https://developer.mozilla.org/) – CSS Grid, Flexbox, `min()`, `nth-of-type()`, CSS counters en `text-shadow`.
- HWIVI-richtlijnen van de docent.
- [The A11Y Project](https://www.a11yproject.com/) – Toegankelijke en verborgen headings.
- Claude (Anthropic) – Hulp bij het schrijven, begrijpen en verbeteren van de code.
- hatGPT (OpenAI) – Hulp bij het structureren en schrijven van mijn learning log in Markdown.



## **Sprint 1 Week 3 Les 1  ( 23 November Maandag )**

### **Bi-weekly geek 1**
Tijdens de Bi-weekly Geek hebben we in teams ethische vragen over het internet van het bord besproken, zoals "Is toegang tot het internet een mensenrecht?", en die opgesplitst in deelvragen. Daarna hebben we verschillende onderzoeksmethodes geleerd, zoals Literature Study, Expert Interview en Guideline Conformity Analysis, en voor elke deelvraag gekozen welke methode het beste past.
![alt text](readme-images/biweeklygeek2.JPG)
![alt text](readme-images/biweeklygeek3.JPG)
![alt text](readme-images/biweeklygeek1.JPG)

### **Naar een responsive design**

#### **Opdracht – Van one column layout naar een responsive design**

Ik heb mijn eigen website zelf onderzocht. Ik heb in Chrome DevTools (Toggle device toolbar) mijn website op een smal scherm bekeken en het scherm daarna langzaam breder gemaakt.

##### Wat zag ik?

- Op een kleine telefoon past de bovenste rij net, maar de knop voor licht en donker is veel te groot. Er staat een groot kader omheen, met het woord "Theme" erboven.
- Op een nog smaller scherm schuift de maan onder de zon. Het kader wordt dan lang en het ziet er rommelig uit.
- "Learning Log" past niet meer op één regel en breekt in twee stukken.
- Tussen de grote titel en de zin eronder zit veel lege ruimte. Ze horen bij elkaar, maar ze staan ver uit elkaar.
- Op een klein scherm is er aan de randen van de bovenkant veel lege ruimte. Die ruimte zou ik beter kunnen gebruiken.
- Op een groot scherm staan de kaarten in het midden en is er aan de zijkanten veel lege ruimte. Het ziet er een beetje leeg uit.

##### Wat kan ik veranderen?

- De knop voor licht en donker kleiner maken, zodat de zon en de maan gewoon naast elkaar staan, zonder groot kader.
- De woorden in het menu iets dichter bij elkaar zetten.
- De titel en de zin eronder dichter bij elkaar zetten.
- Op een klein scherm minder lege ruimte aan de randen laten.
- Op een groot scherm de lege ruimte aan de zijkanten beter gebruiken.

![alt text](readme-images/responsive.png)
![alt text](<readme-images/responsive 2.png>)

#### **Opdracht – Responsive voorbeelden zoeken**

In deze opdracht moesten we drie interessante voorbeelden van responsive design zoeken en kijken hoe een website verandert op een groot scherm en op een telefoon.

Wat heb ik gezien?
Bij OTTO verandert het menu: op een groot scherm zie je alles, op een telefoon zit het achter een menuknop. De producten staan op een groot scherm naast elkaar en op een telefoon onder elkaar. De animatie is er alleen op een groot scherm.
Bij Alister staan de kaarten op een groot scherm naast elkaar, met foto's als versiering en schuine animaties. Op een telefoon staan de kaarten onder elkaar en zijn de animaties weggehaald.
Bij Attio zijn het eigenlijk de aanpassingen die we al kennen. Het lijkt alsof alle tekst en kaarten gewoon ergens anders neergezet zijn. Op een slimme manier, zonder het ontwerp veel te veranderen. De teksten staan onder elkaar, en op één plek naast elkaar. Alleen dat is aangepast. De animaties en effecten zijn meestal niet weggehaald. Dat is hier een andere manier van kijken.

Vanuit ontwerp bekeken:
OTTO: Op een groot scherm zijn de producten niet even groot; de tafel is groter. Toch ziet de pagina er in balans uit, dus het is asymmetrische balans. Op een telefoon staat alles in één kolom met grote foto's; je ziet eerst het product, de hiërarchie is heel duidelijk.
Alister: De zigzag-kaarten laten het oog van rechts naar links en van links naar rechts gaan; dat geeft een mooie flow. Op een telefoon zijn de versierfoto's weg, dus er is meer witruimte en de pagina wordt rustiger. Maar de pagina verliest ook een beetje zijn karakter.
Attio: De teksten, kleuren en de manier waarop de foto's staan, zijn op elk scherm hetzelfde. Daardoor voelt het op een telefoon nog steeds als dezelfde website. De onderdelen veranderen van plek, maar blijven dicht bij elkaar staan, dus je ziet ze nog steeds als één groep (nabijheid).

**Hieronder staan de screenshots van de drie voorbeelden die ik hierboven heb beschreven, telkens op een groot scherm en op een telefoon.**

https://ottoobjects.com/
![alt text](readme-images/vase/1.1.png)
![alt text](readme-images/vase/1.2.png)
![alt text](readme-images/vase/1.3.png)
![alt text](readme-images/vase/1.4.png)
![alt text](readme-images/vase/1.5.png)

https://www.alisteragency.ca/
![alt text](readme-images/alister/2.1.png)
![alt text](readme-images/alister/2.2.png)
![alt text](readme-images/alister/2.3.png)
![alt text](readme-images/alister/2.4.png)
![alt text](readme-images/alister/2.5.png)

https://offsite.attio.com/
![alt text](readme-images/attio/3.1.png)
![alt text](readme-images/attio/3.2.png)
![alt text](readme-images/attio/3.3.png)
![alt text](readme-images/attio/3.4.png)



### **Wat heb ik vandaag voor mijn website gedaan?**

#### **Lettertypekeuze** 

Mijn website vertelt het boek Atomic Habits op een speelse manier, en er komen ook mijn eigen tekeningen in. Daarom zocht ik voor de titels een lettertype dat op handschrift lijkt, speels is maar toch goed leesbaar. Ik heb vier lettertypes (Caveat, Patrick Hand, Fredoka en Shantell Sans) naast elkaar vergeleken met mijn eigen titel en heb voor Shantell Sans gekozen. De letters huppelen een beetje en passen heel goed bij mijn tekeningen. Voor langere teksten heb ik het eenvoudige en goed leesbare Nunito gekozen.

Ik heb de lettertypes niet met de embed code van Google toegevoegd, maar zelf op mijn website gezet met @font-face. Dat is de methode van onze docent, en zo gaan de gegevens van bezoekers ook niet naar Google. Daarbij heb ik het verschil tussen .ttf en .woff2 geleerd: het is hetzelfde lettertype, maar .woff2 is gecomprimeerd voor het web. Shantell Sans ging van 1,3 MB naar 167 KB, en mijn website laadt nu sneller.

Ik heb ook een fout gemaakt: ik had een extra komma gezet na de selector h1, h2, h3, waardoor de regel helemaal niet werkte. Dankzij de rode lijntjes in VS Code heb ik de fout gevonden. Nu weet ik dat er na de laatste selector geen komma komt.

![alt text](readme-images/font-secenekleri.png)

Afbeelding: vergelijking van vier lettertypes met mijn eigen titel. Gemaakt met Claude (Anthropic). Lettertypes: Caveat, Patrick Hand, Fredoka en Shantell Sans (Google Fonts, SIL Open Font License).

#### **Achtergrond: kleurverloop (gradient)**

Ik kwam op het idee om de achtergrond van mijn website op een zonsondergang te laten lijken.
Daarvoor gebruik ik een **kleurverloop** (gradient: kleuren die zacht in elkaar overlopen)
van roze bovenaan, via perzik, naar crème onderaan.
In het donkere thema wordt het een avondlucht: van paars naar nachtblauw.

Ik heb drie custom properties gemaakt (`--sky-top`, `--sky-middle`, `--sky-bottom`),
elk met `light-dark()`, en die gebruik ik in de `body` met **`linear-gradient()`**
(een CSS-functie die kleuren in een rechte lijn laat overlopen; `to bottom` = van boven naar beneden).

Bron: https://developer.mozilla.org/en-US/docs/Web/CSS/gradient/linear-gradient


## **Sprint 1 Week 2 Voorbereiding voor Maandag ( 22 November Zondag )**

### **Bi-weekly Geek 1 Voorbereiding** 

How Does the Internet Work? (Video van BBC) 

1. The Data Deluge (De grote hoeveelheid data)

Elke dag delen mensen ontzettend veel informatie op het internet. We uploaden miljoenen uren aan video's op YouTube en plaatsen miljoenen berichten en foto's op sociale media. Samen produceren we elke dag enorme hoeveelheden data.

2. The Internet Backbone (De ruggengraat van het internet)

In de video bezoeken we Telehouse North in Londen. Dit is een belangrijk onderdeel van de infrastructuur van het internet. In het gebouw staan veel computers, kabels en koelsystemen.

3. Origins of the Internet (Het ontstaan van het internet)

Het internet begon in 1969 in Amerika. Het Amerikaanse ministerie van Defensie wilde computers van verschillende universiteiten met elkaar verbinden. Zo konden onderzoekers gemakkelijker informatie delen en samenwerken.Daarom ontwikkelden ze een netwerk met de naam ARPANET.Op 29 oktober 1969 werd het eerste bericht verstuurd van de University of California in Los Angeles naar het Stanford Research Institute. Ze wilden het woord 'LOGIN' versturen, maar het systeem liep vast na de eerste twee letters: 'LO' :)

4. The Global Network (Het wereldwijde netwerk)

Wat begon met een paar computers, groeide later uit tot een wereldwijd netwerk. In de video wordt verteld dat er meer dan 1,2 miljoen kilometer aan onderzeese kabels ligt. Deze kabels verbinden landen en grote servergebouwen met elkaar.Twee belangrijke personen in de ontwikkeling van het internet zijn Vint Cerf en Robert Kahn. Zij hebben een belangrijke bijdrage geleverd aan de manier waarop verschillende netwerken met elkaar kunnen communiceren.

5. Internet vs. World Wide Web – Het verschil

Het internet is de infrastructuur die computernetwerken met elkaar verbindt, terwijl het World Wide Web een systeem is waarmee we via het internet websites en informatie kunnen bekijken.

6. Data Packet Transmission (Het versturen van datapakketjes)

Als we bijvoorbeeld een video willen bekijken, wordt de informatie niet als één groot bestand in één keer verstuurd. Dat zou veel tijd kunnen kosten en voor vertraging kunnen zorgen.Daarom wordt de informatie verdeeld in kleine datapakketjes. Deze pakketjes kunnen via verschillende routes reizen. Wanneer ze bij ons apparaat aankomen, worden ze weer in de juiste volgorde gezet.

7. Challenges of Information 

Het internet maakt het gemakkelijk om informatie te delen, maar niet alle informatie is betrouwbaar.Een belangrijk probleem is nepnieuws (fake news). Dit is onjuiste of misleidende informatie die zich snel via het internet kan verspreiden.Een ander probleem is de echokamer (echo chamber). Dit betekent dat mensen vooral informatie en meningen zien die bij hun eigen ideeën passen. Daardoor horen ze minder vaak andere meningen en wordt het moeilijker om kritisch te denken.Het is daarom belangrijk om feiten, meningen en nepnieuws van elkaar te kunnen onderscheiden.

Artikel 1 – The Cloud Crash

Op 20 oktober 2025 was er een grote storing bij Amazon Web Services (AWS), een bedrijf dat clouddiensten aanbiedt. De storing duurde ongeveer 15 uur en meer dan 2.000 bedrijven werden getroffen. Veel bekende apps en websites, zoals Snapchat, Roblox, Signal en Duolingo, werkten niet goed. Sommige mensen konden niet werken en examens werden uitgesteld.Deze storing laat zien hoe afhankelijk het internet is van een paar grote technologiebedrijven. Amazon, Microsoft en Google hebben samen ongeveer 60% van de wereldwijde markt voor cloudcomputing. Veel websites en apps gebruiken hun servers en technologie. Als één van deze bedrijven problemen heeft, kunnen veel andere diensten tegelijk uitvallen.Het internet lijkt misschien digitaal, maar het is afhankelijk van fysieke infrastructuur, zoals datacenters, servers en glasvezelkabels. Vooral Europa is sterk afhankelijk van Amerikaanse technologiebedrijven. Dit kan gevaarlijk zijn voor belangrijke diensten, zoals ziekenhuizen, banken en overheden.Volgens het artikel moet Europa daarom minder afhankelijk worden van buitenlandse bedrijven. Dat kan door eigen cloudinfrastructuur te ontwikkelen, verschillende aanbieders te gebruiken en open standaarden te ondersteunen.

- Het artikel laat zien hoe afhankelijk het internet is van grote technologiebedrijven. Volgens de schrijver moeten landen meer controle krijgen over hun eigen digitale infrastructuur, zodat ze minder afhankelijk zijn van buitenlandse bedrijven.

Artikel 2 – Tim Berners-Lee: The Future of the Web

Tim Berners-Lee bedacht het World Wide Web in 1989. Zijn doel was om een open, gratis en toegankelijk web te maken waar iedereen informatie kon delen. Maar volgens hem is het web in de loop der jaren sterk veranderd. Grote technologiebedrijven, zoals Google en Facebook, hebben steeds meer macht gekregen. Ze verzamelen persoonlijke gegevens en verdienen geld met advertenties. Sociale media gebruiken algoritmes om mensen zo lang mogelijk online te houden. Dit kan leiden tot verslaving, polarisatie en de verspreiding van verkeerde informatie. Volgens Berners-Lee is technologie niet neutraal. De manier waarop een website wordt ontworpen, beïnvloedt het gedrag van gebruikers. Daarom moeten ontwerpers niet alleen aan winst denken, maar ook aan de belangen van mensen. Om het web te verbeteren, werkt Berners-Lee aan een project dat Solid heet. Met Solid kunnen gebruikers zelf bepalen waar hun persoonlijke gegevens worden bewaard en met wie ze deze delen. Zo krijgen mensen meer controle over hun eigen informatie.Hij maakt zich ook zorgen over de snelle ontwikkeling van kunstmatige intelligentie (AI). Volgens hem moeten wetenschappers samenwerken om AI veilig en verantwoord te ontwikkelen.

- Het web is gemaakt voor iedereen, maar grote bedrijven hebben nu veel macht. Berners-Lee vindt dat gebruikers weer meer controle moeten krijgen over hun gegevens.


## **Sprint 1 Week 2 Les 3 (20 December 2026 Vrijdag )**

## **Sprint 1 Week 2 Les 2 (18 December 2026 Woensdag )**


### Wat heb ik vandaag voor mijn website gedaan?

#### Licht en donker thema

Mijn website heeft een licht thema (zonsondergang) en een donker thema (avondlucht).Bezoekers kunnen kiezen met de zon- en maanknop linksboven.

**Hoe werkt het?**

1. Alle kleuren staan als **custom properties** (eigen variabelen in CSS die met `--`beginnen, zodat ik een kleur op één plek kan aanpassen) in de `html`-selector. Ik gebruik **`light-dark()`** (een CSS-functie die de eerste kleur kiest in het lichte thema en de tweede in het donkere thema):
`--background: light-dark(#fbd0b0, #4a2545);`
2. De zon en maan zijn twee **radio buttons** (keuzerondjes waarvan je er maar één tegelijk kunt aanvinken) in een **`fieldset`** (een HTML-element dat bij elkaar horende formulier-elementen groepeert) met een **`legend`** (de naam of titel van die groep). Elke input heeft een **`aria-label`** (een naam voor schermlezers), omdat er alleen een icoon in het label staat en geen tekst.
3. Met **`:has()`** (een CSS-selector die een element kiest als er iets bepaalds in zit) kijkt de CSS welke knop is aangevinkt en verandert **`color-scheme`** (de instelling die zegt of de pagina licht of donker is): `html:has([value="dark"]:checked) { color-scheme: dark; }` Daardoor kiest `light-dark()` overal de donkere kleur.
4. De iconen zijn **inline SVG's** (tekeningen in code die direct in de HTML staan, zodat ik hun kleur met CSS kan veranderen), uit de les "Light en dark iconen". Hun kleur komt uit een custom property, dus ze veranderen mee met het thema.

**Wat heb ik geleerd?**
Eerst gebruikte ik `@media (prefers-color-scheme: dark)` (een media query die alleen kijkt naar de instelling van de computer). Die reageert niet op een knop op de website. Met `light-dark()` werkt het wel. Ook had ik de `html:has()`-regels per ongeluk binnen de `html { }`-regel gezet.
Toen werkte er niets. Ik heb geleerd dat `{ }` de grens van een CSS-regel is.

**Bronnen:** Practicum Light & Dark theme (Vasilis), Feather Icons (MIT), MDN (`light-dark()`, `:has()`). Gemaakt met hulp van Claude.

## **Sprint 1 Week 2 Practicum Light & Dark Theme (17 December 2026 Dinsdag )**

### **Oefening 1: Light & Dark 101**

Vandaag heb ik geleerd hoe ik een licht en donker thema maak voor mijn website. Eerst heb ik de CodePen van de docent geforkt, zodat ik een eigen kopie had.

Om alle kleuren op één plek te bewaren, heb ik custom properties gemaakt in de html-selector. Ik heb ze in html gezet, omdat waarden die daar staan worden geërfd door alle elementen op de pagina.

 **Custom property:** een variabele die begint met -- en waarvan ik zelf de naam bedenk. Ik sla een waarde één keer op en kan die daarna overal opnieuw gebruiken.

```css 
html {
  --background: Honeydew;
  --color: DarkSlateGray;
  --border-color: MediumSeaGreen;
  --color-h1: SeaGreen;
}
```

Daarna heb ik deze kleuren gebruikt in de body en de h1.

 **var():** leest de waarde van de custom property die tussen de haakjes staat. Ik heb var() gebruikt, zodat ik een kleur maar op één plek hoef aan te passen en alles automatisch meeverandert.

```css
body {
  background-color: var(--background);
  color: var(--color);
  border-color: var(--border-color);
}
h1 {
  color: var(--color-h1);
}
```
Vervolgens heb ik color-scheme toegevoegd aan de html-selector.

 **color-scheme: light dark:** vertelt de browser dat mijn website zowel een licht als een donker thema ondersteunt. Zonder deze regel werkt light-dark() niet.

```css
html {
  color-scheme: light dark;
}
```

Tot slot heb ik elke kleur met de light-dark() -functie twee waarden gegeven en een groen bosthema gekozen. De tekstkleur en achtergrondkleur zijn elkaars tegenovergestelde, zodat de tekst in beide modi goed leesbaar is.

**light-dark(licht, donker):** kiest de eerste kleur als de computer in lichte modus staat en de tweede kleur in donkere modus.

```css
html {
  --background: light-dark(Honeydew, DarkSlateGray);
  --color: light-dark(DarkSlateGray, Honeydew);
  --border-color: light-dark(MediumSeaGreen, Teal);
  --color-h1: light-dark(SeaGreen, Aquamarine);
}
```

Ik heb het getest door in de instellingen van mijn laptop te wisselen tussen licht en donker. De kleuren veranderden goed.

![alt text](readme-images/lightdarkmodelight.png)

![alt text](readme-images/lightdrakmodedark.png)

### **Oefening 2: Twee thema's (KittenMania)**

Ik heb voor die opdracht een licht en donker thema gemaakt voor een kattenwinkel. Ik heb gekozen voor een oranje thema met simpele kleuren.

Custom properties in de `html`-selector
Bovenaan in de CSS stond al `color-scheme: light dark;` en de code voor de radio buttons (auto / licht / donker). Daaronder heb ik mijn eigen custom properties gemaakt. Ik heb ze in de `html`-selector gezet, omdat waarden die daar staan worden geërfd door alle elementen op de pagina.

> **Custom property:** een variabele die begint met `--` en waarvan ik zelf de naam bedenk. Ik sla een waarde één keer op en kan die daarna overal opnieuw gebruiken.

**`light-dark(licht, donker)`:** kiest de eerste kleur in de lichte modus en de tweede kleur in de donkere modus.

```css
html {
  color-scheme: light dark;

  --background: light-dark(SeaShell, Black);
  --color: light-dark(Black, SeaShell);
  --header: light-dark(Orange, SaddleBrown);
  --card: light-dark(PeachPuff, Sienna);
  --button: light-dark(DarkOrange, Orange);
  --button-text: Black;
  --button-hover: light-dark(Orange, Gold);
}
```

Bij `--button-text` heb ik geen `light-dark()` gebruikt. Zwarte tekst is in beide modi goed leesbaar op een oranje knop, dus één kleur is genoeg.

#### De custom properties gebruiken
Daarna heb ik de custom properties lager in de CSS gebruikt voor de pagina, de header, de kattenkaarten en de knop.

**`var()`:** leest de waarde van de custom property die tussen de haakjes staat. Zo hoef ik een kleur maar op één plek aan te passen en verandert alles automatisch mee.

```css
body {
  background-color: var(--background);
  color: var(--color);
}

header {
  background-color: var(--header);
}

article {
  background-color: var(--card);
}

article button {
  background-color: var(--button);
  color: var(--button-text);
}

article button:hover,
article button:focus-visible {
  background-color: var(--button-hover);
}
```

**`:hover` en `:focus-visible`:** `:hover` werkt als je met de muis over de knop gaat, `:focus-visible` als je de knop met het toetsenbord (Tab) selecteert. Zo zien ook mensen zonder muis welke knop actief is.

#### Waarom werken de radio buttons?
De radio buttons veranderen `color-scheme` naar `light` of `dark`. `light-dark()` kijkt naar `color-scheme` en kiest dan de juiste kleur. Mijn selectors gebruiken die kleur via `var()`. Daardoor werken de knoppen meteen, zonder extra code.

###### Fouten en wat ik heb geleerd
In het begin werkte de header niet. Dat kwam door drie fouten:

1. **Puntkomma's vergeten.** Zonder `;` weet CSS niet waar een regel eindigt, waardoor meerdere regels niet werkten.
2. **Een spatie tussen `light-dark` en `(`.** Een functie moet direct aan de haakjes vastzitten: `light-dark(...)`, niet `light-dark (...)`.
3. **`--card` niet gedefinieerd.** Ik gebruikte `var(--card)` in `article`, maar was vergeten de custom property in de `html`-selector te maken.

Ook heb ik geleerd dat de foto van de kat niet van kleur verandert. Dat is een afbeelding. Wat wel verandert, is de kaart (`article`) eromheen.

**Mijn les:** als iets niet werkt, controleer ik eerst de puntkomma's, de schrijfwijze en of de custom property echt in de `html`-selector staat.




## **Sprint 1 Week 2 Les 1 (16 December 2026 Maandag )**

### **1)Sprintplanning** 

Tijdens de sprintplanning hebben we in GitHub een Project Board aangemaakt voor onze repository. Hier hebben we een Todo-lijst gemaakt en alle taken toegevoegd die we tijdens deze sprint moeten uitvoeren.

### **2)Artikel Lezen**

Voor deze opdracht hebben we eerst geleerd hoe we een artikel op een goede manier kunnen lezen.Ik werd er opnieuw aan herinnerd dat het beter is om niet alles met een markeerstift te markeren. Daarnaast heb ik iets nieuws geleerd: onbekende woorden niet meteen opzoeken, maar verder lezen en me vooral richten op de algemene betekenis van de tekst. Daarna hebben we in groepjes een artikel gelezen. **Ons artikel was The Garden and the Stream van Mike Caulfield.** 

#### **Wat ik heb uit die artikel begrepen ?** 

De schrijver wil ons meegeven dat de methode voor het gebruik van internet goed is. Hij vraagt zich op hoe wij dit kunnen oplossen.
Hier geeft de schrijver op zijn eigen manier opnieuw betekenis aan de twee begrippen: Garden en Stream.
Een Garden is een plek waar we steeds nieuwe informatie kunnen toevoegen. Deze informatie wordt met elkaar verbonden en vormt uiteindelijk een samend geheel.Een Stream is anders. Het gaat hier vooral om gesprekken, meningen, discussiess. Mensen die later bij een discussie komen, begrijpen vaak niet waar het over gaat omdat ze de eerdere context missen.

Dit komt doordat informatie in een Stream op tijd wordt geordend (chronologisch), terwijl een Garden meer draait om een ruimte met verschillende verbindingen.

### **3)Verkenning Onderwerp**

#### **Opdracht 1 – Rangschikken**

Eerst heb ik samen met Annick twee websites gekozen: [nuel.pw](https://nuel.pw/) en [jen.dev](https://jen.dev/).We hebben met een formulier gekeken hoe webby deze websites zijn.Hieronder zet ik een foto van ons ingevulde formulier.

![Onderzoek van twee websites](readme-images/tweewebsite.jpg)

Daarna hebben we in een groepje van vier de vier websites met elkaar vergeleken. Samen hebben we gekozen welke website we het meest webby vonden en welke het minst webby was.

- **Meest webby:** [tamanotchi.world](https://tamanotchi.world/)
- **Minst webby:** [nuel.pw](https://nuel.pw/)

Hieronder zet ik ook een foto van onze tweede beoordeling.

![De meest en minst webby website](readme-images/meestminst.jpg)

#### **Opdracht 2 - Eigen verkenning**

De laatste tijd ben ik het boek Atomic Habits aan het lezen en ik ben bijna klaar. Daarom wil ik de acht belangrijke ideeën uit dit boek op een visuele en interessante manier laten zien in mijn Digital Garden. Ik wil vooral dat het de aandacht van mensen trekt.

De acht punten die ik wil gebruiken:
- Kleine stappen, grote veranderingen
- Systemen in plaats van doelen
- Gewoontes en identiteit
- De twee-minutenregel
- De invloed van je omgeving
- Gewoontes stapelen
- Je voortgang zichtbaar maken
- Slechte gewoontes veranderen
Inspiratie uit andere websites

In de websites die ik heb bekeken, waren er een paar dingen die ik leuk vond. Bijvoorbeeld de animaties van karakters, de hover-effecten op knoppen en sommige lettertypes. Ook vond ik de effecten en ideeën van een website met een game-thema interessant.

Mijn eigen content en bronnen : Ik wil vooral het boek Atomic Habits als bron gebruiken. Ik wil de ideeën uit het boek in mijn eigen woorden vertellen en met mijn eigen tekeningen laten zien.

Hoe wil ik mijn Digital Garden maken? : Ik wil een soort game map maken, waarin bezoekers een route kunnen volgen om meer over gewoontes te leren.Mijn idee is dat bezoekers door de kaart kunnen gaan en verschillende punten kunnen ontdekken. Zo kunnen ze niet alleen lezen, maar ook kijken, klikken en op een interactieve manier leren. Ik weet nog niet precies hoe alles eruit gaat zien. Tijdens het ontwerpen wil ik mijn ideeën verder ontwikkelen.

### **4)Check-out**

Deze opdracht heb ik samen met mijn klasgenoot Mats gemaakt.

#### **1. Wat is een Digital Garden?**

Een Digital Garden is een persoonlijke plek waar je je interesses, ideeën en experimenten kunt verzamelen en delen. Het is een plek die steeds kan groeien en veranderen.

Een gewone website is vaak gemaakt om informatie te geven over bijvoorbeeld een bedrijf, product of dienst. Een Digital Garden is juist persoonlijker. Je kunt er nieuwe dingen uitproberen en laten zien wat je leert of interessant vindt.

#### **2. Wat maakt een website webby?**

Vandaag hebben we verschillende websites bekeken. We hebben gezien dat animaties, interactie, toegankelijkheid, typografie en vormgeving een website webby kunnen maken. Ook is het belangrijk dat een website goed werkt op verschillende schermformaten.

Ik heb nog geen websites gevonden die mij inspiratie geven voor mijn eigen Digital Garden.

#### **3. Mijn eerste ideeën voor een Digital Garden**

Mijn eerste idee is geïnspireerd op het boek *Atomic Habits*. Ik wil de belangrijkste lessen uit dit boek op een interactieve en visuele manier aan bezoekers uitleggen. Zo kunnen mensen de ideeën uit het boek op een leuke manier ontdekken en leren.

Mijn klasgenoot Mats heeft een ander idee. Hij wil zijn zelfgemaakte foto's verzamelen en er een digitaal fotoboek van maken.

# **SPRINT 1**
Challenge: Ontwerp, realiseer en publiceer de eerste versie van jouw digital garden met HTML, CSS (en JS).









## **Sprint 0 Week1 Les2 (11 December 2026 )**







## **Sprint 0 Week1 Les3 (13 December 2026 )**



















## **Sprint 0 Week1 Les1 (9 December 2026 )**

# **SPRINT 0 (Getting a grip)**
Doel: Je richt de randvoorwaarden voor het project in: een repository in GitHub om in te werken, een manier om jouw persoonlijke website te publiceren, een projectboard, kwaliteitsafspraken et cetera.