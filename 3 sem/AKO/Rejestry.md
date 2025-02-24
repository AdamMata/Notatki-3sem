*Procesor* wyposażony jest w wiele grup rejestrów. Traktujemy je jako lokalne zmienne procesora. Dzięki nim ograniczamy dostępy do [[Pamięć fizyczna|Pamięci]].
#
---

# 16-bit
Od dawna przestarzały, będziemy go używać na kursie za pomocą [[Tryb rzeczywisty|trybu rzeczywistego]] naa emulatorze systemu DOS.
#
---
# 32-bit
## Rejestry ogólne
`eax, ebx, ecx, edx`
`ah, al`
`bh, bl`
`eax`: od 0 do 31
`ax`: od 0 do 15 \[0, 15)
`ah`: (high quarter) \[8,16) (1/4 `eax`)
`al`: (low quarter) \[0,8)

>[!Warning]
>Zczytując 1 bajt do *starszej* części rejestru niższe podrejestry będą uzupełnione następnymi blokami pamięci!

## Rejestry szczególne (konwencjonalne)
- `esi`, `edi`: indeksy
- `ebp`: Rejestr bazowy (*base pointer*)

- `esp`: [[Stos|Stack]] pointer
- `eip`: READ ONLY ^[![[Najważniejsze instrukcje#^909b56]]] instruction pointer ^7f4388
#
---

# 64-bit
Nie ma wyższych ćwiartek[^ćwiartki] (8-16) (są, ale nie są polecane, jest na to czarna magia)

Dodatkowo dochodzą:
- rejestry `R0-R15`
Młodsze bity są nazywane rozmiarami słów (`R8D` = młodszy `dword` (32 bity, jak `eax`))
- rejestry [[Instrukcje SSE|XMM]], [[Instrukcje AVX|YMM]], [[Instrukcje AVX|ZMM]]
Używane do operacji na liczbach zmiennoprzecinkowwych (zamiast [[Koprocesor]]a) oraz [[Wywoływanie funkcji|zwracania wartości]].

![[AKO_2024_cz_1.pdf#page=31]]
#
---

# [[Flagi|Rejestr stanu procesora]]

# [[Instrukcje SSE#Rejestry XMM]]

[^ćwiartki]: 1/4 32 = 1/8 64