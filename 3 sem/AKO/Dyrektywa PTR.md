Unieważnia ostrzeżenie kompilatora o czytaniu danych o niepożądanym/niekompatybilnym zadeklarowanym rozmiarze.
>[!warning] `PTR` działa tylko przy zapisach *do pamięci!*
>Przy zapisach do [[Rejestry|rejestru]] zawsze znany jest rozmiar docelowy, i taki zostanie wykorzystany.

Potrzebny m.in. przy wczytywaniu *literałów* do [[Pamięć|pamięci]].
```asm
mov [80000h], dword ptr 3 ; zapisuje 3 na czterech bajtach
```