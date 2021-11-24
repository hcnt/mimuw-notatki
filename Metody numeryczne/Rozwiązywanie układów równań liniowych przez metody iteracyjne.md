# Rozwiązywanie układów równań liniowych przez metody iteracyjne

## Metody stacjonarne oparte na rozszczepieniu

Rozszczepiamy macierz $A$: 
$$
A = M-Z
$$
Gdzie $M$ nieosobliwa

$Ax = b$
$(M-Z)x = b$
$Mx = Zx + b$
$x = M^{-1}(Zx + b)$
$x = M^{-1}((M-A)x + b)$
$x = x + M^{-1}(b - Ax)$

Rozwiązaine $x$ to punkt stały funkcji 
$$\Phi(x) = M^{-1}(Zx + b)$$
$$\Phi(x) = x +M^{-1}(b - Ax)$$

na podstawie [[#Twierdzenie o zbieżności metody rozszczepiania]]

- Jeśli $\rho\left(M^{-1} Z\right)<1$, to metoda iteracyjna
$$
M x_{k+1}=Z x_{k}+b
$$
jest zbieżna do $x^{*} z$ każdego $x_{0}$.

na podstawie [[#Twierdzenie o liniowej zbieżności iteracji liniowej]]

- Jeśli dodatkowo $\gamma:=\left\|M^{-1} Z\right\|<1$, to dodatkowo $\left\|x_{k+1}-x^{*}\right\| \leqslant \gamma \cdot\left\|x_{k}-x^{*}\right\|$

## Przykłady metod opartych na rozszczepieniu

$A = L + D + U$
D - diagonalna
L - trójkątna dolna z zerową diagonalą
U - trójkątna górna z zerowoą diagonalą
$$x_{k+1} = x_k +M^{-1}(b - Ax)$$

### Metoda Jacobiego
$$M = D$$

Kiedy działa?

>Jeśli A jest diagonalnie dominująca,
>$$
\left|a_{i i}\right|>\sum_{j \neq i}\left|a_{i j}\right| \quad \forall i=1, \ldots, N
>$$
>to $m$. Jacobiego jest zbieżna do $x^{*}$ dla każdego $x_{0}$.


### Metoda Gaussa-Seidela
$$M = D+L$$

### Metoda SOR (Successive OverRelaxation)
$$M = \frac{1}{\omega}D+L$$

## Zbieżność metod iteracyjnych

### Twierdzenie o zbieżności metody rozszczepiania
>Ciąg
>$$
x_{k+1}=B x_{k}+c
>$$
>jest zbieżny do $x^{*}$ dla każdego $x_{0} \Longleftrightarrow \rho(B)<1$, gdzie
>$$
\rho(B)=\max \{|\lambda|: \lambda \text { jest wartością własną } B\}
>$$

$\rho(B)$ to inaczej **promień spektralny** macierzy $B$.


### Twierdzenie o liniowej zbieżności iteracji liniowej
>Jeśli $\|B\|<1$, to ciąg $x_{k+1}=B x_{k}+c$ jest zbieżny do $x^{*}$ dla każdego $x_{0}$ oraz
>$$
\left\|x_{k+1}-x^{*}\right\| \leqslant\|B\| \cdot\left\|x_{k}-x^{*}\right\|
>$$

Dowód #todo

## Metody projekcji
nie czaje #todo

## Metody Kryłowa
nie czaje jeszcze bardziej #todo

## Ściskanie macierzy

Czasem możemy poprawić zbieżność metod iteracyjnych jeżeli tylko przemnożymy ją najpierw przez pewną macierz

$$MA = Mb$$

Chcemy tak dobrać $M$ żeby $MA$ miała lepsze własności
$M$ musi być łatwe w konstrukcji i tanio pomnożyć wektor $b$

Należy wybrać $M \approx A^{-1}$ ale tanie w obliczeniu
- jeden (kilka?) kroków prostej metody iteracyjnej
- niepełny rozkład LU, itp.
- najlepiej: dobrać specjalnie do konkretnego zadania!