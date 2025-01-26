# Chroniony %% #todo%%
![[AKO_2024_cz_2.pdf#page=83]]
# Rzeczywisty
Procesor startuje program w trybie 16bitowym rzeczywistym i oddaje kontrolę w trybie 32bitowym chronionym.

adres fizyczny = rejestr segmentowy<<4 + offset

Rejestry segmentowe trybu 16bitowego rzeczywistego:
- `CS` code segment
- `DS` data segment
- `ES` extra segment 
- `SS` stack segment 
## Adres logiczny
w trybie rzeczywistym adres fizyczny ma postać `segment : offset`
>[!tip] Adresowanie bezpośrednie
>Żeby zaadresować znaną komórkę pamięci w trybie 32bitowym przed adresem należy podać słowo `ds`, np:
> ```asm
> mov eax, ds:[400000h]