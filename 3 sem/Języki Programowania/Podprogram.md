>[!note] Funkcja a podprogram
> Zgodnie ze starą konwencją funkcja to zenkapsulowana część programu która zwraca pewną wartość, podprogram (procedura) takowej nie zwraca. Przedawnione odkąd w C/C++ wszystko jest funkcją ([[Kernighan and Ritchie|K&R]]).

*Abstrakcja [[Model proceduralny|proceduralna]] (Abstrakcja przepływu sterowania)

## Wołający/wołany (caller - callee)
- Z różnymi argumentami
- Z różnych punktów
- Przez wielu wołających
# 
---
## 1. Wywołanie
1. Wołający kopiuje rejestry maszynowe do [[Flow control#Rekord aktywacyjny|rekordu aktywacyjnego]] (w tym *adres powrotu*).
2. Wołający kopiuje parametry oraz *adres powrotu* wołanemu.
3. Wołający wykonuje [[Flow control#Skok]] bezwarunkowy.
## 2. Powrót
1. Wołany ładuje swoje rejestry maszynowe.
2. Wołany wykonuje [[Flow control#Skok]] bezwarunkowy.
Mechanizm jest *wbudowany*.
#
---
## Lokalna pamięć podprogramu wołanego:
- Argumenty wywołania
- Łącze dynamiczne (DL, *dynamic link*)
- Adres powrotu (Wpisany na [[Stos]], wczytany do `eip` przy wywołaniu [[Najważniejsze instrukcje#ret|`ret`]])
- Kopia [[Rejestry|rejestrów]] stanu
- Prywatne dane podprogramu ([[Stos]])
### Rekord aktywacyjny
> Zbiór [[Rejestry|rejestrów]] odpowiedzialnych za przełączanie między podprogramami.

Dla wołającego: rejestry maszynowe, adres powrotu
Dla wołanego: wskaźnik do rekordu wołającego, parametry (ładowane na [[Stos]]). Dla kontroli [[Przestrzenie nazw|Zakres widzialności]] potrzebny też identyfikator *obecnego bloku kodu*.
%% #todo slajd ze skrótowymi nazwami zmiennych w rekordzie aktywacyjnym %%
#
---