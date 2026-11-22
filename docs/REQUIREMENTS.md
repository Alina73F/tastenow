# Wymagania

## Wymagania funkcjonalne

### FR-01 Lokalizacja

- wymagane wyraźne przyzwolenie użytkownika,
- system może działać po ręcznym wpisaniu miasta lub adresu,
- zamknięte miejsca są filtrowane,
- obsługa błędu GPS i braku internetu.

### FR-02 Budżet

- limit reprezentowany jako kwota w PLN,
- wynik podaje orientacyjny przedział kosztu,
- limit nie jest gwarantowaną ceną,
- cena nie może być oznaczana jako verified bez źródła i daty.

### FR-03 Preferencje

- jedna preferencja na start,
- domyślna opcja „bez preferencji”,
- kolejne preferencje dodawane dopiero po dowodzie ich użycia.

### FR-04 Ranking

- domyślnie 3–5 wyników,
- sortowanie przez dystans/czas dojścia, dopasowanie do budżetu i preferencji,
- każdy wynik ma główny powód rekomendacji,
- wyniki oznaczają ostatni czas aktualizacji danych.

### FR-05 Szczegóły i trasa

- nazwa, adres, ocena, godziny, źródło danych i orientacyjna cena,
- przycisk otwarcia trasy w aplikacji mapowej,
- brak własnego silnika nawigacyjnego.

### FR-06 Sprzężenie zwrotne

- jeden prosty feedback: trafne, częściowo, nietrafne,
- opcjonalnie przyczyna: zamknięte, za drogie, daleko, zły typ,
- bez kolejki moderacyjnej na start.

## Wymagania niefunkcjonalne

- pierwsza lista maksymalnie w 7 sekund dla 95% prób,
- obsługa słabych połączeń i cache,
- nieprzechowywanie dokładnej lokalizacji po zakończeniu zapytania,
- brak żądania danych osobowych w pierwszym użyciu,
- UI informuje o źródle i aktualności danych,
- dostępność WCAG: kontrast, duże cele dotykowe, VoiceOver/TalkBack.

## Acceptance criteria

- nowy użytkownik wykonuje pełną decyzję bez instrukcji,
- ustawienie budżetu nie daje pustego ekranu, lecz informację o alternatywnych limitach,
- lista nie zawiera wyniku oznaczonego jako zamknięty,
- użytkownik może zamknąć lub odmówić uprawnienia lokalizacji,
- po przekierowaniu do mapy aplikacja zachowuje stan wyboru,
- feedback zapisuje się bez zakładania konta.
