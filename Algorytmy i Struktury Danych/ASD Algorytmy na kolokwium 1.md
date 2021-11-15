# ASD Algorytmy na kolokwium 1

## Sortowanie tablicy z ograniczonymi wartościami w miejscu i stabilnie
Dane:
Zbiór $A$ dozwolonych wartości, z zadanym porządkiem liniowym
tablica $t$ rozmiaru $n$ w której znajdują się jedynie wartości ze zbioru $A$

Problem:
Posortować tablicę $t$ w miejscu i stabilnie

Rozwiązanie:
Bierzemy najmniejszą wartość z tablicy - $x$

Używamy podejścia [[Dziel i zwyciężaj]]

Dzielimy tablicę na pół i dla obu połówek sprawiamy że wszystkie $x$ są na początku danej połówki

$[x_1,x_2,x_3,x_4,a,b,c,d|x_5,x_6,x_7,c,b,d,a,e]$

Teraz bierzemy ciąg $x$ z prawej strony i stawiamy go po ciagu $x$ z lewej

$[x_1,x_2,x_3,x_4,x_5,x_6,x_7,a|b,c,d,c,b,d,a,e]$

Dla każdego elementu z góry wiemy gdzie ma stać, więc dla każdego elementu zrobimy tylko jedną zamianę, wkładając go na właściwe dla niego miejsce, zatem jest to operacja liniowa i zachowująca stabilność

Po zakończeniu wszystkie $x$ znajdują się po lewej stronie tablicy zatem są już postortowane

Żeby osiągnąć oczekiwany stan w obu połówkach, możemy użyć tego algorytmu rekurencyjnie

W tej rekurencji w poszczególnych wywołaniach nie używamy żadnych informacji z wywołania wyżej, zatem możemy wywołania robić w pętli zaczynając od bloków wielkości 2, następnie mergując je w blokach wielkości 4 i tak dalej, obrotów pętli będzie $O(\log n)$ (ponieważ przechodzimy po potęgach dwójki aż nie będziemy mieli bloku  $\geq n$) i algorytm wykonuje się w miejscu

Gdy już wszystkie $x$ znajdują się po lewej stronie tablicy, uruchamiamy algorytm na części tablicy w której nie znajduję się $x$ przestawiając na lewą stronę najmniejszy alement zbioru $A$ który jest większy od $x$

W taki sposób posortujemy całą tablicę

Ostateczna złożoność to $O(|A|n\log n)$
