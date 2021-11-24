# ASD Wykład 4 - Statystyki pozycyjne
Rozważamy problem znalezienia $k$ najmniejszego elementu w tablicy

## Selekcja Hoare'a
Możemy wykorzystać pomysł z algorytmu [[ASD Wykład 2 i 3 - Algorytmy sortowania#Quick sort|quick sort]], gdy dzielimy zbiór na dwie części względem `p = pivot(a)`  to dokładnie wiemy jaki jest rozmiar tych części, więc znając $k$ możemy zawsze ponownie dzielić tylko jeden z tych zbiorów, aż nie znajdziemy elementu o indeksie $k$

Złożoność pesymistyczna $O(n^2)$: 
Złożoność oczekiwana $O(n)$: 