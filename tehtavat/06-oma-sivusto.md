# Oppitunti 6 · Oma sivusto kasaan

**Tavoite:** tunnin lopussa oma sivustosi on kolmisivuinen, sillä on yhteinen navigointi ja footer, yksi valitsemasi komponentti, ja se on julkaistu GitHub Pagesissa. Linkki palautetaan Moodleen.

**Aikaa:** 3 × 45 min. Tehtävät 1–3 ovat pakollisia, 4 on valinnainen, 5 tehdään tunnin lopussa parin kanssa.

**Esimerkit, joita käytät:** `esimerkit/18-monisivuinen/` (rakenne, valikko, murupolku, footer), `esimerkit/19-kuvagalleria.html`, `esimerkit/20-valilehdet.html`, `esimerkit/15-polut-ja-kansiot.html` (kun jokin polku ei toimi).

---

## 0. Ennen aloitusta (5 min)

1. GitHub → oma repo → **Sync fork → Update branch**.
2. VS Code → Source Control → **Pull**. Kansioon `esimerkit/` ilmestyy 18, 19 ja 20 ja kansio `tehtavat/`.
3. Avaa `esimerkit/18-monisivuinen/index.html` selaimessa. Kavenna ikkunaa: valikko muuttuu napiksi. Tämä on tunnin malli.

## Yksityisyys: mitä julkiselle sivulle EI laiteta

Sivustosi on julkinen koko internetille ja jää hakukoneisiin vuosiksi. Hakurobotit keräävät sivuilta puhelinnumeroita ja sähköposteja roskaposti- ja huijauslistoille.

**Älä laita sivulle:**
- omaa puhelinnumeroa
- omaa sähköpostiosoitetta (ei myöskään muodossa `etunimi [at] gmail.com`, robotit osaavat senkin)
- kotiosoitetta, syntymäaikaa, henkilötunnusta, koulun tai työpaikan sisäisiä tietoja
- kuvia muista ihmisistä ilman heidän lupaansa (alaikäisistä ilman huoltajan lupaa)

**Laita sen sijaan:**
- linkki LinkedIn-profiiliin (tee profiili, jos ei ole: se on CV-sivuston luonteva pari)
- linkki GitHub-profiiliin (sinulla on jo)
- harrastus- tai seurasivulle seuran virallinen some (Instagram, Facebook) tai seuran yleinen sähköposti, ei oman huoltajan numeroa
- yhteydenottolomake, joka oppitunnilla 7 kytketään lähettämään viesti sinulle ilman, että osoitteesi näkyy sivulla

Esimerkissä 18 Kuopion Kiekkokerhon puhelin ja sähköposti ovat **yhdistyksen** yleisiä yhteystietoja, eivät kenenkään henkilökohtaisia. Se on sallittu malli. Kuvitteelliset tiedot (`info@esimerkki.fi`, `040 123 4567`) käyvät harjoituksessa, oikeat omat eivät.

Jos olet jo laittanut numeron tai osoitteen sivulle: poista se ja pushaa. Huomaa, että se jää Gitin historiaan. Jos se pitää saada pois kokonaan, pyydä opettajalta apua (`git filter-repo`), älä jätä sitä.

## 1. Kolme sivua (45 min)

Sivustosi aihe on sama kuin oppitunnilla 4 valitsit (CV, harrastus, seura, kotisivu). Tee repon **juureen** kolme sivua:

| Tiedosto | Sisältö | Vähintään |
|---|---|---|
| `index.html` | Etusivu (on jo olemassa, muokkaa) | hero tai esittelykappale, linkit kahdelle muulle sivulle |
| `sivu2.html` → nimeä aiheen mukaan, esim. `tyokokemus.html`, `joukkueet.html`, `galleria.html` | pääsisältö | yksi `h2`, yksi kortti- tai taulukko-osio |
| `yhteystiedot.html` | yhteystiedot | `address` ilman henkilökohtaisia tietoja (ks. kohta "Yksityisyys"), linkit some-profiileihin, yhteydenottolomake (saa olla `action="#"`) |

