**(asemblacja)**
Dwuprzebiegowa:
1. Preprocesor (translacja)
	Wyrażenia [[Adresowanie#Efektywne]], łańcuchy znaków, [[Dyrektywa OFFSET|Dyrektywa OFFSET]], *słownik symboli*, [[Kodowanie instrukcji]]
2. Kompilacja właściwa
	Wyrażenia wykorzystujące [[Licznik lokacji]]

~~`mov al, ax * 5`~~ - mnożenie w czasie wykonania
`mov al, 2*5` - wyrażenie czasu translacji

**Dyrektywa ORG** wpisuje dowolną wartość do [[Licznik lokacji]]. ^5d8bb8

Słownik symboli zawiera:
- adresy obszarów pamięci
- [[Instrukcja#Kod rozkazu]]

tworzy plik listingowy .LIS ^5d4ed4