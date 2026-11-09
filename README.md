# Default-sivut · Sakky HTML-perusteet

Opettajan mallirepo, jonka opiskelija forkkaa omaksi projektikseen (ohje Moodlessa).

## Rakenne

```
index.html          etusivu, käyttää css/tyyli.css
css/tyyli.css       perusmalli: järkevä oletus JOKAISELLE HTML-elementille, KOKEILE-kommentit (oppitunti 5)
img/                kuvat (esimerkki 13 odottaa: icehockey.jpg, icehockey_tuupelaa.mp4)
esimerkit/          00 kokeilusivu (kaikki elementit) + CSS-esimerkkisivut 01–20
tehtavat/           tuntikohtaiset tehtäväohjeet (06-oma-sivusto.md)
```

## CSS-esimerkit (oppitunti 5)

Avaa `esimerkit/index.html`. Perusteet 01–08 seuraavat dioja, toteutusmallit 09–12 ovat valmiita malleja omaan projektiin:

| # | Sivu | Aihe |
|---|------|------|
| 00 | kaikki-elementit | kokeilusivu: jokainen elementti, ei omaa CSS:ää, 10 kokeilua tyyli.css:ään |
| 01 | kolme-tapaa | inline, style-lohko, ulkoinen tiedosto; säännön anatomia |
| 02 | valitsimet | elementti, luokka, id, jälkeläinen, lapsi, pseudoluokat, attribuutti, pseudoelementit |
| 03 | kaskadi | järjestys, spesifisyys, periytyminen, !important |
| 04 | laatikkomalli | content/padding/border/margin, box-sizing, lyhenteet, display |
| 05 | varit-ja-teksti | hex/rgb/hsl, px/rem/em/%/vw/clamp, Google Fonts, fonttipino |
| 06 | flexbox | rivi, gap, justify, align, flex: 1, wrap, header-malli |
| 07 | grid | fr, repeat, auto-fit + minmax, span, template-areas |
| 08 | responsiivinen | viewport, mobile first, media queryt, clamp, käyttäjän asetukset |
| 09 | korttiruudukko | hover-nosto, aspect-ratio, tagit pohjaan, focus-within |
| 10 | hero-ja-sticky-nav | koko sivun etusivumalli: sticky nav, hero, osiot |
| 11 | tumma-tila | CSS-muuttujat + prefers-color-scheme + data-theme |
| 12 | lomake-ja-taulukko | kaksipalstainen lomake, validointitilat, mobiilitaulukko |
| 13 | vaihtuva-hero | kuva ja video vuorottelevat (@keyframes), taustavideon attribuutit, käyttäjän valinta :has(:checked) |
| 14 | kolme-korttia | luentoesimerkki: 3 korttia flexillä, oma 14-kolme-korttia.css ilman muuttujia (ei tyyli.css:ää) |
| 15 | polut-ja-kansiot | suhteelliset polut kansiotasojen välillä: kaavio (img/polut-ja-kansiot.png), taulukko, yleiset virheet |
| 16 | katoava-kortti | luentoesimerkki: kortti nousee, kääntyy ja katoaa klikatessa; label+checkbox+:has(:checked), @keyframes forwards, alta paljastuva pino-kortti, ei JS:ää |
| 17 | erikokoiset-kortit | sama kolmen kortin rivi 7 kertaa, ainoa ero säiliön align-items (stretch / flex-start / center / flex-end), align-self, margin-top: auto, grid-vastine |
| 18 | monisivuinen/ | oppitunti 6: kolme sivua, yhteinen header/nav/footer, hampurilaisvalikko (:has), murupolku, 3-palstainen footer, sivusto.css |
| 19 | kuvagalleria | oppitunti 6: lightbox :target-pseudoluokalla, position: fixed, edellinen/seuraava |
| 20 | valilehdet | oppitunti 6: välilehdet radio + :has(#id:checked) |

## Tehtävät

`tehtavat/06-oma-sivusto.md`: oppitunnin 6 tehtävät (3 sivua, valikko+footer, yksi komponentti, julkaisu, vertaisarviointi) ja arviointitaulukko.

## tyyli.css:n rakenne

1 muuttujat (:root) · 2 nollaus · 3 teksti · 4 listat · 5 linkit · 6 media · 7 taulukot · 8 lomakkeet · 9 details/dialog · 10 sivun runko · 11 apuluokat (.kortti, .kortit, .ilmoitus, .tunniste, .nappi, .vain-ruudunlukija, .ohita, .vieritys, form.kaksi-palstaa) · 12 responsiivisuus · 13 tulostus · 14 tumma tila · 15 OMAT TYYLIT

## Opiskelijalle

1. Forkkaa tämä repo nimellä `luentomateriaali` (ohje: Forkkaus selitettynä -dokumentti Moodlessa). Julkaise Settings → Pages → Branch main / (root); osoite on `https://kayttajanimi.github.io/luentomateriaali/`.
2. Vaihda `index.html`:n title, h1 ja sisältö omaksi.
3. Muokkaa `css/tyyli.css`:n `:root`-muuttujia: värit ja fontit vaihtuvat kerralla.
4. Kopioi tarvitsemasi toteutusmalli `esimerkit/`-kansiosta omalle sivullesi.
5. Kirjoita omat CSS-säännöt `css/tyyli.css`-tiedoston loppuun otsikon `===== OMAT TYYLIT =====` alle. Älä muokkaa `esimerkit/`-kansiota: opettaja päivittää sitä, ja Sync fork tuo päivitykset ilman ristiriitoja, kun omat muutoksesi ovat omissa tiedostoissasi ja tyyli.css:n lopussa.
6. Hae opettajan päivitykset jokaisen tunnin alussa: GitHub → oma repo → **Sync fork → Update branch**, sitten VS Codessa Pull.
