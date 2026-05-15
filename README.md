# 🐪 Kamelenrace

Een pubquiz-meets-racegame voor 2–8 teams. Twaalf verschillende rondetypes, racebaan-in-3D, levende data via Wikipedia & Open Trivia DB. Volledig in één HTML-bestand — geen build, geen install.

![Kamelenrace](https://img.shields.io/badge/teams-2--8-c44536) ![Rounds](https://img.shields.io/badge/round_types-12-FFB627) ![Pool](https://img.shields.io/badge/questions-500%2B-0F4C5C)

## 🚀 Op GitHub Pages zetten — drie stappen

1. **Maak een nieuwe GitHub-repository**
   ```
   https://github.com/new
   ```
   Geef hem bijvoorbeeld de naam `kamelenrace`. Public mag (en moet, voor de gratis Pages-tier).

2. **Upload `index.html` (en eventueel deze README)**
   - Op GitHub: klik **Add file → Upload files**, sleep `index.html` erin, **Commit**
   - Of via terminal:
     ```bash
     git clone https://github.com/JOUWNAAM/kamelenrace.git
     cd kamelenrace
     # Plaats index.html in deze map
     git add index.html
     git commit -m "Initial commit"
     git push
     ```

3. **Pages aanzetten**
   - Ga in je repo naar **Settings → Pages**
   - Onder *Source*: kies **Deploy from a branch** → **main** → `/ (root)` → **Save**
   - Na ±1 minuut staat je site live op:
     ```
     https://JOUWNAAM.github.io/kamelenrace/
     ```

Dat is alles. Geen Jekyll, geen build-step. Open de URL op je laptop en speel.

> 💡 **Tip:** voeg een `.nojekyll`-bestand toe (leeg bestand) als je iets vreemds ziet — dat zegt Pages om Jekyll over te slaan. Voor dit project niet nodig, maar handig om te weten.

## 🎮 Hoe speel je het

1. Voeg 2–8 teams toe. Klik op de dier-emoji om te wisselen.
2. Stel de **lengte** in (4–50 stappen). Tip: 10 voor een avond, 20+ voor een lange sessie.
3. Kies de **moeilijkheidsgraad** (Makkelijk / Normaal / Pittig / Expert) — dit beïnvloedt rekensommen, trivia, kaartlocaties en silhouetten.
4. Selecteer welke spelvormen mee mogen doen (minimaal 2 actief).
5. Klik **Start de race**.

Goed antwoord = stap vooruit. Eerste team bij de finishvlag wint.

## 🎲 De rondetypes

| Type | Wat? | Punten |
|---|---|---|
| 🧮 Rekensommen | Procedureel, schaalt met moeilijkheid | +1 stap goed |
| 🏛️ Hoofdsteden | Land → hoofdstad, met emoji-vlag | +1 stap goed |
| 🚩 Vlaggen Raden | Vlag → land (flagcdn + emoji-fallback) | +1 stap goed |
| 🗺️ Land Silhouet | Zwart silhouet → welk land? | +1 stap goed |
| 🏷️ Merk-Logo | Brand-mark zonder tekst (logoguessr-style) | +1 stap goed |
| 💰 Bedrijfsomzet | Slider 0–max, dichtste bij wint | +2 dichtst / +1 tweede |
| 🕰️ Tijdlijn | In welk jaar was X? Slider 1500–2026 | +2 / +1 |
| 🧠 Algemene Kennis | Open Trivia API + curated NL | +1 stap goed |
| ⏱️ 30 Seconden | Beschrijf 5 woorden, iedereen mag raden | +1 voor beschrijver én rader, per woord |
| 🎨 Tekenen & Raden | Pictionary op canvas | +1 voor tekenaar en goede rader |
| 🛰️ Wereldkaart | Klik op satellietkaart waar plek X ligt | +2 dichtst / +1 tweede |
| 🔥 Wat zoekt NL? | Wie scoort meeste Wikipedia-pageviews? | +3 / +2 / +1 |
| 📊 Top 5 Ranglijst | Rangschik 5 items in juiste volgorde | +1 stap per juist geplaatste positie |

## 🌐 Externe bronnen

Het spel gebruikt alleen gratis, key-loze API's en CDN's:

- **Wikipedia REST Pageviews API** (`wikimedia.org/api/rest_v1/...`) — live populariteitsdata
- **Open Trivia DB** (`opentdb.com`) — extra trivia-vragen
- **flagcdn.com** — landenvlaggen
- **simple-icons CDN** — text-loze brand marks
- **mapsicon via jsDelivr** — landsilhouetten
- **ESRI World Imagery** — satelliettegels voor de wereldkaart
- **OpenStreetMap** — straatkaart-modus
- **Google Fonts** — Bricolage Grotesque, Outfit, Caveat
- **Leaflet 1.9.4 + canvas-confetti 1.9.3** — kaart en feestjes

Geen account, geen API-keys, geen tracking.

## 🥨 Easter egg

8% kans per ronde dat een Duitse heer met snor, lederhose en Tirolerhoed in beeld verschijnt. Hij roept iets ("Donnerwetter!", "Prost!"). Veeg hem niet weg — hij gaat vanzelf.

## 🛠️ Aanpassen

Alle game-data zit als JavaScript-arrays bovenin het bestand:

| Pool | Aantal | Wat |
|---|---|---|
| `DUTCH_QUIZ` | 50 | NL algemene-kennis-vragen |
| `LOGOS` | 50 | Brand-marks (simple-icons slugs) |
| `REVENUES` | 40 | Bedrijfsomzetten voor slider |
| `HIST_EVENTS` | 64 | Historische gebeurtenissen + jaar |
| `MAP_TARGETS` | 54 | Steden/landmarks per moeilijkheid |
| `COUNTRY_DATA` | 68 | Landen met hoofdstad + ISO-code |
| `THIRTY_SECONDS` | 30 | Thema's voor 30 Seconden |
| `DRAW_WORDS` | 77 | Woorden om te tekenen |
| `POPULARITY_QUIZZES` | 25 | Categorieën met Wikipedia-onderwerpen |
| `RANKINGS` | 29 | Top-5 ranglijsten |

Voeg eigen vragen toe door regels aan de arrays toe te voegen. Geen ander codewerk nodig.

## 🔒 Privacy

Geen tracking, geen cookies, geen analytics. Alle externe calls zijn alleen voor inhoud (vlagafbeeldingen, Wikipedia views, etc.) en bevatten geen persoonsgegevens.

## 📜 Licentie

Doe ermee wat je wil. Brand-logo's blijven uiteraard eigendom van hun respectievelijke eigenaars.
