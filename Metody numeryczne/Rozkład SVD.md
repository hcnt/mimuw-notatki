# Rozkład SVD

Niech $A \in \mathbb{R}^{M \times N}, M \geqslant N$. 

Istnieje rozkład
$$
A=U \Sigma V^{T}
$$
- $U \in \mathbb{R}^{M \times N}$ ortogonalna
- $V \in \mathbb{R}^{N \times N}$ ortogonalna
- $\Sigma \in \mathbb{R}^{N \times N}$ diagonalna, $\Sigma=\operatorname{diag}\left(\sigma_{1}, \ldots, \sigma_{N}\right)$ $\sigma_{1} \geqslant \cdots \geqslant \sigma_{N} \geqslant 0$


![[assets/Rozkład SVD_2021-11-22 23.47.36.excalidraw.md]]

Podobnie jak w rozkładzie [[Rozkład QR|QR]] możemy zdefiniować rozkład pełny

![[assets/Rozkład SVD_2021-11-22 23.50.38.excalidraw.md]]

Twierdzenie o istnieniu tego rozkładu mówi że przekształcenie $A$ w pewnej bazie ortogonalnej w przestrzeni $R^M$ ($U$) i w pewnej bazie ortogonlanej w przestrzeni $R^N$ ($V^T$) można to przekształcenie przedstawić jako macierz $\Sigma$ która reprezentuje przekształcenie które tylko skaluje przestrzeń po współrzędnych

## Własności
1. Wartości własne $A^{T} A$ są równe $\sigma_{1}^{2}, \ldots, \sigma_{N}^{2}$.
2. Jeśli $\sigma_{1} \geqslant \cdots \geqslant \sigma_{r}>\sigma_{r+1}=\ldots=\sigma_{N}=0$, to rząd $A$ jest równy r.
3. $A=\sum_{i=1}^{N} \sigma_{i} u_{i} v_{i}^{T}$, gdzie $u_{i}, v_{i}-$ kolumny $U, V$.
4. Tw. Eckarta-Younga: Macierz rzędu $\leqslant k \leqslant N$ najbliższa $A$ w normie $\|\cdot\|_{2}$ lub $\|\cdot\|_{F}$ to $A_{k}=\sum_{i=1}^{k} \sigma_{i} u_{i} v_{i}^{T}$.
#todo wyjaśnić troche o co chodzi w tych własnościach

## Zastosowania

- Wyznaczenie rzędu macierzy
- [[PCA]], używane w uczeniu maszynowym
- Rozwiązanie LZNK, gdy A jest pełnego rzędu (Taniej użyć rozkładu QR) #todo wyjaśnić w jaki sposób
- Rozwiązanie LZNK, gdy A nie jest pełnego rzędu
