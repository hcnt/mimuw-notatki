# ASD Wykład 1 - Algorytmy i Sortowanie

## Notacja asymptotyczna

### $O(f)$

$$O(f) = {g: \exists_{n_0} \exists_c \forall_{n \geq n_0}: 0 \leq g(n) \leq cf(n) }$$

Czyli: zbiór funkcji ograniczany z góry przez pewne $cf$

### $\Omega(f)$

$$O(f) = {g: \exists_{n_0} \exists_c \forall_{n \geq n_0}: 0 \leq cf(n) \leq g(n) }$$

Czyli: zbiór funkcji ograniczany od dołu przez $cf$

### $\Theta(f)$
$$f \in \Theta(g) \iff f \in O(g) \land f \in \Omega(g) $$
Czyli: zbiór funkcji rzędu  $g$
## Inwersja w ciągu

Inwersja to nieuporządkowana para elementów ciagu

$Inv(a)$ - ilość inwersji w tablicy a
$$0 \leq Inv(a) \leq n(n-1)/2$$


## Algorytm w miejscu

Taki algorytm którego złożoność pamięciowa wynosi $O(1)$

## Stabliny algorytm sortowania

Algorytm sortowania który zachowuje względną kolejność elementów o równej wartości

## Złożoność problemu sortowania przez porównania

Tworzymy model drzew decyzyjnych 

Przykładowe drzewo dla 3 elementów
![[Pasted image 20211114204329.png]]

w sortowaniu mamy $n!$ możliwych wyników (ilość permutacji)

pesymistyczna wysokość drzewa decyzyjnego jest rzędu $\log n! \approx n \log n$ 

## Programowanie dynamiczne

Chodzi o to żeby podzielić problem na podproblemy i tablicować wyniki dla tych podproblemów, jeżeli będą się powtarzać to już mamy policzone

Zwykle wykładnicze algorytmy rekurencyjne da się dzięki temu zrobić w sensownej złożoności wielomianowej