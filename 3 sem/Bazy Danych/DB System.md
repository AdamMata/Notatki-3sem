---
aliases:
  - System Bazy Danych
  - DBS
---
# Elementy systemu
- external storage
	który musi być *permanentny* oraz *niezmienny*^[reliable]
- [[Database Management System]]
- [[Język zapytań]]

# Diagram

```mermaid

flowchart

subgraph DB system
	DB[(Database)] <---> DBMS
end
user --query--> DBMS
DBMS --response--> user
```
Zobacz: [[3 sem/Bazy Danych/Użytkownik|User]], [[Database Management System|DBMS]]
# Poziomy modelu architektury
1. External (user)
> Wyeksponowane funkcje DBS.
3. Logical (model)
> Widać struktury danych z perspektywy modelu logicznego. Poziom dostępny dla admina.
3. Internal (physical) level
> Poziom implementacyjny.
