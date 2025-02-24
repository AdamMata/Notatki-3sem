>[!quote]
>Podzbiór iloczynu kartezjańskiego dziedzin prostych (niepodzielnych).
>Innymi słowy pewien zbiór krotek atrybutów.

# [[Związek]] a relacja
Relacja wymaga *dziedzin prostych*, związek zawiera [[Encja|encje]].

>[!important]
>Relacja jest zawsze w postaci *pierwszej normalnej*.

Relację można reprezentować tabelą. Ilość kolumn jest tożsama ze stopniem relacji.

# Własności relacji
- Nie ma duplikatów
- .
- .
# Schemat relacji
```

Książka(ISBN, tytuł, autor),
    _ISBN_ c {legalne numery ISBN}
    tytuł, autor c {łańcuch znaków}
```
```SQL
CREATE TABLE Books(
    ISBN varchar(24)
    Title varchar(128)
    Author varchar(64)
    PRIMARY KEY (ISBN)
)
```

[[Taksonomia baz danych#^aba565|Relacyjna]] baza danych to **zbiór relacji**.
# Integralność relacji
1. Entity integrity (atrybuty klucza nie są nullable)
2. Referential integrity (nie ma dangling kluczy obcych)