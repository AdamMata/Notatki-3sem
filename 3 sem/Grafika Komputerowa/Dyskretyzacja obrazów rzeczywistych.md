# Próbkowanie
**wybór [[Reprezentacja obrazów#^39afbd|rastra]]**

Problemy:
- Zmiana rozmiaru obiektów
- Zmiana kształtu
- Znikanie obiektów pomiędzy próbkowanymi punktami
- [[#Aliasing|Zniekształcenia próbkowania]]
## Aliasing
*poschodkowanie, postrzępienie*
### Rozwiązania: 
- Zwiększenie rozdzielczości
- Przesunięcie rastra
- **Antyaliasing**: gradient na krawędziach kształtu.
- [[#Drżenie (dithering)]]
Funkcje wagowe antyaliasingu: 
- prostopadłościenna (bezwagowa)
- ostrosłupowa (wagowa, preferuje kolor środka)
- stożkowa (wagowa, uwzględnia kolory sąsiadów)

# 
---
# Kwantyzacja
**ograniczenie [[Modele kolorów|puli kolorów]]**

## Poprawa kwantyzacji
### Drżenie (dithering)
gradient za pomocą gęstości pikseli w kolorach sąsiednich
Losowy/nielosowy
Metody nielosowe:
- progowanie
- halftone (wielkość piksela = odwrotna jasność) (przydatne w druku)
- uporządkowane
### Dyfuzja błędów (*error diffusion*)
**Dyfuzja Floyda-Steinberga**: Dodajemy po części błędu kwantyzacji do sąsiednich pikseli.

## Mikrowzory
