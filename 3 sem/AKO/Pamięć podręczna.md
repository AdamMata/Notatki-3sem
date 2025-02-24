---
aliases:
  - Cache
---
> [[AKO_2024_cz_5.pdf#page=30]]


Bity adresu fizycznego dzielą się na etykietę (tag), numer linii, oraz offset w bloku.

W pamięci [[#Cache]] trzymamy bloki pamięci RAM

---
## Linie
Linia pamięci podręcznej to *slot*, w którym trzyma się blok pamięci.
W [[#Odwzorowanie bezpośrednie]] numer linii odpowiadający adresowi jest wpisany w adres.

## Etykiety
Etykieta (*tag*) to *identyfikator* bloku pamięci.
Używa się jej by stwierdzić, czy dany blok jest obecnie odwzorowany gdzieś w pamięci podręcznej.

---
## Odwzorowanie bezpośrednie
Linia, która zostanie zajęta przez pobierany blok jest wyznaczona przez *numer linii* adresu.

>Adres fizyczny = `__tag__|_nr linii_|__offset__`

^e9d535

Sprawdzając, czy dany blok jest zapisany w cache'u:
1. wyznaczamy `nr linii`
2. porównujemy `tag` w linii
3. jeżeli się zgadza, odczytujemy pamięć bloku w `offset`
4. jeżeli nie, dociągamy z RAMu


## Odwzorowanie asocjacyjne
Linie cache mogą być zajęte przez dowolny blok pamięci. 

> `___tag___|_offset_`
> Na przykład 10b offsetu pozwoli zaadresować bloki o rozmiarach 2^10 b = 1kB.
> Pozostałe 22 bity będą identyfikatorem bloku. 

Pozyskując dane:
1. `tag` jest porównywany z etykietami wszystkich zapisanych bloków
2. jeżeli mamy gdzieś zapisany ten blok, odczytujemy pamięć bloku w `offset`
3. jeżeli nie, dociągamy z RAMu

>[!tip] Porównywanie tagów bloków jest zaimplementowane hardware'owo, nie mikroprocesorem.

## Odwzorowanie wielokanałowe
Łączy zalety [[#Odwzorowanie bezpośrednie]] i [[#Odwzorowanie asocjacyjne]].
![[#^e9d535]]

Pierwsza warstwa ma odwzorowanie bezpośrednie. Wyznacza linię, w której możemy znaleźć blok.
==**Linia** składa się tutaj z całego układu pamięci asocjacyjnej.== W ramach linii interesuje nas etykieta.

1. wyznaczamy `nr linii`
2. ~~porównujemy `tag` w linii~~ ==sprawdzamy, czy `tag` jest zapisany gdzieś na linii==
3. jeżeli się zgadza, odczytujemy pamięć bloku w `offset`
4. jeżeli nie, dociągamy z RAMu

---
# Synchronizacja z pamięcią operacyjną
- Write-through
Zapis do pamięci cache jest natychmiast odwzorowywany w RAM-ie

- Write-back
Pamięć RAM jest oznaczona jako nieaktualna *bitem stanu*.

---




