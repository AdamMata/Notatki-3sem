Instrukcje Koprocesora
Zobacz [[Koprocesor#Jak używać koprocesora]]

`FINIT` - inicjalizacja koprocesora - resetuje wartości na stosie koprocesora
## Przesył wartości
Przesył odbywa się z/na [[Koprocesor#Stos|stos]] koprocesora.

|                       | Liczby całkowitej U2 | Liczby zmiennoprzecinkowej float |
| --------------------- | -------------------- | -------------------------------- |
| Wysyłka na koprocesor | `FILD`               | `FLD`                            |
| Odbiór do pamięci     | `FIST`               | `FST`                            |

## Instrukcje arytmetyczne
- `fadd` `fsub`
- `fdiv` `fmul`

## Porównania
- `fcom` ^e793bc

##
Litery końcowe [[Mnemonik|mnemoników]] funkcji koprocesora które modyfikują działanie wspomnianych instrukcji:

| Znacznik mnemonika | Znaczenie | Działanie                                                              |
| ------------------ | --------- | ---------------------------------------------------------------------- |
| `...p`             | pop       | Zmniejsza rozmiar stosu o jeden po wykonaniu - konsumuje drugi operand |
| `...r`             | reverse   | Używa odwrotnej kolejności operandów                                   |
Instrukcja [[#^e793bc|fcom]] jest dostępna w wydaniu `fcomi` która automatycznie zapisuje wynik porównania do [[Flagi|Rejestru flag procesora]].  ^fd39be