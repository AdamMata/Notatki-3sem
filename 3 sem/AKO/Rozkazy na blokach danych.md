Jeżeli chcemy wykonać jedną instrukcje na dużym bloku 
danych
>[!tldr]- Slajdy
>![[AKO_2024_cz_3.pdf#page=189]]

# Ostatni znak reprezentuje wielkość danych w bloku
- MOVSB - przesłanie bajtu
- MOVSW - przesłanie słowa
- MOVSD - przesłanie podwójnego słowa

# Działanie tych rozkazów
1. Wykonanie rozkazu zgodnie z dalszym opisem
2. W zależności od [[Flagi|DE]]:
	- DE=0 Zwiększenie rejestrów EDI/ESI o ilość bajtów zgodną z rozkazem (1,2 lub 4)
	- DE=1 Zmniejszenie rejestrów EDI/ESI o ilość bajtów zgodną z rozkazem (1,2 lub 4)

# Przedrostek REP

Działa podobnie jak [[Najważniejsze instrukcje|LOOP]], w rejestrze [[Rejestry|ECX]] należy umieścić wielkość bloku danych, uwzględniając wielkość pojedyńczej jednostki danych.
> [!example] 
> > Chcemy skopiować tablice 58 słów do innego miejsca w pamięci. Dlatego że słowo = 2bajty, rzeczywisty rozmiar bloku danych to 116 bajtów.
> > ```
> > MOV ECX, 58
> > REP MOVSW
# Rozkazy 
### MOVSx 
> [!warning] > 
> ### MOVSx to nie to samo co [[Najważniejsze instrukcje|MOVSX]]
> tutaj stosuje x jako znacznik rozmiaru danych (B, W, D)^[Byte, Word, Double word]
 
 MOVSx kopiuje zawartość pamięci na który wskazuje ESI do pamięci na którą wskazuje EDI. Następnie dodaje do rejestrów rozmiar danej w bajtach.
 
 Kod `MOVSB` jest analogiczny do:
 ```
 MOV AL, [ESI]
 INC ESI
 MOV [EDI], AL
 INC EDI
```
Z tym, że zachowuje wartość `AL`.
## LODSx
Robi to co MOVSx ale przesyła zawartość x-bajtową na która wskazuje DS:SI do EAX (lub AX, AL).
## STOSx
Działa odwrotnie do LODSx, przesyła zawartość EAX (lub AX, AL) do pamięci na która wskazuje ES:DI. Uzywa się tez go do zerowania obszaru danych wielkości x.
## SCASx
Porównuje wartość na która wskazuje ES:DI do tej w EAX (lub AX, AL), ustawia flagi podobnie jak odejmowanie.
## CMPSx
W nim możemy wybrać które z ESI, EDI będzie source a które dest. Porównujemy blok danych ESI z blokiem danych EDI. Po każdym porównaniu flagi sa ustawiane. Prefix REP jest tutaj bezużyteczny, zamiast niego używamy:
```
REPE --powtarzaj dopóki równe
REPNE --dopóki nierówne
REPZ --dopóki zero
REPNZ --dopóki nie zero
```

^c7e432

