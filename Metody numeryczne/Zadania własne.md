# Zadania własne

Problem
Znaleźć $v \in \mathbb{C}^{N}$ oraz $\lambda \in \mathbb{C}$ t. że
$$
A v=\lambda v, \quad\|v\|=1
$$
W praktyce spotyka się zadania:
- znaleźć największą/najmniejszą (co do modułu) wartość własną (i ew. odp. wektor własny)
- znaleźć wartość własną bliską zadanej liczbie (i ew. odp. wektor własny)
- znaleźć wszystkie wartości własne (i ew. odp. wektory własne)

## Wyznaczenie największego wektora własnego

Zakładamy ze istnieje tylko jeden taki wektor w macierzy $A$

Algorytm:

```
while not stop:
	x = dowolny wektor
	tmp = Ax
	tmp /= norm(tmp) # Zmiana na wektor jednostkowy
	x = tmp

```


Idea

![[assets/Zadania własne_2021-11-23 23.02.11.excalidraw.md]]
Gdy $\left|\lambda_{2}\right| /\left|\lambda_{1}\right| \approx 1$ zbieżność może być wolna


## Iloraz Rayleigh

Problem
Mając przybliżony wektor własny $v$, jak dobrać dla niego $\lambda ?$
Zminimalizować resztę,
$$
\|A v-\lambda v\|_{2} \rightarrow \min
$$
To jest LZNK, a rozwiązaniem jest
$$
\lambda=\frac{x^{H} A x}{x^{H} x} \quad \text { (iloraz Rayleigh) }
$$
Dowód: #todo

## Metoda odwrotna potęgowa i metoda RQI wyznaczania specyficznych wektorów własnych
#todo

## Kryterium stopu
#todo

## Metoda QR oraz metoda "dziel i rządź" rozwiązywania pełnego zadania własnego
#todo
