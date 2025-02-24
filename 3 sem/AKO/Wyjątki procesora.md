^[[[AKO_2024_cz_4.pdf#page=69]]]
Nazywane **przerwaniami sprzętowymi wewnętrznymi**. Proceury obsługi wyjątków mają swoje [[Tablica wektorów przerwań|deskryptory]].


> [[AKO_2024_cz_4.pdf#page=72|Przykładowe wyjątki]]
> https://wiki.osdev.org/Exceptions - lista wyjątków wraz z typami


## Niepowodzenia (Faults)
Recoverable usterki. Większość wyjątków leży w tej kategorii.
- Dzielenie przez 0
- Przepełnienie
- *Page Fault*: strona [[Pamięć|RAM]] przeniesiona do pamięci wirtualnej na dysku
- Nieznany rozkaz

## Pułapki (Traps)
Stany kontrolowanej bezczynności
- m.in. breakpointy debuggera.
## Błędy nienaprawialne (Aborts)
Nie da się wskazać błędnej operacji ani bezpiecznie kontynuować.
- *Double fault*: Błąd obsługi [[#Niepowodzenia (Faults)]]