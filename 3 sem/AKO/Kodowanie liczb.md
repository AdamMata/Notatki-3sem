# Całkowitych
## NKB
## U2
Zakres: 127 do -128

![[Najważniejsze instrukcje#^e04c4b]]

---
## U1 (nieomawiany)
## Znak - moduł
`±xxx xxxx`
**Podwójne zero**: +0 i -0.
Używany w liczbach zmiennoprzecinkowych.

#
---
# Rzeczywistych
## Stałoprzecinkowe
$2^n, 2^{n-1},...,2^0 . 2^{-1}, 2^{-2},...$
## Zmiennoprzecinkowe
`seeemmmm`
>[!info] Wykładnik ma **bias**
>Jest sztucznie *zwiększony* o +127 względem NKB, żeby nie kodować go jako U2

- #32bit: 8 bit wykładnik 
- #64bit: 11 bit wykładnik
## Temporary real

Liczba 80-bitowa stosowana przez [[Koprocesor]].
>[!warning] Przechowuje mantysę w formacie **jawnym**!
>Jedynka mantysy jest zakodowana na stałe

Wykonując operacje na 80 bitach jest w stanie podawać dokładne wyniki obliczeń dla liczb 64-bitowych.