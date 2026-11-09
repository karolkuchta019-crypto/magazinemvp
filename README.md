# Prosty System Magazynowy (HTML + JavaScript)

Prosty, szkolny system magazynowy działający w całości w przeglądarce.  
Nie wymaga serwera, bazy danych ani instalacji – wystarczy otworzyć plik HTML.

---

## Funkcje systemu

System obsługuje następujące operacje magazynowe:

1. **Przyjęcie towaru** – zwiększenie stanu dostępnego
2. **Wydanie towaru** – zmniejszenie stanu dostępnego (z kontrolą ilości)
3. **Rezerwacja towaru** – przeniesienie części stanu do rezerwacji
4. **Zwolnienie rezerwacji** – odblokowanie wcześniej zarezerwowanej ilości
5. **Zwrot towaru** – przyjęcie towaru z powrotem do magazynu

Dodatkowo system posiada:
- Listę produktów ze stanem **dostępny** i **zarezerwowany**
- Listę aktywnych rezerwacji
- Historię wszystkich ruchów magazynowych
- Zapis danych w przeglądarce (localStorage)

---

## Jak uruchomić

1. Skopiuj kod HTML do pliku o nazwie `magazyn.html`
2. Otwórz plik w dowolnej przeglądarce (Chrome, Firefox, Edge, Opera...)
3. Gotowe – system działa od razu

> Nie trzeba instalować niczego. Nie trzeba serwera.

---

## Jak korzystać z systemu

### 1. Dodawanie produktu
- Wpisz nazwę produktu (np. `Śruba M8`)
- Opcjonalnie zmień jednostkę (domyślnie `szt.`)
- Kliknij **Dodaj produkt**

### 2. Przyjęcie towaru
- Kliknij zielony przycisk **+** przy produkcie
- Podaj ilość i opcjonalne uwagi
- Zatwierdź

### 3. Wydanie towaru
- Kliknij czerwony przycisk **−**
- System sprawdzi, czy jest wystarczająca ilość dostępna
- Jeśli nie – pokaże komunikat o błędzie

### 4. Rezerwacja towaru
- Kliknij żółty przycisk **R**
- Podaj ilość do zarezerwowania
- Opcjonalnie wpisz kto rezerwuje
- Zarezerwowana ilość zostaje przeniesiona ze stanu dostępnego do zarezerwowanego

### 5. Zwolnienie rezerwacji
- W sekcji **Aktywne rezerwacje** kliknij przycisk **Zwolnij**
- Ilość wraca do stanu dostępnego

### 6. Zwrot towaru
- Kliknij niebieski przycisk **↩**
- Działa podobnie jak przyjęcie towaru

---

## Jak działają stany magazynowe

- **Stan dostępny** – towar, który można wydać lub zarezerwować
- **Stan zarezerwowany** – towar zablokowany, nie można go wydać
- **Razem** = dostępny + zarezerwowany

---

## Przechowywanie danych

Wszystkie dane są zapisywane w **localStorage** przeglądarki:
- `magazyn_produkty` – lista produktów
- `magazyn_rezerwacje` – rezerwacje
- `magazyn_historia` – historia ruchów

Dzięki temu:
- Dane nie giną po odświeżeniu strony
- Dane są dostępne tylko na tym komputerze i w tej przeglądarce
- Nie ma potrzeby logowania ani serwera

---

## Struktura kodu

Plik jest podzielony na logiczne części:

| Część              | Opis                                      |
|--------------------|-------------------------------------------|
| HTML               | Struktura strony + Bootstrap              |
| Style CSS          | Podstawowe style wyglądu                  |
| Modele danych      | `produkty`, `rezerwacje`, `historia`      |
| Funkcje operacji   | przyjęcie, wydanie, rezerwacja itd.       |
| Funkcje interfejsu | odświeżanie widoku, otwieranie modali     |
| Start aplikacji    | `window.onload` – wczytanie danych        |

Kod zawiera **dużo komentarzy**, żeby łatwo było zrozumieć, co robi każda funkcja.

---

## Technologie

- **HTML5**
- **CSS3** + Bootstrap 5 (wygląd)
- **JavaScript (Vanilla)** – bez frameworków
- **localStorage** – przechowywanie danych

---

## Możliwe rozbudowy (pomysły na przyszłość)

- Usuwanie produktów
- Edycja nazwy produktu
- Eksport historii do CSV
- Filtrowanie i wyszukiwanie produktów
- Ciemny motyw
- Możliwość ustawienia minimalnego stanu (alert o niskim stanie)

---

## Autor

Projekt szkolny – prosty system magazynowy napisany w czystym HTML + JavaScript.
