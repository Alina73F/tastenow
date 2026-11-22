# Pre-mortem i ryzyka

## Założenie niepowodzenia

Wyobrażono sobie datę 90 dni później, kiedy produkt istnieje, ale nie ma regularnych użytkowników ani partnerów.

## Największe przyczyny niepowodzenia

1. dane o cenach i godzinach są niedokładne,
2. użytkownik może szybciej porównać opcje w Google Maps,
3. AI nie dodaje wystarczającej wartości,
4. koszt API przekracza przychód,
5. brak momentu dystrybucji,
6. użytkownik nie płaci za subskrypcję,
7. solo dev tworzy własne dane i moderację zamiast walidować produkt.

## [RISKS] — czerwone flagi

| Ryzyko | Prawdopodobieństwo | Skutek | Reakcja |
|---|---|---|---|
| Google Maps jest wystarczająco dobry | Wysokie | Brak wyróżnienia | Testować bezpośrednio 30-sekundowy wybór |
| Ceny z menu są szybko nieaktualne | Wysokie | Utrata zaufania | Pokazywać przedział i źródło |
| Godziny są nieaktualne | Wysokie | Utrata zaufania | Oznaczać aktualność i zbierać feedback |
| Niska ochota na subskrypcję | Wysokie | Brak modelu dochodu | Najpierw partnerzy i rabaty |
| Zbyt szeroki ICP | Wysokie | Brak skutecznego kanału | Jeden segment i jedno miasto |
| Over-engineering | Średnie | Opóźnienie MVP | Tylko lokalizacja, budżet, preferencja i lista |
| Koszt danych i API | Średnie | Niskie marże | Cache i limity |
| AI halucynuje | Średnie | Niemiarodajny wynik | Nie używać AI w MVP |
| Wymóg rezerwacji | Średnie | Zależność od dostawców | Najpierw deep link do zewnętrznego systemu |

## Warunek zatrzymania projektu

Zatrzymać budowę i zmienić kierunek, jeśli po 100 realnych sesjach:

- mniej niż 20% użytkowników wybiera lokal z TasteNow,
- więcej niż 20% wyników jest zamkniętych lub nie odpowiada budżetowi,
- użytkownicy nie wracają po 7 dniach,
- pilotażowi partnerzy nie potwierdzają chęci płatności.
