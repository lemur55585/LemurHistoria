# Informacje o bibliotekach i danych zewnętrznych

LEMUR HISTORIA ładuje część bibliotek i danych geograficznych z publicznych CDN. Ich licencje dotyczą konkretnych bibliotek lub zbiorów danych, a nie samego kodu aplikacji.

## D3.js 7.9.0
- Projekt: https://github.com/d3/d3
- Licencja: ISC.
- Plik CDN: `https://unpkg.com/d3@7.9.0/dist/d3.min.js`.

## topojson-client 3.1.0
- Projekt: https://github.com/topojson/topojson-client
- Licencja: ISC.
- Plik CDN: `https://unpkg.com/topojson-client@3.1.0/dist/topojson-client.min.js`.

## world-atlas 2.0.2
- Projekt: https://github.com/topojson/world-atlas
- Licencja pakietu: ISC (sprawdź metadane konkretnego wydania).
- Zbiór: `countries-50m.json`, opracowany na podstawie Natural Earth.

## world-countries 5.1.0
- Projekt: https://github.com/mledoze/countries
- Licencja: Open Database License (ODbL) 1.0. Przy dalszej redystrybucji wyciągów lub adaptacji bazy sprawdź wymóg atrybucji i warunki share-alike.
- Endpoint: `https://cdn.jsdelivr.net/npm/world-countries@5.1.0/countries.json`.

## Natural Earth Vector v5.1.2
- Projekt: https://github.com/nvkelso/natural-earth-vector
- Serwis: https://www.naturalearthdata.com/
- Licencja danych Natural Earth: domena publiczna; atrybucja jest mile widziana.
- Endpoint: `https://cdn.jsdelivr.net/gh/nvkelso/natural-earth-vector@v5.1.2/geojson/ne_50m_admin_1_states_provinces.geojson`.

## Ikony i PWA

`icon.svg`, `icon-192.png` i `icon-512.png` są częścią projektu LEMUR HISTORIA i zostały przygotowane na potrzeby tej aplikacji.

## Uwagi

Wersje URL dla bibliotek i zbiorów danych są przypięte. CDN nadal jest zewnętrzną zależnością; service worker może zapamiętać małe zasoby po ich pierwszym udanym pobraniu. Ciężki plik prowincji celowo nie jest przechowywany automatycznie w cache, by nie zużywać znacznej części limitu przeglądarki.
