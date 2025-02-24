---
aliases:
  - Rejestr stanu procesora
  - Rejestr flag
  - Rejestr znaczników
---


# Rejestr stanu procesora
> Rejestr znaczników/flag

- `CF` - przeniesienie
- `ZF` - zero
- `DF` - kierunek *przesuwania* [[Najważniejsze instrukcje#Instrukcje powtarzalne]]
- `SF` - znak
- `PF` - parzystość
- `OF` - przepełnienie
- `IF` - wł/wył obsługa [[Przerwanie systemowe|przerwań]]. ^df39b0


Każdy bit odpowiada jakiejś fladze instrukcji dopiero co wykonanej. 
>[!warning] Nie wszystkie instrukcje wpływają na flagi!

Bity 12-21 są użyteczne dla systemu operacyjnego.
np. [[Mnemonik]] `CPUID` dostępny jeśli bit 21 jest `1`.
## Rozkazy zmiany
`clc` zmienia `CF` na 0, `stc` na 1.
`pushf`, `popf` dumpują/ściągają flagi na/ze [[Stos|stosu]].