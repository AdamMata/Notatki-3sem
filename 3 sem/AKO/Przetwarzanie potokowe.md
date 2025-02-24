Wykonywanie [[Cykl rozkazowy]] dla wielu instrukcji jednocześnie.
# Problemy
## Niezgodność danych
- Wykonywanie na nieaktualnych danych (czytanie przed zapisem)
- Nadpisanie wyniku (zapis przed zapisem) 
> Analogiczne do [[ACID#Konsekwencje nie-ACIDowych transakcji]] w Bazach Danych.

### Rozwiązania
#### Szeregowanie statyczne
> Wykonywane na poziomie kompilacji
- Usuwanie zależności czasowych (zmiana kolejności instrukcji, by w międzyczasie policzyć coś, co przyda się później żeby nie musieć czekać)
#### Szeregeowanie dynamiczne (sprzętowe)
> Wykonywane w trakcie działania programu
#### Scoreboarding

### Rozgałęzienia
**Rozwiązania**:
- Branchless programming
- Zwielokratnianie strumieni
- Static/Dynamic branch prediction
> Np. tablica skoków (zliczanie często wywoływanych [[Wywoływanie funkcji|podprogramów]])
