# Instrukcje dla agentów

## Cel projektu

TasteNow ma szybko i wiarygodnie odpowiedzieć: „gdzie mogę zjeść teraz, w pobliżu i w moim budżecie”.

## Priorytety decyzji

1. Lean First: wybieraj najmniejsze rozwiązanie, które weryfikuje hipotezę.
2. Distribution First: każda funkcja musi wspierać pozyskanie, aktywację albo retencję.
3. Rygorystycznie różnicuj dane zewnętrzne od danych posiadanych w TasteNow.
4. Nie buduj AI, social features, rezerwacji ani live occupancy przed potwierdzonym problemem i wolumenem danych.
5. Ograniczaj koszty operacyjne i czas na support.

## Zakres MVP

Do MVP należą tylko:

- pobranie i zgodna z uprawnieniami obsługa lokalizacji,
- otwarte teraz,
- budżet,
- jedna preferencja, np. wegańskie lub bezglutenowe,
- ranking kilku lokali,
- godziny otwarcia i podstawowe informacje,
- mapa i trasa,
- proste trackowanie aktywacji i wyboru lokalu.

Nie należy implementować bez osobnej decyzji:

- AI chat,
- głosowego asystenta,
- Live Crowd,
- rezerwacji,
- głosowania ze znajomymi,
- publicznych zdjęć i wersji społecznościowych,
- verified menu,
- last-minute deals,
- trasy wieloma środkami transportu.

## Właściwy stack MVP

- React Native z Expo,
- Expo Location,
- Expo Router,
- Supabase: Postgreza, Auth opcjonalnie, Edge Functions tylko, gdy potrzebne,
- Google Places API jako początkowe źródło danych,
- Mapy i nawigacja przez aplikację mapową systemu.

Nie dodawaj własnej infrastruktury, mikrousług, kolejki ani analityki niestandardowej przed osiągnięciem realnego wolumenu.
