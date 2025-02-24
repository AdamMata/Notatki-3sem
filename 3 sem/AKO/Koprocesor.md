---
aliases:
  - Koprocesor
  - Koprocesor arytmetyczny
---
[[Najważniejsze instrukcje]]:
`fadd, fsub, f...`: operacje na [[Kodowanie liczb#Zmiennoprzecinkowe|floatach]]. ^405df0
![[AKO_2024_cz_3.pdf#page=170]]

>[!info] Używa rejestrów 80-bitowych
>![[Kodowanie liczb#Temporary real]]
# Stos
Wewnętrzne operacje przeprowadza na własnym [[Stos|stosie]]:
## R0 - R7
*Implementacyjnie* posiada rejestry od `R0` do `R7`. **Nie używamy tych rejestrów**.
Każdy rejestr ma odpowiadające bity w [[#Rejestr flag]].

## ST(0) - ST(7)
*Wyeksponowane* są rejestry *od wierzchołka stosu*: `ST(0)` (wierzchołek), `ST(1)` (liczba poprzednia) itd. ^96f97e

# Rejestr flag
Dwa bity na [[#R0 - R7|rejestr]]. Kody oznaczają:
	00 - rejestr =/= 0
	01 - rejestr = 0
	10 - rejestr miał błędne obliczenia (error propagation, dzielenie przez zero, itd.)
	11 - rejestr jest nieużywany (pusty/[[Pamięć#^0d8c33|śmieciowe dane]])
[[Najważniejsze instrukcje]]: kopiuj do głównego procesora używając `FSAVE`

# Rejestr sterujący
![[AKO_2024_cz_3.pdf#page=163]]

#
---
# Jak używać koprocesora
1. Wyprowadź wzór obliczenia które będziesz przeprowadzał na kartce.
> Uporządkuj kolejność działań tak, żeby jak najrzadziej musieć zmieniać kolejność operandów ^[Może warto zastosować Odwrotną Notację Polską? Unikaj nawiasów.]
 ^895c01
2. Zainicjalizuj rejestry koprocesora
> Użyj `finit` żeby ustawić nowe [[#^96f97e|ST(0)]].
4. Prześlij dane koprocesorowi
> [[Najważniejsze instrukcje]]: `FLD mem` - wyślij na stos lokację mem
> >[!warning]+ `mem` musi być poprzedzone [[Dyrektywa PTR]]!
> >ALU nie zna [[Kodowanie liczb#Zmiennoprzecinkowe|precyzji]] liczby którą dostaje.
>
> >[!warning]+ Komunikacja odbywa się przez [[Pamięć fizyczna]]!
> >Myśl o ko- i zwykłym procesorze jak o dwóch osobnych komponentach. ^[Na początku koprocesor był osobnym komponentem, dzisiaj są wbudowane. Kompatybilność wsteczna :/] **Nie ma** bezpośredniego dostępu do rejestrów procesora! ^[Drobny szczegół: [[Najważniejsze instrukcje#^fd39be|fcomi]]]
> 
> ![[Najważniejsze instrukcje#Instrukcje Koprocesora#Przesył wartości]]

3. Wykonaj obliczenia
> Wysyłaj [[#^405df0|rozkazy]] do obliczeń których potrzebujesz według [[#^895c01|wyprowadzonego wzoru]]. 
> ![[Najważniejsze instrukcje#Instrukcje Koprocesora#Instrukcje arytmetyczne]]