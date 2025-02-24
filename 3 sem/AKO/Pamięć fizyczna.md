# Komunikacja pamięć-procesor

 
---

# Rodzaje pamięci RAM
> [[AKO_2024_cz_5.pdf]]

| Rodzaj | Prędkość      | Odporność | Odświeżanie [^1] | Zużycie mocy |
| ------ | ------------- | --------- | ---------------- | ------------ |
| DRAM   | wolna (60ns)  | niska     | potrzebne        | niskie       |
| SRAM   | szybka (10ns) | wysoka    |                  | wysokie      |

[^1]: [[AKO_2024_cz_5.pdf#page=12|Proces odświeżania pamięci]]

## FPM DRAM
> Fast Page Mode

Stosuje zmodyfikowany [[#Cykl dostępu]]: wysyła wiele sygnałów CAS na 1 RAS. 

### EDO DRAM
> Extended Data Out

Ulepszony, bardziej precyzyjny [[#FPM DRAM]].

## SDRAM
> Synchronous

## DDR SDRAM
> Double Data-Rate Synchronous

Używa obu zboczy zegara.

---
# Rodzaje pamięci nieulotnej

## Flash
>[!Tip] [[AKO_2024_cz_5.pdf#page=52|Pamięć Flash]] pozwala na przechowywanie wielu bitów informacji w jednej komórce.
## ROM (MROM)
>Read-only memory ^[[[AKO_2024_cz_5.pdf#page=49]]]

Nieulotna, tj. nie wymaga ciągłego zasilania.
Zawiera:
- BIOS
- Adres *pierwszej instrukcji po włączeniu* `F000:FFF0` ([[Adresowanie#Segmentowe]])

 
### Rodzaje
- PROM - 1x programowalna
- EPROM - Erasable, wielokrotnie programowalna
> Kasowana za pomocą UV
- EEPROM - Electrically Erasable
> Kasowana elektrycznie
- NVRAM - Non Volatile RAM
> SRAM + EEPROM



---

# Cykl dostępu
1. **Sygnał RAS** (Row Address Strobe)
Wysyłany do RAMu po tym, jak magistrala adresowa ustabilizowała bity, gotowa do odczytu **rzędu**.
2. **Sygnał CAS** (Column Address Strobe)
Analogicznie, gotowa do odczytu **kolumny**.
3. Wysył na **magistralę danych**


>[!info] Zużycie energii
>$$E = V^2 \cdot f$$
>Zwiększając napięcie znacznie rośnie zużycie energii, a za tym temperatura komponentów. Ogranicza to możliwości pamięci.

# 
## Lokalność czasowa
Częste, szybkie odwołania do tych samych komórek
## Lokalność przestrzenna
Podobne adresy

 
 >[!tldr] [[AKO_2024_cz_5.pdf#page=28|Hierarchia układów pamięci]]
 >>[!warning] Slajd niekompletny o procesory wielordzeniowe



# [[Pamięć podręczna]]