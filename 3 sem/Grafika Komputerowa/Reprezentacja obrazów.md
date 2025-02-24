
# Rastrowa

^39afbd

Płaszczyzna (*raster*) podzielona na **piksele** z naniesonym [[Kolor|kolorem]].

>[!info]- Pixel = *pic*ture *el*ement

Używana przez drukarki, monitory, skanery, aparaty fotograficzne. ^c37b81
## Sposoby reprezentacji
- tablica 2-wymiarowa (*bitmapa*[^1])
- drzewa czwórkowe (quadtree)
- drzewa binarne

[^1]: Nazwa już nieaktualna odkąd większość obrazów nie jest binarnie czarno-biała.

## Formy danych obrazowych
- Obrazy kolorowe {int, int, int, (int)[^2]} 
- Obrazy szare (*wielopoziomowe*) {int}
- obrazy czarno-białe (*dwupoziomowe*) {bool}

[^2]: kanał alfa
# Wektorowa
Obraz złożony z figur płaskich (odcinków, krzywych).
Tworzony poprzez rysowanie kolejnych figur składowych.

Używana przez plotery, tablety graficzne.

Grafikę wektorową można emulować na [[#^c37b81|urządzeniach rastrowych]].