Vaatimukset kaikille kolmelle:

- Sama `<header>`, `<nav>` ja `<footer>` joka sivulla. Kopioi ne esimerkistä 18 ja vaihda sisältö omaksi. **Korjaa polut:** sivusi ovat juuressa, joten `css/tyyli.css` ja `img/…`, ei `../../`.
- Navissa `aria-current="page"` sillä linkillä, joka on kyseinen sivu. Tarkista jokaiselta sivulta erikseen.
- `<title>` on joka sivulla eri ja kertoo sivun nimen: `Yhteystiedot – Maijan CV`.
- Murupolku kahdelle alasivulle (ei etusivulle).
- Tiedostonimet pienillä kirjaimilla, ei ääkkösiä, ei välilyöntejä.

**Tarkistus:** klikkaa kaikki navin linkit läpi jokaiselta sivulta. Kuusi linkkiä, kaikki toimivat, logo vie etusivulle.

## 2. Hampurilaisvalikko ja footer (30 min)

1. Kopioi `esimerkit/18-monisivuinen/sivusto.css` kansioon `css/` nimellä `sivusto.css`.
2. Linkitä se joka sivulla `tyyli.css`:n **jälkeen**:
   ```html
   <link rel="stylesheet" href="css/tyyli.css">
   <link rel="stylesheet" href="css/sivusto.css">
   ```
3. Lisää naviin checkbox + label kuten esimerkissä 18. Kavenna ikkunaa alle 640 px ja testaa: nappi näkyy, lista aukeaa ja sulkeutuu.
4. Footer kolmella palstalla: yhteystiedot, sivut, linkit. Vaihda sisältö omaksi. Kavenna: palstat menevät allekkain.
5. Muuta vähintään kaksi asiaa `sivusto.css`:ssä niin, että se näyttää sinun sivustoltasi (värit tulevat `tyyli.css`:n `:root`-muuttujista, joita olet jo säätänyt; vaihda esim. murupolun erotin, napin teksti, footerin palstaleveys).

**Miksi oma `sivusto.css` eikä kaikki `tyyli.css`:n loppuun?** Molemmat käyvät. Erillinen tiedosto pitää tyyli.css:n puhtaana, jolloin opettajan päivitykset eivät koskaan osu omiin riveihisi.

## 3. Yksi komponentti (30 min)

Valitse yksi ja toteuta se sivullesi **oikealla sisällöllä**, ei esimerkin tekstillä:

| Komponentti | Esimerkki | Sopii, kun sivullasi on |
|---|---|---|
| Kuvagalleria + lightbox | 19 | 4–8 kuvaa: portfolio, harrastus, tapahtumat |
| Välilehdet | 20 | 2–4 rinnakkaista sisältöä: hinnasto, lukujärjestys, kielet fi/en |
| Vaihtuva hero (kuva ↔ video) | 13 | yksi hyvä kuva ja lyhyt video |
| Korttiruudukko hover-nostolla | 09 | lista asioita: projektit, tuotteet, joukkueet |

Komponentin CSS saa olla `<style>`-lohkossa kyseisellä sivulla, jos sitä käytetään vain siellä. Jos sitä käytetään kahdella sivulla, se menee `sivusto.css`:ään.

**Kuvat:** omat kuvat kansioon `img/`, pienennä alle 500 kt (esim. squoosh.app tai Windowsin Kuvat-sovellus → Muuta kokoa). Nimeä pienillä kirjaimilla: `harjoitukset-2026.jpg`.

## 4. Valinnainen: 404-sivu ja tulostusnäkymä (jos aikaa jää)

- Tee `404.html` juureen (sama header ja nav, viesti "Sivua ei löytynyt" ja linkki etusivulle). GitHub Pages näyttää sen automaattisesti väärille osoitteille. Testaa: `…/luentomateriaali/eiole.html`.
- Avaa CV- tai yhteystietosivu → Ctrl+P → Esikatselu. Jos nav ja footer tulostuvat, lisää `sivusto.css`:ään `@media print { nav, body > footer, .valikko-nappi { display: none; } }`.

