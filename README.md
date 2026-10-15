# LEMUR HISTORIA 6.1.0

Otwarta, przeglądarkowa strategia geopolityczna. Aplikacja jest statyczna i została przygotowana do publikacji w GitHub Pages. Główna logika i interfejs znajdują się w `index.html`; wszystkie pozostałe wymagane pliki leżą obok niego w głównym katalogu repozytorium. Nie ma builda ani backendu.

## Publikacja na GitHub Pages

1. Wgraj wszystkie pliki projektu do katalogu głównego repozytorium: `index.html`, `manifest.webmanifest`, `sw.js`, ikony, `README.md`, `LICENSE-NOTICE.md`, `THIRD_PARTY_NOTICES.md` i `tests.js`.
2. Otwórz **Settings → Pages → Deploy from a branch**, wybierz gałąź `main` i katalog `/ (root)`.
3. Otwórz adres HTTPS GitHub Pages. Service worker i instalacja PWA wymagają HTTPS; w lokalnym podglądzie najlepiej użyć `python3 -m http.server 8000`.

Nie przenoś plików do podkatalogów, bo manifest i service worker są skonfigurowane względem katalogu głównego publikacji.

## Co zawiera wersja 6.1.0

- **Otwarta kampania:** usunięte cele zwycięstwa i warunki końca kampanii. Gracz może prowadzić państwo bez narzuconego zakończenia.
- **Logistyka i okupacja:** kalkulacja jakości linii zaopatrzenia, wzrost oporu, powstania oraz garnizony zmniejszające opór kosztem dostępnej piechoty. Panel `Okupacje` pokazuje kontrolowane obszary, opór i stan dostaw.
- **Frakcje polityczne:** niezadowolenie grup społecznych, ryzyko przewrotu, kryzysy rządowe i wydarzenia z wyborem reakcji. Trwałość wskaźników jest zachowana w zapisie.
- **Pamięć świata:** kronika zapamiętuje ważne wojny, traktaty, sankcje, kryzysy i przewroty. Wspomaga kontekst odpowiedzi dyplomatycznych AI.
- **Edytor scenariuszy:** edycja kraju gracza, startowej daty, skarbca, dochodu, armii, ustroju, poparcia, stabilności, podatków, kolorów i początkowych relacji. Scenariusze można walidować, importować i eksportować w JSON.
- **Mapa:** widoczne są granice państw, prowincje pozostają wewnętrznym mechanizmem kalkulacji. Szczegółowe prowincje są ładowane po przybliżeniu; w trybie awaryjnym wykorzystywane są schematyczne regiony.
- **Czat:** trzy kolumny na dużym ekranie, responsywny układ mobilny i ankiety dyplomatyczne. Przy dwóch uczestnikach nie pojawia się pytanie o zgodę na głos.
- **Zapisy:** migracja zapisów v2–v5 do v6, limitowanie i walidacja importowanych danych, seedowany RNG, IndexedDB dla większych kampanii.
- **PWA / offline:** manifest, ikony i service worker cachują powłokę aplikacji oraz niewielkie, przypięte wersjami zasoby mapy po pierwszym pobraniu.

## Ważne ograniczenia

To rozbudowana symulacja i sandbox, nie realistyczny model prognostyczny. Wartości wielu państw, logistyka, opór, wpływ sankcji, reakcje rządów i walki są modelami gry. Granice i nazwy pochodzą z wymienionych niżej bibliotek i zbiorów danych.

GitHub Pages nie ukrywa kluczy API. Klucz OpenRouter wprowadzaj tylko w ustawieniach gry i nie umieszczaj go w kodzie, repozytorium, eksporcie ani zrzutach ekranu. Klucz ujawniony w rozmowie lub repozytorium należy unieważnić i utworzyć nowy. Bez API dostępne są lokalne reguły doradcy i dyplomacji.

## Testy

Wymagany Node.js 20 lub nowszy. W katalogu głównym uruchom:

```sh
node --test tests.js
```

Testy obejmują składnię głównego skryptu i service workera, czyste reguły ekonomii/bitwy/wyborów, migrację starszego stanu, kontrakt działań AI, strukturę czatu, scenariusze, okupację, frakcje oraz kompletność płaskiej paczki GitHub Pages. Są testami statycznymi i jednostkowymi, nie zastępują pełnego testu E2E w Chrome/Firefox po publikacji.
