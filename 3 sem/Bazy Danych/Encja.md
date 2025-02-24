---
aliases:
  - Entity
---
Rzecz odróżnialna od innej rzeczy.
# Zbiór encji
Modelując klasyfikujemy encje w *zbiory encji* (zasada abstrakcji).
Encje w zbiorze odróżnia się wartościami *atrybutów*.
> W przypadku gdy dwie encje są zbieżne w atrybutach które modelujemy rozwiązujemy *tożsamością* (id).

>[!important] Atrybuty są prymitywne
>Atrybut musi być niepodzielny i samowystarczalny.

---

# Atrybut
powinien posiadać:
- Znaczącą (najlepiej) nazwę
- Dziedzinę (typ, enum/zakres wartości)
- Opcjonalność (opcjonalnie)
- Unikatowość (opcjonalnie)

# Klucz
- unikalny atrybut encji
- unikalny identyfikator (*primary key*)
- Klucz biznesowy (istniejący w rzeczywistości)
- Klucz sztuczny (*surogate/artificial*) istniejący wyłącznie w bazie danych
- Klucz złożony (z wielu atrybutów)

>[!warning] Encja musi mieć klucz!

Klucz musi być unikalny i minimalny (każdy atrybut składający się na klucz jest niezbędny).
# Redundancja
Niepożądana sytuacja w której *ta sama informacja* jest zapisywana równocześnie *w wielu encjach*. (Wartość jednego atrybutu warunkuje wartość innego). Tym **gorzej** jeśli redundantny atrybut jest częścią/jest powiązany z kluczem.
# Well-formed
- Żaden atrybut nie zależy od klucza
- Żaden atrybut nie zależy od innego atrybutu