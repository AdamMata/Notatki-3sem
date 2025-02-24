# Teoretyczne
Układy opracowanie przez (głównie) [CIE]().
## CIE RGB
Wymaga stosowania ujemnych składowych.
Trik na wyłącznie dodatnie składowe polega na składowych poza spektrum widzialnym.
### CIE XYZ
Transformacja układu CIE RGB która zapewnia dodatnie składowe. Abstrakcja uniemożliwia nazwanie osi.
![[CIE-XYZ.png]]
>[!note] Ograniczenia sprzętowe
>Na powyższym diagramie w ramach figury leżą wszystkie postrzegalne ludzkim okiem kolory (wg [[Teoria Younga-Helmholtza]]). Wyświetlacz używa tylko [[Modele kolorów#RGB|niektórych dostępnych barw]].

Przestrzeń barw jest mniej więcej ostrosłupem (ma podstawę *podkowy*).
Na Y jest luminancja, na XZ: barwa.
Standardowym wycinkiem jest przecięcie przez płaszczyznę $X+Y+Z=1$. 
Na wskroś punktu białego leżą *kolory dopełniające*.
Problem: gradient kolorów nie jest wszędzie równomierny (taka sama odległość nie oznacza równie "różnych" kolorów).

---
## CIE LUV
[[Przekształcenia#Nieliniowe|Nieliniowy]] z CIE XYZ
- L - jasność 
- U - RG
- V - YG
**Percepcyjna jednorodność**: Różnica we wrażeniu jest proporcjonalna do odległości. 
Kolor cechują:
- chroma $c_{ab}^* = \sqrt{A^2 + B^2}$ (odległość od bieli)
- odcień $h_{ab}^* = \arctan{\frac{B}{A}}$ (kierunek)
## CIE LAB
Opisuje barwy światła odbitego. Transformacja nieliniowa modelu [[Kolor#CIE XYZ]].

---
## TekHVC
**Jednorodny percepcyjnie**. Zależny nieliniowo z CIE.
Wykorzystuje intuicyjne składowe ([[Kolor#HSV]]). 
Barwa H w przedziale 0..360°. Chroma $C$ w przedziale $0..100$, $V=L_{LUV}$ (%)

---
# Techniczne
## RGB
> Red Green Blue

Mieszanie [[Kolor#Addytywne]]. Używany w monitorach CRT, LCD, projektorach. Reprezentuje ok. 16,7mln barw dla bajtu na kolor.
>[!tip]
>Ludzkie oko osiąga wrażenie ciągłości koloru już dla 5 bitów na kolor w RGB
## HSV
> Hue Saturation Value

Bardziej intuicyjny niż [[Kolor#RGB]] Model użyteczny dla grafików, użytkowników.
Hue: kąt od czerwieni w kierunku zielonego R = 0, G = 120, B = 240
S: odległość od bieli
V: odległość od czerni %% #todo zdj z prostokątem hsv: zazębione trójkąty %%
### HSL
> Hue Lightness Saturation

Jasność 0.5 (szary) jest punktem wyjścia dla kolorów podstawowych. Powyżej 0.5 wszystkie kolory dążą do bieli.

---
## CMY(K)
> Cyan Magenta Yellow (blacK)
> *cyjan fuksja żółty (czarny)*

Mieszanie [[Kolor#Subtraktywne]]. Czerń jest używana w drukarkach dla poprawy jakości czerni bez używania dużych ilości pigmentu oraz przyspieszenia schnięcia (schnie jeden tusz zamiast trzech).
### CMY -> CMYK
1. Wyciągamy część wspólną CMY do $K = k\cdot \min (C,M,Y)$. W praktyce wyciągamy tylko pewną część $k$ od 0 do 1 dobieraną doświadczalnie.
2. $C, M, Y -= K$

---
## YUV, YIQ
Sygnały analogowe używane w transmisji telewizyjnej. Europejska transmisja PAL używa YUV, Amerykańska NTSC - YIQ. Liniowe przekształcenie RGB.
Kompatybilne z transmisją czarno-białą. Jasność (Luminancję) $Y$ koduje się tak samo jak biel, kolor koduje się w pustych miejscach.
>[!tip]
>W związku z kompatybilnością wsteczną z telewizją czarno-białą kanał $Y$ przekazuje najwięcej informacji.

$$ Y = 0,299R + 0,587G, 0,114B$$
$$RGB_T = RGB-T$$
W YUV $U$ zależy liniowo od $B_T$, $V$ od $R_T$.
W YIQ $I$ oraz $Q$ oba zależą od $R_T$ i $B_T$.

YUV i YIQ są zależne liniowo między sobą nawzajem.

Określone standardami EBU i FCC.
## YD_bD_r
Kodowanie systemu SECAM. Liniowy względem RGB.
## YC_bC_r
Używany w taśmach magnetycznych. Pozwala na równomierne rozłożenie bitów 0 i 1, co zapobiega rozmagnesowaniu.
 %% #todo slajd z kodowaniem 4:x:x %%

# Zależności modeli

|                                       | Zależny liniowo z [[Modele kolorów#CIE RGB\|CIE RGB]]? | Jednorodny percepcyjnie? |
| ------------------------------------- | ------------------------------------------------------ | ------------------------ |
| [[Modele kolorów#CIE XYZ\|XYZ]]       | ?                                                      |                          |
| [[Modele kolorów#CIE LUV\|LUV]]       |                                                        | TAK                      |
| [[Modele kolorów#CIE LAB\|LAB]]       |                                                        | TAK                      |
| [[Modele kolorów#TekHVC\|TekHVC]]     |                                                        | TAK                      |
| [[Modele kolorów#RGB\|RGB]]           |                                                        | TAK                      |
| [[Modele kolorów#HSV\|HSV]]           |                                                        |                          |
| [[Modele kolorów#CMY(K)\|CMYK]]       | ?                                                      | ?                        |
| [[Modele kolorów#YUV, YIQ\|YUV, YIQ]] |                                                        |                          |
| [[Modele kolorów#YC_bC_r\|YC_bC_r]]   |                                                        |                          |
 