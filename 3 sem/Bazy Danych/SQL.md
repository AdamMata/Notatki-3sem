---
aliases:
  - Structured Query Language
---
- **interaktywny**: wyniki są dostępne natychmiast w formacie wybranym przez [[Database Management System|DBMS]].
- **embedded** (*osadzony*): instrukcje można *zinline'ować* w inny język.


# Core SQL
Instrukcje obsługiwane standardowo przez każdy [[Database Management System|DBMS]].
>[!info] Treść całej notatki pokrywa tylko Core SQL
## [[Język zapytań#^9e9a7a|DDL]]
```sql
create table
create view
create index

alter table

drop table
drop view
drop index
```
## [[Język zapytań#^e3fc8c|DML]]
```sql
select
insert
update
delete
```
(`select` działa też jako DQL)
## [[Język zapytań#^62d9fb|DCL]]
```sql
grant
revoke
```

# 
---
# Nomenklatura

## Tabela

Odpowiednik [[Relacja|relacji]], ale ma **powtarzające się rzędy**.
## Typy atrybutów
```sql
int, integer, smallint
decimal, numeric, real (fixed point)
float, double precision (floating point)
char, character
varchar, text
date, datetime
logical
money
image
blob, clob
```
`blob`: *binary large object*.
## Opcje
```
not null
unique
[not] case-sensitive
default ...
primary key
references [...]
autoincrement
```

# 
---
`SELECT field AS alias`
## Operatory
```sql
** ^
* /
+ -

NOT AND OR
==

```
>[!warning] NULL =/= NULL, NULL IS NULL

## Funkcje agregujące
```sql
COUNT()
AVG()
SUM()
MIN()
MAX()
```

```sql
WHERE X = A or X = B
```
<=>
```sql
WHERE X IN (A, B)
```

# Złączenia (JOIN)