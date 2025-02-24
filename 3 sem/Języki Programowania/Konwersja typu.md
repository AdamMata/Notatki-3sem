
# Niejawna (standardowa/zawężenie)
- Możliwa utrata dokładności
# Promocja (rozszerzenie)
- Powrót [[Podtyp]] do typu nadrzędnego
# Jawna (rzutowanie)
```C
int a = 3;
float b = 1.5;

a += (int)b; // 4
```
# Automatyczna
Zdefiniowana przez użytkownika, ale wykonywana *implicite*.
```C++
class Num {
    operator int();
}

Num num;
int a = num + 1;
```