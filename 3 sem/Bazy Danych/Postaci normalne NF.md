---
aliases:
  - NF
  - Normal Form
---
Opisują **zależności** między [[Encja#Atrybut|atrybutami]]. Zastosowanie to przede wszystkim znajdowanie [[Redundancja|redundancji]].
# 1NF
~~Brakujące w prezentacji~~
# 2NF
Złamana gdy istnieje zależność od tylko jednej składowej klucza złożonego.
```mermaid
flowchart

subgraph K
	K1 <---> K2
end
K --> X
K1 --> Y
```
# 3NF
Złamana gdy istnieje zależność przechodnia.
```mermaid
flowchart
Osoba --> Miasto --> ZaludnienieMiasta
Osoba --> ZaludnienieMiasta
```
# Boyce-Codd NF
Złamana gdy istnieje *wyznacznik* niebędący jednym z *kluczy kandydujących.*
Wyznaczniki to wszystkie atrybuty, od których zależy jakiś inny.

# 4NF
Nie posiada zależności wielowartościowych, tzn. każdy wyznacznik jednoznacznie wskazuje na *jedną* możliwą wartość atrybutu.
