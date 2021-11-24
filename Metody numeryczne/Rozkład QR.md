# Rozkład QR


$A \in \mathbb{R}^{M \times N}, M \geqslant N$ oraz $\operatorname{rank}(A)=N$

## Rozkład wąski
$$
A=\hat{Q} \hat{R}
$$
$\hat{Q} \in \mathbb{R}^{M \times N}$ [[Własności macierzy#Ortogonalność|ortogonalna]] 
$\hat{R} \in \mathbb{R}^{N \times N}$ górna trójkątna z niezerową przekątną

![[Rozkład QR (Wąski)_2021-11-20 20.22.49.excalidraw]]

Ten rozkład nazywamy **wąskim**, ponieważ macierz $\hat{Q}$ jest tak wąska jak macierz $A$

## Rozkład pełny
Czasem wolelibyśmy żeby macierz $\hat{Q}$ była kwadratowa, dlatego możemy dodać do niej $m-n$ wektorów które zachowają ortogonalność całej macierzy
$$
A=Q R
$$
$Q \in \mathbb{R}^{N \times N}$ [[Własności macierzy#Ortogonalność|ortogonalna]] 
$\hat{R} \in \mathbb{R}^{M \times N}$ górna "trójkątna" z niezerową przekątną
![[Rozkład QR_2021-11-20 20.44.55.excalidraw]]

## Różnice

Rozkład pełny nazywamy **pełnym** ponieważ macierz $Q$ jest kwadratowa.

Rozkład wąski jest bardziej ekonomiczny w utrzymywaniu w pamięci, natomiast rozkład pełny ma lepsze własności matematyczne




