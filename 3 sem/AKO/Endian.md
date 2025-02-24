---
aliases:
  - Endianowość
---
# Little endian
>Mniejsze niżej

Młodszy koniec liczby [[Pamięć fizyczna#LSB]] jest w pierwszym adresie.
# Big endian
> Większe niżej

Starszy koniec liczby jest w pierwszym adresie.
>[!tip] Język naturalny
>W języku polskim używamy BE do opisu liczb.
>>Tysiąc sto dwadzieścia pięć

---

[[Najważniejsze instrukcje]]: `BSWAP` zmienia endianowość rejestru.
Żeby zmienić endianowość długiej liczby na wielu rejestrach należy wykonać `bswap` i zamienić rejestry miejscami (np. instrukcją `mov` z temp'em albo instrukcją `xchng`).