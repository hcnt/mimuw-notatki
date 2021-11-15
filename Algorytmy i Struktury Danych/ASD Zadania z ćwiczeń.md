# ASD Zadania z ćwiczeń
Zadanie $1.8$ - sortowanie przez wstawianie
Dokonaj analizy pesymistycznej złożoności obliczeniowej tego algorytmu dla następujących przypadków:

a) $|a[i]-a[j]|<2020$, dla każdej pary $1 \leq i, j \leq n$ takiej, że $\left|i - j\right|<2020$
Odpowiedź: $O\left(n^{2}\right)$ ponieważ ciąg odwrotnie uporządkowany spełnia warunki zadania, a sortuje się w $O(n^2)$

b) $|i-a[i]|<2020$, dla każdego $1 \leq i \leq n$
Odpowiedź: $O(n)$ ponieważ liczba inwersji w $a$ jest $\leq 4040 n$ (dla $j-i \geq 4040$ możemy udowodnić, że $a[i] \leq a[j]$. (różnica pomiędzy $i$ a $a[i]$ jest maksymalnie 2020, więc pomiędzy dwoma elementami maksymalna przerwa może być 4040)

c) dla co najwyżej 2020 elementów zachodzi $i \neq a[i], 1 \leq i \leq n$
Odpowiedź: $O(n)$ ponieważ liczba inwersji w $a$ jest $\leq 2020 n$ (każda inwersja zawiera jakiś element $i \neq a[i]$ ).