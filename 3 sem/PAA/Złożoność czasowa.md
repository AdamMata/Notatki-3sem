[[Oszacowania asymptotyczne]]

>[!tip] Mnożenie czasów
>$$
>\begin{align}
>\\ T(k) &= T(k-1) \cdot T(k-1) 
>\\ \log (T(k)) &= \log (T(k-1) \cdot T(k-1))
>\\ &= 2 \log T(k-1)
>\\ T(k) &= 2^{2 \log T(k-1)}
>\\ &= 4 T(k-1)
>\end{align}
>$$

^73e47c

