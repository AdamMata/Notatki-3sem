[[AKO_2024_cz_1.pdf#page=46]]

1. Fetch
2. Decode
3. Read
4. Execute
5. Write
^cykl-rozkazowy
# Program counter ([[Rejestry#^7f4388|EIP]])
> wskaźnik instrukcji/licznik rozkazów

Określa położenie *kolejnej* [[Instrukcja|instrukcji]].
[[Rejestry]] `eip` (32-bit) `rip` (64-bit) trzymają [[Pamięć fizyczna|adres]] komórki z *następną* instrukcją.
Po zczytaniu procesor już prosi [[Pamięć fizyczna]] o kolejny rozkaz.

*Rozkaz sterujący* (skokowy) zmieni `eip` po wykonaniu.
> np. branch, jump, itp.

[[Najważniejsze instrukcje#Skoki|Rozkaz sterujący warunkowy]] wykona skok jeśli spełniony jest pewien warunek. Najczęściej warunek musi zostać obliczony wcześniej innymi instrukcjami. 

*Niesterujący* zwiększy licznik po odkodowaniu.
*Zwiększy*, nie zinkrementuje! Zwiększy się o długość instrukcji i argumentów. ^[[[Kodowanie instrukcji]]]