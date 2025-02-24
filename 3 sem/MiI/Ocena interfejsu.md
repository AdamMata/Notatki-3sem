Ocena powinna mieć miejsce *jak najwcześniej* i *jak najczęściej, na bieżąco*. Wczesne wykrycie błędu zapobiega marnowaniu pracy.

>[!tip] Ostatecznym kryterium jest zadowolenie użytkownika

^673363

# Miary jakości
- Wydajność obsługi
- Prostota obsługi (minimalizacja błędów)
- Usuwanie/naprawianie/wycofywanie błędów obsługi ^05233b
- Łatwość i trwałość nauki obsługi (intuicyjność)
- Customizacja interfejsu
- ![[#^673363]]
# Klasyfikacja metod oceny

**Na podstawie użytkownika**
- obiektywne: pomiar napięcia psychicznego
- subiektywne: wywiad, ankieta

**Ze względu na zakres**
- ogólne: heurystyki, założenia
- szczegółowe: ocena funkcjonalności, [[Interfejsy#GOMS]]

**Ze względu na źródło wiedzy**
- od użytkownika
- od specjalisty
- od teorii i dobrych praktyk

# Heurystyka
Ocena dokonywana przez zespół ekspertów, oparta na ich doświadczeniu i przewidywaniu.

**Kryteria oceny:**
- Wizualizacja stanu (trybu) systemu
- Stosowanie języka znanego użytkownikowi
- Swoboda *kolejności* i *sposobu wykonania* działań 
	Również możliwość cofania błędnych decyzji. Łączy się z możliwością customizacji: system nie powinien blokować użytkownikowi stosowania inaczej dostępnych narzędzi.^[Na przykład otwarcie linku w nowej karcie przeglądarki.]
- Spójność i standardyzacja
	W ramach systemu używami jednolitej konwencji, możliwie zbliżonej do ogólnie przyjętej konwencji.
	- Sposób obsługi
	- Barwy, czcionki
	- Menu, przyciski, skróty
	- Feedback
- Zapobieganie błędom
	Uniemożliwianie akcji prowadzących do błędnego stanu.
- Oszczędzanie pamięci użytkownika
	Zapamiętywanie wcześniej wprowadzonych danych, działań; przechowywanie dostępnych akcji w łatwo dostępnym panelu.
- Elastyczność i wydajność
- Prostota dialogu
	Prezentacja *przede wszystkim* najczęściej używanych opcji.
- Diagnozowanie błędów
	Komunikaty błędów powinny być czytelne dla użytkownika.
- Pomoc i dokumentacja
	- "Dymki" (hover)
	- Manual, wiki, forum
	- Tutorial
	- Helpline
	- Szkolenia

# Przegląd poznawczy (cognitive walkthrough)
Użytkownik (specjalista prowadzący przegląd) przechodzi przez program w pewnym celu. Analizuje przegląd poprzez 4 pytania:
1. Czy użytkownik pracuje nad właściwym zadaniem?
2. Czy użytkownik wie, że działanie jest dostępne?
3. Czy użytkownik kojarzy cel z działaniem?
4. Czy użytkownik wie, że zbliża się do celu?
## Jogthrough
Uproszczone pytania:
1. Czy użytkownik wie, co ma zrobić?
2. Czy użytkownik pozna, że mu się udało?

# Badanie funkcjonalności (checklista)
Używana w późnej fazie na kompletnym projekcie. #todo 