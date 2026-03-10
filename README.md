# MineSweeper — Klasyczny Saper w Terminalu

**MineSweeper** to gra logiczna napisana w języku C, polegająca na odkrywaniu pól planszy w celu znalezienia wszystkich bezpiecznych miejsc oraz oznaczaniu min flagami. Projekt został zrealizowany przez zespół w składzie: Adam G. i Przemek P.

## 📋 Opis projektu
Gra polega na logicznym dedukowaniu położenia min na podstawie cyfr wskazujących liczbę bomb w sąsiedztwie danego pola. Rozgrywka kończy się w momencie odkrycia pola z miną. Po wygranej gracz może zapisać swój wynik w tabeli 5 najlepszych rezultatów.

## 🚀 Uruchomienie programu
Program kompiluje się i uruchamia z poziomu terminala za pomocą następujących komend:

1.  **Kompilacja**: `make` 
2.  **Uruchomienie gry**: `./game -p`
3.  **Pomoc**: `./game -h`
4.  **Wczytanie z pliku**: `./game -f` (funkcja eksperymentalna)

## 🎮 Poziomy trudności
Gracz ma do wyboru cztery tryby rozgrywki, z których każdy posiada inny mnożnik punktów:

| Poziom | Rozmiar planszy | Liczba min | Mnożnik |
| :--- | :--- | :--- | :--- |
| **1. Łatwy** | 9x9 | 10 | x1  |
| **2. Średni** | 16x16 | 40 | x2  |
| **3. Trudny** | 16x30 | 99 | x3  |
| **4. Własny** | 9x9 do 49x49 | 25% pól | 1, 2 lub 3  |

## 🕹️ Instrukcja obsługi (Sterowanie)
Ruchy wykonuje się poprzez wpisanie współrzędnych w formacie:

* `r [x] [y]` — odkrywanie pola (**reveal**).
* `f [x] [y]` — stawianie lub usuwanie flagi (**flag**).

## 🛠️ Architektura i Moduły
Program został podzielony na kilka funkcjonalnych modułów:
* **`board.c`**: Generowanie i obsługa planszy, inicjalizacja struktur oraz zliczanie bomb.
* **`sweeper.c`**: Główny silnik gry (`gameEngine`), obsługa ruchów gracza i odkrywanie pól.
* **`highscore.c`**: Obsługa wyników, zapis/odczyt z plików oraz wyświetlanie tabeli liderów.
* **`levels.c`**: Zarządzanie wyborami poziomów trudności.
* **`struct.h`**: Wszystkie struktury wykorzystywane w programie.

## 👥 Podział pracy
* **Adam Grochulski**: Generowanie planszy, implementacja logiki zliczania bomb i manipulowania współrzędnymi.
* **Przemysław Pindral**: Implementacja systemu wyników, mechanika stawiania flag oraz integracja ostatecznego rezultatu rozgrywki.

## ⚠️ Ograniczenia i Uwagi
* Zapewnienie estetycznego wyświetlania planszy w terminalu było kluczowym wyzwaniem projektowym.
* Wczytywanie planszy z pliku nie zostało w pełni poprawnie zaimplementowane.
