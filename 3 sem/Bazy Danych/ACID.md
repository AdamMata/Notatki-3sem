
# 
[[Transakcja|Transakcja]] jest ACID-owa gdy spełnia poniższe wymagania:
## Atomic
Transakcja zostanie wypełniona w całości.
## Consistent
Transakcja pozostawia bazę w poprawnym stanie.
## Isolated
Transakcję można wykonać niezależnie od innych.
## Durable
Pomyślnie zakończona transakcja wprowadza stałe zmiany do bazy.

Zachowanie reguł ACID jest obowiązkiem programisty, nie [[Database Management System|DBMS-a]]!

# Konsekwencje nie-ACIDowych transakcji
## Lost update
Dwa równoczesne zapytania modyfikują dane sprzed modyfikacji. Zapamiętane zostanie tylko to, które wykonało się później.
## Dirty read
1. A czyta dane
2. B modyfikuje dane
3. A dalej procesuje swoje odczytane dane jak gdyby były aktualne
albo
4. B modyfikuje dane
5. A czyta zmodyfikowane dane
6. B wycofuje zmiany ([[##Rollback]])
7. A procesuje dane sprzed Rollback-u

## Non-repeatable read
Dwa takie same odczyty w ramach jednej transakcji dają różne wyniki.

## Phantom rows

