---
aliases:
  - ABI
  - Application Binary Interface
  - Interfejs Binarny
---
![[AKO_2024_cz_3.pdf#page=28]]

Definicje tego, która funkcja korzysta z których rejestrów i do czego ich używa.
[[API]] stanowi abstrakcję ABI. Czytelne nazwy funkcji i ich analogi w ABI są zawarte w bibliotekach systemowych `.dll`

[[Wywoływanie funkcji]] odbywa się według interfejsu ABI, zgodnego ze [[Wywoływanie funkcji#Standardy|standardem]].

[[Najważniejsze instrukcje#INT]]: instrukcja `INT kod` wywołuje funkcję systemową [[OS]]a. `INT` oznacza **interrupt**: [[Przerwanie systemowe]].
Kody pozyskuje się z **wektora funkcji systemowych** ([[Tablica wektorów przerwań]]). ^c08508