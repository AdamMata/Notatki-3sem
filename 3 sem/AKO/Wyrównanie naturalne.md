Adres danej jest podzielny przez jej rozmiar, np. każda kolejna 4B liczba jest w co czwartej komórce.

Wyrównanie pozwala przyspieszyć dostęp do [[Pamięć|RAMu]]: bajty w pamięci adresuje się za pomocą [[Pamięć#^78ee08|słów]], rozmieszczonych co 4B, co pozwala "wciągnąć" wiele bajtów przy jednej transakcji. 
> [[Pamięć fizyczna]] 

# Padding
Pola struktur są wyrównywane pustymi bajtami (paddingami), żeby zachować wyrównanie naturalne pól.
```
struct A {
	i8 a,
	i16 b
} // 8b + 16b = 3B?
```
zostanie skompilowany jako
```
struct A { 
	i8 a,
	i8 _padding1,
	i16 b
} // rozmiar A = 4B!
```
