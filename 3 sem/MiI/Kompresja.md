# Współczynnik kompresji
3:1, 100:1 etc.
# Problemy
- symetria czasowa
> czas kompresji vs. czas dekompresji: istotne przy przesyłaniu danych w czasie rzeczywistym, np. wideorozmowy

- czas dekompresji
> istotny przy np. streamingu, publikowaniu masowym

- stratność
- kompresja sprzętowa i programowa
- skalowalność
---
# Stratna
Wykorzystuje właściwości kompresowanego medium
- sygnał
- użyty przetwornik
- urządzenie wyjściowe
- percepcja człowieka
Pozwalaja na kompresję nawet jak 5-500 : 1.
# 
---

# Wideo
Celuje w ok. 15fps, lepiej toleruje niższą rozdzielczość ze względu na ruch.
### Metody **intra**

^88f302

Wykorzystują metody kompresji [[#Obraz|obrazu]] w ramach jednej klatki - najczęściej [[#JPEG]].
### Metody **inter**
Wykorzystują podobieństwo następujących klatek.
- Predykcja
	Założenie kontynuacji zmian
- Estymacja ruchu (*Motion Estimation*)
	Znalezienie obszaru największego zainteresowania i poświęcenie mu większej dokładności
- Wektor ruchu (*Movement Vector*)
- Kompensacja ruchu (*Motion Compensation*)
	Obiekty poruszają się w **blokach**.
	Problemy:
		- Rozmiar bloku wpływa na możliwość kodowania zmian
		- Standard: bloki 4x4
		- Nie zawsze da się znaleźć blok: zastosuj [[#^88f302|kompresję intra]].
### Ramki
Makrobloki 16x16, 4 dla luminancji, po 1 na kanał chrominancji [[Modele kolorów#YC_bC_r]].
### Klasyfikacja ramek
- I - intra - klatki kluczowe, najmniej skompresowane
- P - predicted
- B - bidirectional (predicted z obu stron) - najlepiej kompresowane (błędy nie propagują się)
- D - direct
### Zniekształcenia
- Rozmycie
- Schodki
- Obwódki krawędzi
- Posteryzacja[^1]
### Zapobieganie zniekształceniom
- Większy bitrate (mniejszy [[#Współczynnik kompresji]])
- Więcej keyframe'ów
---
# Obraz
Więcej danych dla środka obrazu/miejsca gdzie jest największy ruch, więcej danych na intensywność koloru niż na barwę.
### Redukcja dokładności kwantyzacji

^ca963d

**Least significant bit truncation** - usuwamy najmniej znaczące bity
### Redukcja rozdzielczości
**Pruning**
### Paleta barw
Lista dostępnych kolorów, zapisanie klucza z palety
### Redukcja palety barw
### Redukcja chrominancji
**Color subsampling**, np. próbkowanie [[Kolor#YC_bC_r]].
### Redukcja w dziedzinie widma
Np. [[Kompresja#JPEG]].
Usuwa skrajne wartości. Samo kodowanie jest bezstratne.

---
# Audio
Maskuje słabsze dźwięki, łączy bliskie. Dla **mowy** usuwanie ciszy, zapis mono dla niskich częstotliwości, zastosowanie skali logarytmicznej.
### Kompresja falkowa
### Techniki różnicowe
DPCM (zapisz różnicę)
ADPCM *adaptive dpcm* (funkcją 2/3 potęgi przewiduj następny punkt, zapisz różnicę)
często stosowane w kompresji audio.
### Modele psychoakustyczne
Oparte o rozdzielczość ludzkiego ucha.
### Ton maskujący/ maskowanie widmowe
#### W dziedzinie częstotliwości
 Wycinamy częstotliwości które zostaną zagłuszone przez pobliskie głośniejsze. Zakres obejmowany przez kolejny ton maskujący rośnie wykładniczo.
 
 #### W dziedzinie czasu
 Korzystamy z bezwładności słuchu.
#
---
# Bezstratna
Nie traci informacji.
## Przykładowe metody
- Run Length Encoding
> dwie 1-ki, pięć 9-ek, etc.
> nieskuteczna dla danych z szumem
- metody słownikowe
> LZ77, 78, LZW
- kodowania entropijne
> Huffman, arytmetyczne
- metody statystyczne (m.in. Huffman)
> statyczne (wyprowadzona tabela)
> dynamiczne (wyprowadzane automatycznie)
> adaptacyjne (modyfikacja tabeli statycznej)
> wada: słownik też trzeba przechować. Zmniejszona skuteczność dla małych plików.

Skuteczność kompresji bezstratnej:

|                     | Osiągnięta      | Potrzebna |
| ------------------- | --------------- | --------- |
| [[Kompresja#Obraz]] | ±2:1,  max. 3:1 | 5-50:1    |
| [[Kompresja#Audio]] | ±10:1           | 5-20:1    |
| [[#Wideo]]          |                 | 5-300:1   |
^[[[MiI 03 Compression.pdf#page=6]]]
Względnie niski poziom kompresji, ok. 3:1
#
---
# Wybrane formaty kompresji
## JPEG
**Joint photographic expert group**
Algorytm symetryczny, RGB(4:4:4), YUV(4:4:4)/ (4:2:2)/ (4:1:1), CMYK.
Stosuje *Discrete Cosine Transform* DCT dla bloków 8x8 px.
## MPEG-1
**Moving Picture Experts Group**
Płyty CD wymagają min. 2h na #todo MB
Dwa tryby: CBR (*Constant BitRate*), VBR (*Variable BitRate*)
## MP3
==(nie będzie na egzaminie)==
**MPEG-1/2 Audio Layer 3**
1. Podział na 25-ms ramki
2. DCT ramki
3. Podział na 32 pasma częstotliwości
4. Maskowanie równoległe szumów i słabych sygnałów
5. Kodowanie bitów dla pasm
6. Ustalenie liczby bitów na ramkę
7. Odrzucenie informacji
8. Kompresja stratna
9. Kompresja strumienia Huffmanem
10. Dodanie nagłówków i scalanie

>[!tip] Joint Video Team
MPEG + VCEG (Video Coding Experts Group) + ITU-T.