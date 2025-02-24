# Dziel i zwyciężaj

>[!info] Wzór na złożoność czasową
$$ T(n) = \Theta (n^{ \log_b(\max{\{a, d(b)\}}) } \cdot (\log n)^*)$$
\* : tylko jeżeli $a = d(x)$
>>[!warning] $d(x)$ musi być *multiplikatywna*
>>$d(x_1 \cdot x_2) = d(x_1) \cdot d(x_2)$ 
# Krok wstecz
>[!info] Wzór na [[Złożoność czasowa|Złożoność Czasową]]
>![[Krok_Wstecz.png]]
>>1. Jeżeli $d(n)$ razy dowolny wielomian nie jest wykładnicza
>>2. Jeżeli $a$ do jakiejś potęgi prześcignie $d(n)$
>>3. Jeżeli $a$ do dowolnej potęgi nie dogoni $d(n)$ 
