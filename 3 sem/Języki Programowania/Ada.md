#język
Nazwany po [Adzie Lovelace](https://en.wikipedia.org/wiki/Ada_Lovelace)
Rozwiązuje [[Współbieżność#Problemy]]

---
Współbieżny (Concurrent)
strukturalny, kompilowny, imperatywny, statycznie typowany
Z uwagi na bezpieczeństwo stosowany w systemach krytycznych (militaria, awionika, kosmonautyka, bankowość) 
IDE: GNAT Studio (https://github.com/AdaCore/gnatstudio, instrukcja instalacji na eNauczaniu)

Każda tablica musi zostać zainicjowana
`STRING` jest tablicą znaków
`and then`, `or else` operatory logiczne warunkowe
Przypisanie: `X := cośtam`
nie ma znaczących indentacji: 
```Ada
loop
	cośtam
end loop
```
Procedury (nie zwracają) i funkcje (zwracają)
```Ada
function foo(X,Y:FLOAT; N:INTEGER) return FLOAT // is ...
begin
	...
	return ...;
end foo;
```
>[!error] rodzaje wejściowe wyjściowe
>`in` `out`

Zadania: procedury asynchroniczne
	Usterka zadania nie powoduje usterki programu (bez propagacja błędów)
```Ada
// deklaracja
task type Aabb is
	entry APrint;
	entry BPrint;
end Aabb;
```
```Ada
// definicja
task body Aabb is
begin
	...
???
```
>[!error] eNauczanie

delegacja do wątku: `accept ... do`

rendezvous (spotkanie): mechanizm bezpośredniej komunikacji między zadaniami
	żeby zadanie A nie czekało na zakończone zadanie B (deadlock?)
`select (delegacja1) or (delegacja2) end select`
`select (delegacja_ważna) or delay 5.0; (delegacja_nieważna) end select`
`5.0` w sekundach opóźnienia dla drugiej delegacji między wykonaniami.
`select ... then abort` wykonaj i zatrzymaj wywołanie

dozór:
```Ada
select
	when dice=6 => accept ... do
		...
	// end when ?
end select
```