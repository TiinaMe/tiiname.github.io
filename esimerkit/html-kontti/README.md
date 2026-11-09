# Omien HTML-sivujen hostaus Docker-kontilla

Pienin mahdollinen esimerkki: nginx-palvelin kontissa tarjoilee `sivut/`-kansion tiedostot.

```
html-kontti/
├── Dockerfile        # miten image rakennetaan
├── compose.yaml      # sama asia yhdellä komennolla
└── sivut/
    ├── index.html
    ├── toinen.html
    └── tyyli.css
```

## Tapa 1: Dockerfile + docker-komennot

```bash
# 1. Rakenna image (nimi: omasivu)
docker build -t omasivu .

# 2. Käynnistä kontti taustalle, ohjaa portti 8080 -> 80
docker run -d --name omasivu -p 8080:80 omasivu

# 3. Avaa selain: http://localhost:8080

# 4. Lopetus ja poisto
docker stop omasivu
docker rm omasivu
```

Kun muokkaat sivuja, aja `docker build` uudelleen ja käynnistä kontti uudestaan.

## Tapa 2: Docker Compose

```bash
docker compose up -d --build   # rakenna ja käynnistä
docker compose down            # pysäytä ja poista
```

## Tapa 3: Ilman Dockerfileä (nopein kokeilu)

Ei buildia ollenkaan – kansio liitetään suoraan valmiiseen nginx-imageen:

```bash
docker run -d --name omasivu -p 8080:80 \
  -v "$(pwd)/sivut:/usr/share/nginx/html:ro" nginx:alpine
```

Windows PowerShellissä `$(pwd)` tilalle `${PWD}`. Muutokset HTML-tiedostoihin näkyvät heti selaimen päivityksellä.

## Hyödyllisiä komentoja

| Komento | Mitä tekee |
|---|---|
| `docker ps` | näyttää käynnissä olevat kontit |
| `docker logs omasivu` | nginxin lokit (pyynnöt, virheet) |
| `docker exec -it omasivu sh` | pääte kontin sisälle |
| `docker images` | koneelle rakennetut imaget |

## Keskeiset käsitteet

- **Image** = valmis paketti (käyttöjärjestelmä + nginx + sivusi). Rakennetaan kerran.
- **Kontti** = imagesta käynnistetty prosessi. Niitä voi olla useita samasta imagesta.
- **Portin julkaisu** `-p 8080:80` = koneen portti 8080 ohjataan kontin porttiin 80.
- **Volume / bind mount** `-v` = koneen kansio näkyy kontin sisällä; sopii kehitykseen.
