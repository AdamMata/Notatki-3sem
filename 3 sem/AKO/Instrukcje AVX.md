---
aliases:
  - YMM
  - ZMM
  - Advanced Vector Extensions
---
![[Instrukcje SSE#^db9ad6]]
> Rozszerzenie [[Instrukcje SSE]].

# Rejestry YMM, ZMM
> Advanced Vector Extensions

Obecne w nowszych architekturach, pozwalają zachować liczby 
- 256b (YMM) 
- 512b (ZMM)
![[Rejestry AVX.png]] ^[https://en.wikipedia.org/wiki/Advanced_Vector_Extensions]
Rejestrów jest w sumie 16 (`zmm0-zmm15`), albo 32 w standardzie AVX-512.

# Operacje
`vbroadcast**` ss(scalar)/sd(double-precision [[Instrukcje SSE#Na Kodowanie liczb Zmiennoprzecinkowe floatach|float]])
`vbroadcastf128` 
> kopiują pamięć do rejestru XMM/YMM

