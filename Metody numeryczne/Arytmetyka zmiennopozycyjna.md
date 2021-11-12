# Arytmetyka zmiennopozycyjna


$$x = (-1)^s \cdot m * 2^e$$

$m$ - mantysa ($0 \leq m < 2$)
$e$ - cecha ($e \in \mathbb{Z}$)
$s$ - znak

W komputerze mamy ograniczoną liczbę bitów na zapis $m$ i $e$

## Liczby maszynowe znormalizowane 

zakładamy że pierwszy bit $m$ = 1 więc $1 \leq m < 2$
przechwywujemy liczbę jako

| s | e + e_max | m |


## Reprezentacja liczb rzeczywistych

IEEE 754 gwarantuje 4 tryby zaokrąglania
do najbliższej, w góre, w dół, w stronę zera

domyślnie jest do najbliższej $RN(x)$

Precyzja:

$$\frac{|x - RN(x)|}{|x|} \leq \frac{1}{2^p} = v$$
$v$ to precyzja arytmetyki

$fl(x) = x \cdot (1 + \epsilon)$
$|\epsilon| \leq v$ bo $fl(x) = x + \epsilon \cdot x \rightarrow \frac{fl(x) - x}{x} = \epsilon$

Poza skrajonściami mamy
$$ fl(a \square b) = (a \square b) (1 + \epsilon)$$

## Błędy obliczeń

Po dodaniu 2 liczb mamy precyzję 

$$ \frac{|a + b - fl(a+b)|}{|a+b|} \leq 2 \frac{|a| + |b|}{|a + b|}v $$

zatem jeżeli liczby są tego samego znaku to mamy dużą precyzję wynik mniejszy niż $2v$

ale gdy $a \approx -b$ to $\frac{|a| + |b|}{|a + b|}v \approx \frac{2|x|}{\text{b.mała liczba}} >> 1$  
Więc wtedy nie mamy praktycznie żadnej gwarancji precyzji, to zjawisko nazywamy "redukcja cyfr przy odejmowaniu"






