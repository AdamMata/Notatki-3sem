# [[Algorytm|Algorytmy]] [[Rekurencja|rekurencyjne]]
## Dziel i rządź
Dla funkcji złożonej $T(n)$ z krokiem rekurencyjnym $a\cdot T(\frac{n}{b}) + d(n)$ dla liczb $n=b^k$:
$$T(n) = ca^k + 
\sum_{i=0}^{k-1}{a^i \cdot d(b^{k-i})}$$

^c38d54

> Funkcja rozwiąże $a^k$ podproblemów w czasie stałym $c$.
> Rekurencyjnie wywoła się na głębokość $k-1$, i w każdym kroku spędzi: 
> 1. $a^i$ czasu na rozwiązanie ich wszystkich
> 2. $d(b^{k-i})$ czasu na złączenie $b$ podproblemów o rozmiarze $k-i$

>[!warning] $d$ dwóch zmiennych 
>$d(n_1)\cdot d(n_2)$ patrz [[Giaro.pdf#page=12]]
## Krok wstecz
[[Giaro.pdf#page=13]]: wzór analogiczny do [[#^c38d54|typu "dziel i rządź"]].

---