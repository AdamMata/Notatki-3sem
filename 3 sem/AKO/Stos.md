---
aliases:
  - Stack
---
Stos służy do tymczasowego przechowywania danych, które nie mieszczą się w rejestrach.

>[!important] Stos rośnie w stronę malejących adresów

Miejsce na stos jest alokowane automatycznie, wskaźnik mamy w [[Rejestry|rejestrze]] `esp`.

>[!important] `ESP` wsazuje na *wierzchołek stosu*, tj. *pierwsze wolne miejsce*

[[Najważniejsze instrukcje#push/pop]] ^eba4d0

>[!warning]- Stack pointer powinien **zawsze** być podzielny przez 4! [[Wyrównanie naturalne]]
>Pushować tylko wielkości 4-bajtowe! Tryb 32bitowy będzie ostrzegał i nie puści pushowania mniejszych rejestrów.
>**Ignorowanie ostrzeżeń grozi niewyrównaniem stosu!**
>
>>[!warning] Stos ma być wyrównany!
>Stack pointer trzeba przywrócić do zastanej wartości pod koniec wykonywania programu. Na stosie znajduje się [[Podprogram#Lokalna pamięć podprogramu wołanego|adres powrotu programu]].

>[!warning] Pop nie usuwa danych, ale...
>...ta pamięć już do programu nie należy! [[Przerwanie systemowe]] może niespodziewanie przywłaszczyć obszar pamięci który jeszcze przed chwilą był nasz. Dostęp spowoduje wtedy trudno replikowalny [[Przerwanie systemowe#Wyjątki procesora [AKO_2024_cz_4.pdf page=69|wyjątek]].

>[!note] Abstrakcja
>W [[Tryby procesora#Chroniony]], [[OS]] może podmieniać nam stos w zależności od obecnego uprzywilejowania.

![[Najważniejsze instrukcje#^909b56]]
[[Wywoływanie funkcji]]
# Ramka stosu
![[AKO_2024_cz_3.pdf#page=27]]

# [[Interfejs ABI]]
