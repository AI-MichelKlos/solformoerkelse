# 🌘 Solformørkelses-Missionen

Et lille browserspil til børn om **den delvise solformørkelse over Danmark den 12. august 2026**, hvor 80–88 % af solen bliver dækket. Det er den kraftigste solformørkelse i Danmark siden 2015 — og indtil 2048.

Lavet af **Michel Klos**.

**Spil det her:** https://ai-michelklos.github.io/solformoerkelse/

---

## Om spillet

Tager cirka 15 minutter. Kan spilles af én eller to sammen — man skriver sit navn i starten og får et diplom til sidst. Bygget til mobil, alt foregår med tryk og træk.

**Kapitel 1 — Tidsmaskinen**
Myte eller sandt om vikingernes ulv Sköll, den kinesiske drage, og formørkelsen der stoppede en krig.

**Kapitel 2 — Månemissionen**
Barnet trækker selv månen hen over solen med fingeren. Dækningsprocent, lysstyrke og temperatur ændrer sig live, og pointen bliver tydelig: 83 % dækket er stadig ikke mørkt. Bagefter en skyder der viser hvorfor det ikke sker hver måned — månebanen hælder 5 grader.

**Kapitel 3 — Mission Mørke**
Hvad sker der med fuglene, med temperaturen, og med lyspletterne under træerne? Slutter med det vigtigste: et sorteringsspil om hvad man må og ikke må kigge igennem.

Til sidst: diplom, live nedtælling til den 12. august kl. 20:04, og en huskeliste til selve dagen.

---

## Videoerne

Spillet har fem videopladser. Læg dine egne videoer i mappen `videos/` med **præcis disse filnavne**:

| Fil | Hvor i spillet | Indhold |
|---|---|---|
| `videos/1-intro.mp4` | Start af kapitel 1 | Månen glider ind foran solen |
| `videos/2-vikingemyten.mp4` | Midt i kapitel 1 | Ulven Sköll bider i solen |
| `videos/3-maanen-glider-ind.mp4` | Start af kapitel 2 | Set fra rummet: månens skygge rammer Jorden |
| `videos/4-dyrene-i-moerket.mp4` | Start af kapitel 3 | Fuglene bliver stille, lyset bliver gråt |
| `videos/5-solbriller.mp4` | Sikkerhedsdelen | Barn tager solformørkelsesbriller på |

Mangler en fil, viser spillet automatisk en kort tekstbeskrivelse i stedet — **spillet virker fint uden videoerne**.

Foretrækker du YouTube, kan du i stedet skrive et embed-link øverst i `index.html`:

```js
const VIDEOER = {
  intro: "https://www.youtube.com/embed/XXXXXXXXXXX",
  ...
};
```

Hold filerne under ca. 10 MB hver — GitHub Pages er ikke bygget til store videofiler, og siden skal loade hurtigt på mobil.

---

## Tilpas tallene

Tidspunkter og dækningsprocent gælder for København. Skal spillet bruges et andet sted i landet, rettes `FAKTA` øverst i `index.html`:

```js
const FAKTA = {
  dato:     "12. august 2026",
  start:    "19:10",
  maksimum: "20:04",
  slut:     "20:54",
  daekning: 83,                              // op til 88 % i Vestjylland
  maalTid:  new Date(2026, 7, 12, 20, 4, 0)  // bruges til nedtællingen
};
```

---

## Sådan lægger du det på nettet

1. Opret et nyt repository på GitHub, fx `solformoerkelse`, og sæt det til **Public**.
2. Upload `index.html`, `README.md` og mappen `videos/`.
3. Gå til **Settings → Pages**, vælg branch `main` og mappe `/ (root)`, og tryk Save.
4. Efter et minut eller to ligger spillet på `https://ai-michelklos.github.io/solformoerkelse/`.

---

## Teknisk

Én HTML-fil uden byggeværktøjer, uden frameworks og uden eksterne afhængigheder. Ingen cookies, ingen sporing, intet gemmes — navnet lever kun i browserens hukommelse, indtil siden lukkes.

Dækningsprocenten i månespillet regnes ud med den rigtige formel for arealet af overlappet mellem to cirkler, så tallet på skærmen svarer til, hvor meget af solskiven der faktisk er dækket. Maksimum er sat til 87 %, så det matcher virkeligheden i Danmark.

---

## Sikkerhed

Spillet lærer børn, at man **kun** må se på solen gennem briller mærket **ISO 12312-2** eller via et hulkamera. Almindelige solbriller, røget glas og kikkerter er farlige. Det gælder også, når det meste af solen er dækket.

---

## Kilder

- [Lex.dk — Solformørkelsen den 12. august 2026](https://lex.dk/solformørkelsen_den_12._august_2026)
- [Illustreret Videnskab — Delvis solformørkelse 2026](https://illvid.dk/universet/solsystemet/solformoerkelse/delvis-solformoerkelse-hvad-er-det-og-hvornaar-sker-det-i-danmark)
- [Science Museerne — Forbered dig til den delvise solformørkelse](https://sciencemuseerne.dk/om-science-museerne/nyhed/artikel/forbered-dig-til-den-delvise-solformoerkelse)

---

© 2026 Michel Klos. Fri til at bruge og dele i skoler, klubber og hjem.
