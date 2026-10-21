# DROPZONE

Przeglądarkowa gra battle royale dla jednego gracza z 23 botami. Bez zależności i zewnętrznych usług. Wymaga przeglądarki na komputerze, klawiatury i myszy.

## Uruchomienie

```sh
cd /workspace/gra
python3 -m http.server 8000 --bind 0.0.0.0
```

Otwórz serwer na porcie 8000 w przeglądarce. Można też otworzyć bezpośrednio `index.html`.

## Sterowanie

- WASD lub strzałki: ruch; Shift: sprint.
- Mysz: celowanie; lewy przycisk: strzelanie.
- R: przeładowanie; E: apteczka (+50 zdrowia); Escape: pauza.
- Podejdź do przedmiotów, aby zebrać apteczkę lub ulepszenie karabinu.

Unikaj fioletowej strefy i wyeliminuj pozostałych zawodników. Drzewa, skały i skrzynie blokują ruch i pociski. Dźwięk można włączyć przyciskiem u góry. Gra nie obsługuje sieciowego multiplayera ani sterowania dotykowego.
