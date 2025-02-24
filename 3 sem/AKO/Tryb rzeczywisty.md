Procesor startuje program w trybie 16-bitowym rzeczywistym i oddaje kontrolę w trybie 32-bitowym chronionym.

# Segmenty
 ^[[[AKO_2024_cz_4.pdf#page=14]]]
w trybie rzeczywistym adres fizyczny ma postać `segment : offset`. ([[Dyrektywa SEGMENT]])
adres fizyczny = rejestr segmentowy<<4 + offset. ^3e3f99

Rejestry segmentowe trybu 16-bitowego rzeczywistego:
- `CS` code segment
- `DS` data segment
- `ES` extra segment
	- kolejne dodatkowe segmenty `FS`, `GS`, ...
- `SS` stack segment 

>[!important] Rejestry segmentowe mają 16b
>Występują tylko w trybie 16-bitowym rzeczywistym.


>[!tip] [[Adresowanie#Natychmiastowe]]
>Żeby zaadresować znaną komórkę pamięci w trybie 32-bitowym przed adresem należy podać słowo `ds`, np:
> ```asm
> mov eax, ds:[400000h]
>```

![[Tryb tekstowy]]

![[Tryb graficzny]]
