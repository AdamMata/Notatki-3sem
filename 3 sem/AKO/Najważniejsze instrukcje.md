# mov
`mov gdzie(rejestr) co(literał/rejestr/pamięć)`
>[!Warning] Nie ma `mov pamięć pamięć`!
>Zobacz [[Kodowanie instrukcji]].

W większości modeli adres zapisany pod adresem np. `dane` zapisuje się bez `[]`
> `mov rax dane`

## movzx
Używany do przemieszczania danych do większego rejestru. **Zeruje** wszystkie starsze bity.
## movsx
Jak `movsx`, tylko używa **wartości [[Flagi|ZF]]**. Zachowuje wartość liczby w U2.

---
# add/sub
...oraz wszystkie inne obliczenia dwuargumentowe

`add co_i_dokąd do_czego`
Jak odwołać się do pamięci?
> `[adres]`, np. `[100h]`

## adc
**dodatkowo** dodaje do wyniku [[Flagi|flagę carry]].

---
# mul/div
Wyjątkowo mnożenie jest jednoargumentowe. W zależności od rozmiaru czynnika wybierane są [[Rejestry|rejestry]] do odczytu i zapisu:
8-bit: `arg * al` -> `ax`
16-bit: `arg * ax` -> `eax`
32-bit: `arg * eax`->`rax`
64-bit: `arg * rax`->`rdx:rax` (młodsze bity w `rax`, starsze bity w `rdx` ([[Endian#Big endian|big endian]]))

`div ebx` = $\frac{edx:eax}{ebx}$ -> iloraz: `eax`, reszta: `edx`

---
# lea
*load effective address*
![[Adresowanie#^5bb429]]

```
lea ebx, [tag+edi+1]
```
$$\equiv$$
```
mov ebx, offset tag
add ebx, edi
add ebx, 1
```

---
# push/pop
Wepchnij/zdejmij wartość na [[Stos]]. Potrzebne przy wywoływaniu funkcji.
## pusha/popa
*Push all/pop all* - zapamiętuje wszystkie [[Rejestry#Rejestry ogólne]]

---
# db
*define byte*. `db dana, ... dana`
Można użyć do [[Kodowanie instrukcji]].
# nop
*no operation*. Pusty przebieg procesora.
# xchg
*exchange*. zamienia dane z dwóch miejsc
# bswap
Zmienia [[Endian|Endianowość]] rejestru.
#
---
# Rozkazy sterujące
Realizują [[Flow control|Kontrolę przepływu]].
## Skoki
### Bezpośrednie
W [[Kod maszynowy|kodzie maszynowym]] zazwyczaj zajmuje 2 bajty: [[Instrukcja#Kod rozkazu]] i *zakres skoku*. Współczesne kompilatory w miarę potrzeby rozszerzają zakres skoku do 4 bajtów. Cała instrukcja zajmuje wtedy 6B.
### Pośrednie
Zamiast etykiet używają *adresów zawartych w podanym rejestrze* lub w *obszarze danych*. Innymi słowy instrukcja docelowa skoku jest zmienną. Nadpisują `eip`. Przydatne m.in. przy polimorfizmie.

### 
---
### Warunkowe
- [[Flow control#Przepływ prosty|Kontrola przepływu]]: `loop`, `jae`, `jg`, etc.
### Bezwarunkowe
- `jmp`
- [[Wywoływanie funkcji]]: `ret`, `call`, `int`

---

>[!summary]- Tabele skoków i testowanych flag
> ![[AKO_2024_cz_2.pdf#page=33]]
> ![[AKO_2024_cz_2.pdf#page=136]]

^7a9fd0

| Rodzaj liczby                          | Mnemonik porównania                     |
| :------------------------------------- | --------------------------------------- |
| [[Kodowanie liczb#NKB]]                | above/below/equal                       |
| [[Kodowanie liczb#U2]]                 | greater/lesser/equal                    |
| [[Kodowanie liczb#Zmiennoprzecinkowe]] | brak; użyj odejmowania w [[Koprocesor]] |

^e04c4b

## loop

>[!warning] `loop` nie rozszerza swojego zakresu!
>`loop` jest zawsze [[Kodowanie instrukcji|kodowane]] na 2B, zakres skoku jest ograniczony \[-128,127].

>[!info] `loop` używa rejestru `ecx`
>`loop` działa w dwóch krokach wykonywanych **w ustalonej kolejności**:
>1. dekrementacja ecx
>2. przerwanie jeżeli ecx = 0
>
>>[!warning] [[Stos#^a7507b]] 
>>Jeżeli [[Podprogram|funkcja]] wywoływana w ramach pętli używa `ecx`, nie ma obowiązku przywrócenia zastanej wartości!

>[!warning] `loop` nie ustawia żadnych [[Flagi|flag]]
>Nawet jeżeli dekrementacja wywoła przepełnienie!

## [[Wywoływanie funkcji]]
### call
Wywołaj [[Podprogram]] (oznaczony słowem `extern`)
`call funkcja`
1. odkłada adres funkcji
2. skok bezwarunkowy
3. wykonuje do napotkania `ret`
4. zczytuje ze stosu adres powrotu i wpisuje go do `eip`

>[!tip] Nie ma `mov eip`
>Aby włożyć coś do `eip` zrób:
>```asm
>push coś
>ret
>```
>Pamiętaj że używasz przy tym [[Stos|stosu]].
^909b56
### ret
Wczytuje adres powrotu ze stosu i wykonuje skok bezwarunkowy.

---
### int
interrupt - [[Podprogram]] systemowy. 
>[!warning] Nie mylić z [[Przerwanie systemowe]]!
> *Obsługa* przerwań i podprogramów jest analogiczna, ale to różne rzeczy.

^09dee0

![[Interfejs ABI#^c08508]]


Ślad podprogramu systemowego na [[Stos]]: eip, cs, flagi
### iret
Kończy obsługę przerwania.

#
---

# SET
np. `setc ax` "jeżeli carry, wpisz 1"
%% #todo research instrukcje z grupy set %%

# Przesunięcia bitowe
>[!tldr]- Slajdy
>![[AKO_2024_cz_3.pdf#page=113]]

**Użycie:** `shr rejestr, o_ile`

|    Rozkaz    | Używa [[Flagi\|CF]]? | Ostatni bit                            | Uwagi                                                   |
| :----------: | :------------------: | :------------------------------------- | ------------------------------------------------------- |
| `shr`, `shl` |         TAK          | przepada, zapisany do CF               | *shift right/left*                                      |
| `sar`,`sal`  |         TAK          | przepada, zapisany do CF               | Przesunięcie arytmetyczne - pomija najstarszy bit znaku |
| `ror`, `rol` |         TAK          | rotuje do najmłodszego, zapisany do CF | *rotate right/left*                                     |
| `rcr`, `rcl` |         TAK          | rotuje poprzez CF                      | *rotate with carry right/left*                          |

# Testy bitowe
`BT r/m, bit`
`BTR` - reset (ustaw 0)
`BTS` - set (ustaw 1)
`BTC` - complement (flip)

---
# IN/OUT
![[Urządzenia zewnętrzne#Najważniejsze instrukcje `IN` `OUT`]]

---
# [[Instrukcje koprocesora]]

# [[Rozkazy na blokach danych]]

# [[Instrukcje SSE]]