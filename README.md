# Lifemax

Mobile-first sidequest do prawdziwego życia. Cała aplikacja — CSS, JavaScript, grafiki i dane — znajduje się w `index.html`. Bez bibliotek, zewnętrznych zasobów i procesu budowania. Interfejs po polsku, motyw zgodny z ustawieniem systemu.

## Uruchomienie

Otwórz `index.html` w przeglądarce lub uruchom:

```sh
cd /workspace/gra
python3 -m http.server 8010 --bind 0.0.0.0
```

Aplikacja dostępna jest na porcie 8010. Dane są lokalne dla przeglądarki i adresu strony; zmiana domeny lub portu nie przenosi postępów. Przy zablokowanym localStorage gra działa w pamięci i pokazuje ostrzeżenie. Nie ma logowania, śledzenia GPS ani serwera wyników. Schowek ma ręczny wariant awaryjny.

## Zasady

- 3 misje dziennie: 10/25/50 XP i skrzynia drewniana/srebrna/złota. 48 misji w 4 kategoriach.
- Jeden reroll dziennie wymienia niezakończone misje. Odnowienie o lokalnej północy.
- Pierwsza misja danego dnia podtrzymuje serię. Od drugiego dnia bonus rośnie o 5 XP, do 35 XP. Pominięcie dnia przerywa serię.
- 30 przedmiotów, 5 rzadkości, 6 zestawów. Szanse dropu widoczne przed otwarciem skrzyni. Duplikaty dają pył do wymiany na wybrany typ skrzyni.
- CP to XP + wartość unikalnych przedmiotów + bonusy kompletnych zestawów + bonusy zdobytych odznak. Bonusów nie dopisuje się ponownie przy odświeżeniu.
- Każda ukończona misja odkrywa heks na symbolicznej mapie. Możesz zapisać nazwę i notatkę.
- 17 odznak, edytowalny nick i wystawa do 3 zdobytych przedmiotów na karcie flexu.

## Własne treści

W `index.html` dane mają osobne, opisane sekcje:

- **Misje:** dodaj obiekt do `MISSIONS`: unikalne `id`, `difficulty` (0–2), `category`, `title`, `description`, `xp`. Bazowe misje powstają z `MISSION_TEXTS`.
- **Przedmioty:** dodaj obiekt do `ITEMS`: unikalne `id`, `set` (identyfikator z `SETS`), `rarity` (0–4), `name`, `icon`, `lore`. Zestawy i ich bonusy edytuj w `SETS`, szanse w `CHESTS`.
- **Odznaki:** dodaj do `BADGES` obiekt z `id`, `name`, `icon`, `hint`, `bonus` i funkcją `test(s)` zwracającą prawdę po spełnieniu warunku.

Zachowuj istniejące identyfikatory — zapisane postępy odwołują się do nich. Krótka instrukcja znajduje się też na dole ekranu Profil.

## Weryfikacja

Sprawdzono w Chromium przy szerokości 390 i 1440 px: trzy misje i reroll, XP, serię i bonus raz na dzień, codzienne odświeżanie, skrzynie, duplikaty i wymianę pyłu, dokładne CP, zestawy, odznaki, mapę z notatkami, edycję nicku i wystawy, kopiowanie awaryjne, zapis po przeładowaniu i reset z potwierdzeniem. Sprawdzono także jasny motyw, brak poziomego przewijania, zablokowany localStorage oraz uszkodzony zapis.
