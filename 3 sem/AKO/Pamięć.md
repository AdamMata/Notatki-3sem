---
aliases:
  - RAM
---

>[!Note] Zobacz też: [[Pamięć fizyczna]] 

Pamięć to jest de facto *wektor liczb*.
Jeśli komórkę tworzy 8 bitów, pamięć ma *organizację bajtową*.

>[!Info] Dane zapisane w pamięci są nierozróżnialne od instrukcji! ^[[[Architektura von Neumanna]]]

# Słowo

^78ee08

~~Słowem określa się rozmiar rejestru, który jest w stanie zaadresować całą [[#^przestrzen-adresowa|przestrzeń adresową]].~~ Była to prawda, gdy komputery miały mały RAM. Dzisiaj, by zachować kompatybilność wsteczną, słowo to po prostu **dwa bajty**.

![[Dyrektywy alokacji.png]]

**Przestrzeń adresowa** to zbiór wszystkich liczb które stanowią adresy istniejących komórek w pamięci. Zazwyczaj przestrzeń adresowa ma liczność równą największej możliwej wartości słowa. ^przestrzen-adresowa
# Znaczność bitów
\[==M==SB __ __ __ ... __ ==L==SB]
## MSB
==Most== Significant Bit
## LSB
==Least== Significant Bit

>[!warning]
>W pamięci **zawsze** *coś* jest!

^0d8c33

>[!warning]
>Różne programy różnie wizualizują przestrzeń adresową. Zwróć uwagę czy adresy z góry na dół rosną czy maleją.
>Dodatkowo [[Stos]] rośnie odwrotnie do [[Sterta]].
