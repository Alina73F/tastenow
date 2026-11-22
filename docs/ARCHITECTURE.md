# Architektura i technologie

## Stack

- React Native + Expo,
- Expo Router,
- Expo Location,
- Supabase jako baza, auth i minimalny backend,
- Postgres + PostGIS,
- Google Places API jako początkowe źródło lokali i godzin,
- Mapy systemowe jako środek nawigacji,
- Expo Application Services jako dystrybucja testowa.

## Minimalna architektura

```text
Telefon
  -> Expo app
  -> Supabase Edge Function
       -> Google Places API
       -> cache/dane TasteNow
       -> PostGIS
  -> lista rankingowa
  -> link do mapy systemowej
```

## Model danych

### place

- id,
- source,
- source_place_id,
- nazwa,
- adres,
- współrzędne,
- godziny otwarcia,
- cena orientacyjna,
- data ostatniej aktualizacji.

### search_event

- minimalny identyfikator sesji,
- współrzędne zanonimizowane lub obszar coarse,
- budżet,
- preferencja,
- liczba wyników,
- wybrany wynik,
- feedback.

## API

Jedno główne endpoint:

```text
POST /search
{
  "latitude": 52.23,
  "longitude": 21.01,
  "budget": 40,
  "preference": "vegan"
}
```

Odpowiedź zawiera maksymalnie 5 lokali z przejrzystym źródłem i znacznikiem aktualizacji.

## Ranking MVP

1. odfiltrowanie zamkniętych lokali,
2. odfiltrowanie lokali poza rozsądnym dystansem,
3. dopasowanie do budżetu,
4. dopasowanie do preferencji,
5. sortowanie według dystansu i jakości danych.

Nie używać złożonego ML ani AI.

## Koszty i limity

- cache wyników według obszaru i filtra,
- cache godzin i podstawowych danych,
- limit API po stronie aplikacji i Edge Function,
- brak zapisywania dokładnej trasy,
- bieżące monitorowanie kosztu Google Places na wyszukiwanie.

## Kiedy warianty wymagają zmiany

- Google Places nie dostarcza wiarygodnych cen: MVP pokazuje orientacyjny przedział i nie pokazuje ceny jako potwierdzoną.
- wolumen przekracza limity darmowe: przeanalizować koszt przed dodawaniem funkcji.
- użytkownicy potrzebują ofert regionalnych: najpierw pilotaż w jednym mieście.
- social features generują retencję: dopiero wtedy dodać konta i synchronizację.
