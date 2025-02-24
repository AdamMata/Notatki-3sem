Oznacza linijkę z której [[Proces kompilacji|kompilator]] obecnie asembluje kod.

Dostęp odbywa się poprzez symbol `$`.
`$+3eb0` -> "przesuń licznik lokacji o `3eb0`."

```asm
text db '...'
length = $ - text
```

[[Dyrektywa ORG]] *ustawia* licznik lokacji.
```
ORG $+24 ; pomiń następne 24 liniki
```