## 5. Julkaisu ja vertaisarviointi (25 min)

1. Commit ja push. Odota minuutti. Avaa `https://sinun-tunnus.github.io/luentomateriaali/`.
2. Avaa sivusto **puhelimella** tai DevToolsin laitetilassa (Ctrl+Shift+M, iPhone-leveys). Käy kaikki kolme sivua läpi.
3. Vaihda linkki parin kanssa. Pari tarkistaa listan ja kirjoittaa havainnot Moodleen:

```
PARIN SIVUSTO: ____________________  OSOITE: ____________________

[ ] Kaikki navin linkit toimivat jokaiselta sivulta (6 klikkausta)
[ ] aria-current on oikealla linkillä joka sivulla (näkyy korostuksena)
[ ] Puhelinleveydellä valikko on nappi ja aukeaa
[ ] Footer menee puhelimella yhteen palstaan
[ ] Murupolku näkyy alasivuilla, ei etusivulla
[ ] Komponentti toimii hiirellä JA Tab-näppäimellä
[ ] F12 → Console on tyhjä (ei punaisia 404-rivejä)
[ ] Kuvilla on alt-tekstit (F12 → Elements → img)
[ ] Title on eri joka sivulla (katso välilehden nimi)
[ ] Ei vaakavieritystä puhelimella
[ ] Sivulla EI ole henkilökohtaista puhelinnumeroa, sähköpostia tai osoitetta
[ ] Yhteystiedoissa on linkki LinkedIniin / GitHubiin / seuran someen

Paras asia parin sivustolla: ______________________________
Yksi parannusehdotus:       ______________________________
```

4. Korjaa parin löytämät virheet, commit, push.
5. Palauta Moodleen: oma Pages-osoite + parin tarkistuslista.

## Arviointi

| | Hyväksytty | Hyvä | Kiitettävä |
|---|---|---|---|
| Rakenne | 3 sivua, nav toimii | + murupolku, aria-current oikein | + 404-sivu tai print-tyyli |
| Responsiivisuus | sivu luettava puhelimella | + hampurilaisvalikko toimii | + ei vaakavieritystä, kuvat skaalautuvat |
| Komponentti | kopioitu ja toimii | + oma sisältö ja omat kuvat | + mukautettu ulkoasu, toimii näppäimistöllä |
| Laatu | Console tyhjä, ei henkilökohtaisia yhteystietoja | + alt-tekstit, title joka sivulla | + validaattori (validator.w3.org) ei virheitä |
| Git | pushattu Pagesiin | + commit-viestit kertovat mitä tehtiin | + vähintään 5 committia tunnin aikana |

## Yleisimmät ongelmat

| Oire | Korjaus |
|---|---|
| Sivu näkyy ilman tyylejä Pagesissa, koneella toimii | Polku alkaa `/`:llä tai kirjainkoko eroaa. Esimerkki 15. |
| Valikko ei aukea | `nav:has(…)` vaatii, että checkbox on `nav`-elementin sisällä. Tarkista `id` ja `for` täsmäävät. |
| Valikko näkyy aina napin kanssa | Media query puuttuu tai `sivusto.css` ladataan ennen `tyyli.css`:ää. |
| Murupolku näyttää navilta (keltainen tausta) | Luokka `murupolku` puuttuu `nav`-elementistä. |
| Footer ei mene palstoihin | `div.palstat` puuttuu tai palstat eivät ole sen suoria lapsia. |
| Lightbox avautuu mutta sivu hyppää | `.lightbox` ei ole `position: fixed`. |
| Console: 404 kuvalle | Tiedostonimi tai polku eroaa; katso Network-välilehdeltä mitä selain haki. |

## Mitä seuraavaksi

Oppitunti 7: lomake oikeasti lähettämään, saavutettavuus (kontrasti, näppäimistö, ruudunlukija), `<meta>`-kuvaukset, W3C-validaattori ja Lighthouse. Oppitunti 8: JavaScriptin ensikosketus, jossa tämän tunnin hampurilaisvalikko ja välilehdet tehdään uudestaan oikein.
