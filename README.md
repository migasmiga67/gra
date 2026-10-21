# DROPZONE

Przeglądarkowa gra battle royale 3D z kamerą zza pleców i 23 botami. Wymaga WebGL, klawiatury i myszy. Silnik Three.js 0.160.1 jest dołączony lokalnie w `vendor/` wraz z licencją MIT; nie potrzeba npm ani CDN.

## Uruchomienie

```sh
cd /workspace/gra
python3 -m http.server 8001 --bind 0.0.0.0
```

Otwórz serwer na porcie 8001 w przeglądarce. Można też otworzyć bezpośrednio `index.html`.

## Sterowanie

- WASD lub strzałki: ruch; Shift: sprint.
- Mysz: obrót kamery i celowanie; lewy przycisk: strzelanie. Po wejściu do gry kursor zostaje przechwycony. Escape zwalnia kursor i pauzuje grę.
- Gdy przeglądarka nie pozwala przechwycić kursora, obracaj kamerę ruchem myszy nad grą.
- R: przeładowanie; E: apteczka (+50 zdrowia); Escape: pauza.
- Podejdź do przedmiotów, aby zebrać apteczkę lub ulepszenie karabinu.

Unikaj fioletowej strefy i wyeliminuj pozostałych zawodników. Drzewa, skały i skrzynie blokują ruch i pociski. Dźwięk można włączyć przyciskiem u góry. Gra nie obsługuje sieciowego multiplayera ani sterowania dotykowego.

## Weryfikacja

`node --check game.js` sprawdza składnię. Sprawdzono w Chromium: renderowanie WebGL, 24 postacie, ruch względem kamery, strzelanie, przeładowanie, leczenie, pauzę, eliminacje, obrażenia od strefy, porażkę, restart i zwycięstwo. Na słabszym sprzęcie zalecana jest włączona akceleracja sprzętowa.
