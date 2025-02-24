# write
```asm
push msg_length
push OFFSET msg
push 1 ; std_out
call __write

add esi, 12 ; 3*4B
```

# read
```asm
push buf_length
push OFFSET buf
push 0 ; std_in
call __read

add esi, 12 ; 3*4B
```

# MessageBox
Dekoratory:
- A - ANSII
- W - widechar ([[Kodowanie znaków#UTF-16]])
- @16 - sumaryczny rozmiar argumentów
```
push 0
push OFFSET tytul
push OFFSET tekst
push 0
call _MessageBoxW@16
```

>[!warning] Konsumowanie stosu
>[[#write]] i [[#read]] **nie konsumują** argumentów: wymagają usunięcia parametrów `add esi, 12`.
>[[#MessageBox]] **konsumuje** argumenty w ramach implementacji wewnętrznej.
>![[3 sem/AKO/Przekaz argumentów#Przez pamięć]]