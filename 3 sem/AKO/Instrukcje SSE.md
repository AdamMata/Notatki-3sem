---
aliases:
  - XMM
  - SIMD
  - Streaming SIMD Extensions
---
>[!Warning] Ten materiał **nie jest poruszany na wykładzie**, tylko na **ćwiczeniach**, a *może* pojawić się na egazminie - zarówno teoretycznym, jak i praktycznym!

^db9ad6
> Zobacz też: [[Instrukcje AVX|Advanced Vector Extensions]]

Używają rejestrów XMM. Przydatne do operacji typu *Single Instruction, Multiple Data* (SIMD).

# Rejestry XMM
8 rejestrów *128* bitowych `xmm0` do `xmm7`.

# Instrukcje
Dzielą się na operacje typu **scalar** i **packed**.
- Scalar (SS)
Działa na jednej, najmłodszej liczbie 32-bitowej. (SISD)
- Packed Singles (PS)
Wykonuje równoległe operacje na 4 liczbach 32-bitowych. (SIMD)

## Na [[Kodowanie liczb#Zmiennoprzecinkowe|floatach]]

| Operacja               | Scalar `...ss`                                                     | Packed `...ps`                                   |
| ---------------------- | ------------------------------------------------------------------ | ------------------------------------------------ |
| Przemieszczanie danych | `movss`                                                            | `mov*ps` [^movaps]                               |
| Arytmetyka             | add, sub, mul, div, rcp^[Reciprocal - odwrotność $\frac{1}{x}$]... | ... sqrt, max, min, rsqrt ^[$\frac{1}{\sqrt x}$] |
| Porównania             | cmp, comi, ucomi                                                   | cmp                                              |
| Bitowe                 | ---                                                                | and, or, xor, andn^[nand]                        |
**Przykład użycia**
```asm
movaps xmm0, [v1] ; v1 - 4 liczby 32B
addps xmm0, [v2]
movaps [sum_v1v2], xmm0
```

>[!Warning] Operacje `sqrt**` i `rsqrt**` mają 2 operandy!
>Potrzebny jest rejestr, gdzie zapisać wynik. Np.:
>`sqrt xmm2, xmm1`


## Na [[Kodowanie liczb#Całkowitych|całkowitych]]

| Operacja        |                                            |
| --------------- | ------------------------------------------ |
| Przemieszczanie | `pEXTrw` (extract word), `pINSrw` (insert) |
| Arytmetyka      | `pADD*`^[`*`- B/W/D/Q]                     |
[^movaps]: `*` - **A**ligned/**U**naligned ([[Wyrównanie naturalne]]), **L**ow/**H**igh, **L**ow to **H**igh/**H**igh to **L**ow (przy przemieszczaniu `xmm-xmm`) / **M**a**SK** (maska znaków - 4/8bitowy ciąg znaków singli z rejestru)

