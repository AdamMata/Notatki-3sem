#język 
Konwencja CamelCase dla klas i camelCase dla zmiennych *wymuszona kompilatorem*.

# Definicja funkcji

```Haskell
let sumOfSq a b = sq(a) + sq(b) where sq a = a*a
```
```Haskell
let foo Num => Num
foo 0 = 0
foo n = foo (n-1)
```

# Złożenia funkcji
```Haskell
let times2plus1 = times2 . plus1
```

# Instrukcje warunkowe
>[!info]- `if` zawsze występuje z `else`
>Ponieważ stanowi deklarację *alternatywnej wartości*, a nie [[Flow control|przepływu]] obliczeń.
```Haskell
case n of
	1 -> One
	0 -> Zero
	_ -> Many -- Default case
```
# Indentacje
Indentacje są **obowiązkowe** i definiują [[Scope|bloki kodu]].^[Jak w [[Python|Pythonie.]]]

# 

# Listy
```Haskell
-- Konkatenacja list
concat [[1..3], [4,5]]
[1,2,3] ++ [4,5]

['a', 'b', 'c'] == "abc"
```

```Haskell
head [1..9] -- 1
tail [1..9] -- [2..9]
```

## Indeksowanie
```Haskell
[1..9] !! 5 -- 5
```

## Consing (Konstruowanie)
```Haskell
0:[1..5] ++ 6:7:8:9:[]
```

## Mapowanie
```Haskell
map (*2) [1..9] -- uproszczone wyrażenie lambda
map (\ x -> x*2) [1..9]
-- [2,4..18]
```
^3fcbda
## Filtracja
```Haskell
filter [1..9] [1,0,0..0] -- [1]
```

## Folding ([[Model funkcyjny#^2b48fd|Agregacja]])
```Haskell
foldr (*) 1 [1..9] -- 9! (od prawej)
```

## `zip` i `unzip`
Tworzą z pary list listę par i vice versa.
### `zipWith`
Przeprowadza `zip` i wykonuje działanie na parze.
```Haskell
zipWith (+) [1,2,3] [0,10,20] -- [1, 12, 23]
```

# 
---

# Moduły
```Haskell
Prelude> import Data.List
Prelude Data.List> reverse [1..5] -- [5..1]
```

# Pattern matching
#todo

# Tacit programming
```Haskell
let sum = foldr (+) 0 -- implicit argument
sum [1,2,3]
```

```Haskell
let sq = (^2)
```

# [[Rachunek lambda|Wyrażenia lambda]]
```Haskell
(\ x -> x+1) -- '\' oznacza lambda
```