[[AKO_2024_cz_4.pdf#page=11]]

# Uruchamianie trybu tekstowego `3`
```asm
mov ah, 0
mov al, 3
int 10h
```
(analogicznie do [[Tryb graficzny#Uruchamianie trybu graficznego 13h]])

Początek obszaru tekstu: `B8000` ([[Adresowanie#^04e618|adres fizyczny]])
2B na znak:
*Bajt znaku ASCII*
*Bajt atrybutu*: `mRGB` tła + `iRGB` znaku, gdzie `m` to migotanie a `i` to intensywność