# Liniowe Zadanie Najmniejszych Kwadratów

## Problem

Niech $A \in \mathbb{R}^{M \times N}, M \geqslant N$ oraz $\operatorname{rank}(A)=N$ i niech $b \in \mathbb{R}^{M}$.
Znaleźć $x \in \mathbb{R}^{N}$ taki, że
$$
\|b-A x\|_{2} \rightarrow \min
$$

## Rozwiązywanie przez rozkład [[Rozkład QR|QR]]

$$
\|b-A x\|_{2}^{2} =\|b-Q Rx\|_{2}^{2}= \|QQ^Tb-Q Rx\|_{2}^{2}= \left\|Q\left(Q^{T} b-R x\right)\right\|_{2}^{2}
$$ 
$Q$ jest [[Własności macierzy#Ortogonalność|ortogonalna]] więc nie zmieni wartości normy, czyli możemy pominąć

$$
=\left\|Q^{T} b-R x\right\|_{2}^{2}=\left\|\left[\begin{array}{c}
\hat{Q}^{T}\\ 
\tilde{Q}^{T}
\end{array}\right] b-\left[\begin{array}{c}
\hat{R} \\
0
\end{array}\right] x\right\|_{2}^{2} 
$$


$$
=\|\left[\begin{array}{c}
\hat{Q}^{T} b-\hat{R} x \\
\tilde{Q}^{T} b
\end{array}\right]\|_{2}^{2}=\left\|\hat{Q}^{T} b-\hat{R} x\right\|_{2}^{2}+\|\tilde{Q}^{T} b \|_{2}^{2}
$$

$\|\tilde{Q}^{T} b \|_{2}^{2}$ nie zależy od $x$ więc mozemy pominąć podczas szukania minimum


Musimy zatem zminimalizować $\left\|\hat{Q}^{T} b-\hat{R} x\right\|_{2}^{2}$ a będzie to najmniejsze gdy  $\hat{Q}^{T} b =\hat{R} x$
musimy więc wykonać następujace operacje

$$
\begin{aligned}
&\text { Oblicz } \hat{b}:=\hat{Q}^{T} b(\text { koszt: } \mathcal{O}(M N)) \\
&\text { Rozwiąż } \hat{R}x=\hat{b}\left(\text { koszt: } \mathcal{O}\left(N^{2}\right)\right) \\
\end{aligned}
$$

## Rozwiązanie przez układ normalny


Z rozwiązywania przez rozkład QR wiemy że 
$$
x=\hat{R}^{-1} \hat{Q}^{T} b
$$

Mnożąc przez (nieosobliwą) $\hat{R}^{T} \hat{R}$ mamy
$$
\hat{R}^{T} \hat{R} x =\hat{R}^{T} \hat{Q}^{T}b
$$
A z definicji [[Rozkład QR|rozkładu QR]] wiemy że 
$$
\hat{R}^{T} \hat{Q}^{T}b = A^Tb
$$

Z drugiej strony
$$\hat{R}^{T} \hat{R}x=\hat{R}^{T} \hat{Q}^{T} \hat{Q} \hat{R}x=A^{T} Ax$$ 

więc ostatecznie $x$ jest rozwiazaniem **układu równań normalnych**

$$A^TAx=A^Tb$$

![[assets/Liniowe Zadanie Najmniejszych Kwadratów_2021-11-22 23.33.45.excalidraw.md]]

Własności $A^T A$:
- Mała ($N \times N$)
- Symetryczna
- Dodatnio określona (bo A jest pełnego rzędu) #todo nie rozumiem :(

Więc musimy wykonać następujące operacje aby rozwiązać

Oblicz $B=A^{T} A$ (koszt $M N^{2}$)
Wyznacz [[Rozkład Cholesky'ego]] $B=L L^{T}$ (koszt  ($\mathcal{O}\left(N^{3}\right)$)
Rozwiąż układ $L L^{T} x=A^{T} b$ (koszt $\mathcal{O}(M N)$)

Jest około dwa razy taniej niż przez rozkład QR ale może mieć gorsze własności numeryczne #todo czemu?


## Nieregularne LZNK

$A \in \mathbb{R}^{M \times N}, M \geqslant N$, ale $\operatorname{rank}(A)<N$.
Szukamy $x \in \mathbb{R}^{N}$ t.że
$$
\|b-A x\|_{2} \rightarrow \min
$$
Skoro $\operatorname{ker}(A) \neq 0$, to rozwiązanie nieregularnego LZNK nie jest jednoznaczne: 

$x$ minimalizuje $\|b-A x\|_{2} \Longrightarrow x+z$, gdzie $z \in \operatorname{ker}(A)$

Rozwiązuje się to za pomocą rozkładu [[Rozkład SVD|SVD]] #todo jak?