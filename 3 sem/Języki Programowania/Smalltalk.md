**Język czysto obiektowy**.
Istnieją tylko obiekty i komunikaty między nimi.

Język *refleksyjny*: środowisko jest samo-opisane w samym języku.

Istnieje ciągła historia obiektu
**Komunikat**: Obiekty nie współdzielą danych, tylko je sobie komunikują
**Interfejs**: Zbiór komunikatów obsługiwanych przez obiekt
**Zmienne instancji**: prywatna pamięć obiektu
**Metody prymitywne**: wykonywane bezpośrednio przez maszynę wirtualną języka.
>[!quote] Na począku była metaklasa


Cincom Smalltalk
# Komunikaty
>[!warning] Wykonywane od lewej do prawej
>`a+b*2` =/= `(a+(b*2))`
>

# Blok akcji
Coś jak closure/lambda. Używany w pętlach i wyrażeniach warunkowych, przekazywany jako obiekt.
# Zmienne
- **współdzielone**: (zmienne klasy) coś jak `static` w Javie: wspólna w ramach klasy.
- **obiektu** (pola)
#
---
# Zastosowania
- gry
- symulacje
- programy graficzne
- aplikacje webowe (biblioteka Seaside)
# Środowiska
## IDE
- ==Cincom VisualWorks (darmowy dla studentów, dostępny w laboratorium)==
	Instrukcja na eNauczaniu. Po uruchomieniu:
	- `+`
	- Browse > System > Package > New Package
	- Package > File into > `main.st`
	- (Okno projektu) > Tools > Workspace
	- Uruchomienie: ⚡
- Squeak (trudny w użyciu)
- GNU Smalltalk z VisualGST
- ...
## Interpretery online
- jdoodle
- tutorialspoint

```Smalltalk
Smalltalk defineClass: #Class
	superclass: #{Core.Object}
	indexedType: #none

"2-parameter constructor"
initialize: arg name: name 
	nazwa := name
	field := arg
	vector := 0@0

getter
	^field

setter: arg
	field := arg

"communicate"
+ operand
	^(Class new) operand.field + field
```