# Rozwiązywanie układów równań liniowych przez rozkład QR

Jeśli $A$ - kwadratowa nieosobliwa,
$$
A=Q R
$$

![[Text Elements]]

Jako że macierz jest kwadratowa to nie ma podziału na rozkład [[Rozkład QR#Rozkład wąski|wąski]] i [[Rozkład QR#Rozkład pełny|pełny]]

$Q$ - [[Własności macierzy#Ortogonalność|ortogonalna]]
$R$ - górna trójkątna

Układ równań:
$$
A x=b \quad \Longrightarrow \quad Q \underbrace{R x}_{=: y}=b
$$
skąd algorytm:
1. $y=Q^{T} b \quad\left(\right.$ koszt: $\left.\mathcal{O}\left(N^{2}\right)\right)$
2. Rozwiąż układ z macierzą trójkątną $R x=y . \quad\left(\right.$ koszt: $\left.\mathcal{O}\left(N^{2}\right)\right)$

Ale rozkład QR wymaga ok. 2 razy więcej flopów niż rozkład [[Rozkład LU|LU]].

Ale ta metoda ma dużo lepsze własności numeryczne (czemu? #todo)