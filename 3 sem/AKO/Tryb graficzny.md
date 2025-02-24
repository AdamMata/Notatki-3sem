[[AKO_2024_cz_4.pdf#page=16]]

# Uruchamianie trybu graficznego `13h`

```asm
mov ah, 0   ; tryb sterownika
mov al, 13h ; tryb graficzny
int 10h     ; funkcja BIOSa
```

# 
---
- Obraz 320px x 200px
- 256 kol/B według palety
- Piksele nie są kwadratowe, tryb jest przystosowany do monitorów o wymiarach 4:3
- Początek obszaru pamięci: `A0000`

![[Paleta 13h.png]]
