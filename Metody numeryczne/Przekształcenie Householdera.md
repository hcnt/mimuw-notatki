# Przekształcenie Householdera

$$
H=1-2 \frac{v v^{T}}{v^{T} v}
$$

#### Własności
- [[Własności macierzy#Symetria|Symetria]]
- [[Własności macierzy#Ortogonalność|Ortogonalność]]
- [[Własności macierzy#Izometria|Izometria]]
- Liniowa pamięć na reprezentację (*Wystarczy pamiętać wektor $v$*)


#### Wyznaczanie $y = Hx$
$$
H x=\left(I-2 \frac{v v^{T}}{v^{T} v}\right) x=x-\frac{2}{\|v\|_{2}^{2}}\left(v^{T} x\right) \cdot v
$$
Koszt wyznaczenia jest liniowy


#### Wyznaczanie $Hb = y = \alpha \cdot e_1$

Komu to potrzebne? nie wiem #todo

Dla zadanego wektora $b$ chcemy znaleźć takie $y$ które ma tylko jedną niezerową współrzedną

Przekształcenie jest [[#Izometria|izometryczne]] więc $\alpha=\pm\|b\|_2$

$$
H b=b-2 \frac{v v^{T}}{v^{T} v} b=b-2 \frac{v^{T} b}{v^{T} v} v
$$

Dalej jakieś dziwne przekształcenia #todo 

Ostatecznie wychodzi że koszt wyliczenia $y$ jest liniowy