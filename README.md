# LEMUR HISTORIA 5.0.1

Przeglądarkowa gra strategiczna o zarządzaniu państwem, wojnach i dyplomacji. Projekt jest przeznaczony do hostowania jako zwykła strona statyczna na **GitHub Pages**. Gra uruchamia się z głównego pliku `index.html`; nie ma backendu ani procesu budowania.

## Publikacja na GitHub Pages

1. Skopiuj `index.html` do głównego katalogu repozytorium. Pliki `README.md`, `LICENSE-NOTICE.md` i `THIRD_PARTY_NOTICES.md` są dokumentacją i mogą leżeć obok gry.
2. W GitHub otwórz **Settings → Pages**, wybierz gałąź `main` i katalog `/ (root)`.
3. Otwórz opublikowany adres HTTPS.

**Ważne:** w tym wydaniu nie ma osobnego pliku scenariusza „Bitwa pod Pragą”. To był scenariusz testowy. Taktyczne potyczki w zwykłej kampanii pozostają częścią gry.

## Co zmieniło się w tej poprawce

- **Brak punktów na mapie:** nie są rysowane znaczniki bitew, numerki starć, miasta ani ikony budynków. Mapa prezentuje kolory i scalone kontury państw. Prowincje pozostają danymi wewnętrznymi silnika.
- **Po podboju znika aktywny front:** pełne przejęcie państwa usuwa aktywną wojnę i licznik frontu. Raporty bitew pozostają w kronice, ale nie pojawiają się jako punkty na mapie.
- **Stare podboje są porządkowane przy wczytywaniu zapisu:** jeżeli starszy zapis miał już państwo pod kontrolą innego państwa, przestarzały licznik frontu, wojna i rozbieżne kontrole prowincji są usuwane lub normalizowane.
- **Zgodność zapisów:** zachowano format zapisu v5 i klucz `lemur_historia_global_v5`, więc zwykła aktualizacja pliku nie tworzy nowej, pustej kampanii. Loader nadal próbuje odczytać IndexedDB oraz starsze klucze `lemur_historia_global_v4`, `lemur_historia_global_v3`, `lemur_historia_global_v2` i `pax_historia_global_v1`. Stare zapisy są migrowane przed wznowieniem rozgrywki.
- **Otwarta kampania:** gracz nie musi wybierać warunku zwycięstwa; nie ma automatycznego końca kampanii po osiągnięciu dawnego celu.

## Mapa i źródła

Biblioteki mapy są przypięte do wersji i korzystają z atrybutów SRI oraz zapasowego CDN. Podstawowe granice państw pochodzą z `world-atlas@2.0.2`, metadane z `world-countries@5.1.0`, a szczegółowe prowincje z Natural Earth Vector `v5.1.2`. Prowincje są pobierane asynchronicznie i pozostają niewidoczne jako granice. Gdy zewnętrzne biblioteki lub dane nie odpowiadają, gra pokazuje uproszczony widok awaryjny.

## Zapisy, AI i bezpieczeństwo

Zapisy zawierają numer wersji. Import JSON jest walidowany, a starsze formaty przechodzą migrację. Mniejsze zapisy korzystają z `localStorage`, większe z IndexedDB. Losowość symulacji wykorzystuje generator z ziarnem zapisanym w kampanii.

Klucz OpenRouter nie jest dołączony do pliku. W aplikacji statycznej każdy klucz wpisany do przeglądarki może być widoczny dla użytkownika; nie należy umieszczać sekretu na stałe w publicznym repozytorium. Publiczne wspólne API wymagałoby prywatnego pośrednika, którego sam GitHub Pages nie zapewnia.

Część parametrów gospodarczych, społecznych i wojskowych jest syntetyczna i służy rozgrywce, nie stanowi oficjalnych danych statystycznych.

## Licencje

Informacje o bibliotekach i źródłach danych stron trzecich znajdują się w `THIRD_PARTY_NOTICES.md`. Warunki dotyczące kodu gry opisuje `LICENSE-NOTICE.md`; nie należy zakładać licencji MIT, jeśli nie została osobno wybrana.
