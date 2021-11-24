# Interpolacja Lagrange'a
Problem:

Dla zadanych (parami różnych) węzłów interpolacji $x_{0}, \ldots, x_{N}$ i wartości $f\left(x_{0}\right), \ldots, f\left(x_{N}\right)$ znaleźć wielomian $p \in P_{N}$ taki, że
$$
p\left(x_{i}\right)=f\left(x_{i}\right), \quad i=0, \ldots, N
$$

Czyli, wiemy o danej funkcji tylko jakie ma wartości w kilku punktach, i chcemy te punkty [[Interpolacja|interpolować]] wielomianem

Twierdzenie
>Zadanie interpolacji Lagrange'a ma jednoznaczne rozwiązanie.

Dowód: 
$$
P_{N}=\operatorname{lin}\left\{\varphi_{0}, \varphi_{1}, \ldots, \varphi_{n}\right\}
$$
Z warunków interpolacji,
$$
p\left(x_{i}\right)=\sum_{j=0}^{N} c_{j} \varphi_{j}\left(x_{i}\right)=f\left(x_{i}\right), \quad 0 \leqslant i \leqslant N
$$
Jest to układ $N+1$ równań liniowych z $N+1$ niewiadomymi $c_{j}$. 

Ma on jednoznaczne rozwiązanie wtw wektor zerowy jest jedynym rozwiązaniem $Ax = 0$ (Twierdzenie z Algebry liniowej #todo notatka o tym)

Ale jedyny wielomian stopnia $\leqslant N$, który zeruje się w $N+1$ punktach, musi być zerowy.

## Obliczanie

W bazie naturalnej jest to po prostu koszt obliczenia układu równań

W bazie newtona możemy użyć lepszego algorytmu

### Różnice dzielone

nie rozumiem #todo
wiem tylko że koszt $O(N^2)$




### Błąd interpolacji

Niech $p$ będzie WIL dla of w punktach $x_{0}, \ldots, x_{N}$.
- Dla dowolnego $\bar{x} \in \mathbb{R}$
$$
f(\bar{x})-p(\bar{x})=f\left(x_{0}, x_{1}, \ldots, x_{N}, \bar{x}\right) \cdot \phi_{N+1}(\bar{x})
$$
- Ponadto, jeśli $f \in C^{(N+1)}[a, b]$, gdzie $[a, b]$ zawiera $x_{0}, \ldots, x_{N}, \bar{x}$, to istnieje $\xi=\xi(\bar{x}) \in(a, b)$ takie że
$$
f(\bar{x})-p(\bar{x})=\frac{f^{(N+1)}(\xi)}{(N+1) !} \cdot \phi_{N+1}(\bar{x})
$$
$$
\phi_{N+1}(x)=\left(x-x_{0}\right) \cdots\left(x-x_{N}\right)
$$
Trochę podobne do [[Szereg Taylora]]