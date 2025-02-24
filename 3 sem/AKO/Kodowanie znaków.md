# ASCII
**American Standard Code for Information Interchange**
`0xxx xxxx`
## ANSI Codepage
Kod ASCII rozszerzony o dodatkowy zbiór znaków nazywany *codepage*m. Przykładowo charset używany w konsoli Windows (Latin 2) jest ASCIIm rozszerzonym o polskie znaki. 
# Unicode
`U+ab12` to przykładowy *punkt kodowy* Unikodu. Wszystkie zajęte punkty kodowe (dziś ponad 1 mln) stanowią *przestrzeń kodową*.
> ASCII `61` = Unicode `U+0061

>[!warning] Unicode a UTF
>Unicode **nie jest** systemem kodowania znaków! Jest jedynie standardem *punktów kodowych* które są odtwarzane z systemów kodowania ([[#UTF]])

## BMP
**Basic Multilingual Plane** - przestrzeń kodowa Unikodu.
Nie jest wypełniona w 100% - przestrzeń jest przeznaczona na skrypty narodowe, po nich puste przestrzenie na rozszerzanie skryptów.
Od `D800` do `DFFF` są pary surogackie - zapobiegają niejednoznaczności przy kodowaniu [[Kodowanie znaków#UTF-16]].
# UTF
**Unicode Transformation Format**
Przestrzeń kodową można zmapować na określoną ilość bitów. Używa się dwóch takich map: **UTF-8** i **UTF-16**, oraz rzadziej **UTF-32**. Dodatkowo za pomocą [[Kodowanie znaków#BOM|Byte Order Mark]] definiuje się [[Endian|Endianowość]] UTF.
## UTF-8
Bardziej wydajna opcja niż UTF-16.
- Znaki ze zbioru ASCII (punkty kodowe 0-7F) koduj jak [[Kodowanie znaków#ASCII]] (na jednym bajcie) (7bit na kod)
> `0xxxxxxx`
- Kody między 80 a 7FF koduj na 2 bajtach: (11bit na kod)
> `110xxxxx 10xxxxxx`
- Kody 3-bajtowe: (16bit na kod)
>`1110xxxx 10xxxxxx 10xxxxxx`
- Kody 4-bajtowe: (21bit na kod)
> `11110xxx 10xxxxx 10xxxxxx 10xxxxxx`

>[!tip] Wykorzystanie informacji
> Znajomość kodów pozwala odzyskiwać błędy przy odkodowywaniu i kontynuować odczytywanie błędnego strumienia.

## UTF-16
Każdy znak używa albo 16 albo 32 bitów. Wszystkie znaki z [[Kodowanie znaków#BMP]] są na 16.
Znaki spoza BMP:
`110110xx xxxxxxxx 110111xx xxxxxxxx`
>[!warning] Bias (przesunięcie)
>Kodując punkt kodowy w UTF-16 zapisuje się liczbę *o `1 0000 (h)` mniejszą* niż właściwa liczba punktu kodowego. Pozwala to zaoszczędzić jeden bit na znak. Rozkodowywując należy zaciągnąć znak przesunięty z powrotem o tę wartość.
## UTF-32
Zakodowanie pełnego punktu kodowego na 32 bitach.

# BOM
**Byte order marker**. Używany na początku pliku definiuje wykorzystywaną [[Endian|Endianowość]] kodowania. Użyteczne przy kodowaniu w UTF-16 i UTF-32.

>[!Tip] BOM jest zakodowanym punktem kodowym `FEFF`

| Kodowanie                           | BOM           |
| ----------------------------------- | ------------- |
| UTF-8                               | `EF BB BF`    |
| UTF-16 [[Endian#Little endian\|LE]] | `FF FE`       |
| UTF-16 [[Endian#Big endian\|BE]]    | `FE FF`       |
| UTF-32                              | `00 00 FE FF` |
