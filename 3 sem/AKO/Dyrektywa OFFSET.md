Generuje [[Pamięć|adres]] obszaru zamiast jego wartości.
```asm
.data
liczba: db 17

...

.code
mov esi, offset liczba
mov ah, [esi]
```