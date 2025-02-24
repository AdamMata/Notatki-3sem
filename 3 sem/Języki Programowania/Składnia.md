---
aliases:
  - Syntax
---
Składnia każdego języka formalnego może zostać zdefiniowana [formalnie](https://en.wikipedia.org/wiki/Backus%E2%80%93Naur_form).

# Proces analizy składni
1. Analiza leksykalna
Tokenizacja (tworzenie *słów*), zajmuje się tym *skaner*.
2. Analiza składniowa
Parsing (tworzenie *wyrażeń*). Rolę zaczyna grać [[Semantyka]].
# Format
- Sztywny (kolumny kart perforowanych, miejsca znaczące)
- Swobodny (separatory, słowa zarezerwowane, kluczowe)
# Starszeństwo operacji
Zgodnie z *formatem swobody* człon należy do poprzedniego słowa kluczowego.
> Przykład:
```C
if (a) ; else if (b) ; else (c) ;
```
>$\iff$
```C
if (a) {

} else if b {

}
else c {

}
```

# Instrukcje złożone

# Składnia liniowa a strukturalna
W składni *liniowej* nie funkcjonują [[Przestrzenie nazw]].

W składni *strukturalnej* zmienne o niższym [[Przestrzenie nazw]] "nadpisują" zmienne globalne. Pozwala to zaoszczędzić [[Pamięć fizyczna]]. Kontroluje widoczność oraz *lifetime* obiektów