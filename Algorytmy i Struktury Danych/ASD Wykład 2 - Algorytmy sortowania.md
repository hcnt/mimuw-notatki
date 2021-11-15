# ASD Wykład 2 - Algorytmy sortowania

## Insertion sort

Dla każdego elementu zamieniamy go po kolei z elementami większymi od niego po lewej stronie

- liczba porównań $n-1 + Inv(a)$ (*pesymistyczne $O(n^2)$*)
- liczba przesunięć $Inv(a)$ (*pesymistyczne $O(n^2)$*)
- [[ASD Wykład 1 - Algorytmy i Sortowanie#Algorytm w miejscu|w miejscu]]
- [[ASD Wykład 1 - Algorytmy i Sortowanie#Stabliny algorytm sortowania|stabilny]]
### Usprawnienie - metoda Shella
#### k-posortowanie
tablica jest k-posortowana jeżeli dla ustalonego k: $a[i] \leq a[i+k]$
dla $k=1$ tablica jest posortowana
dla $k \geq n$ tablica może być w dowolnym stanie

#### h-sortowanie
sortowanie w którym sortujemy $h$ podciągów tablicy, gdzie odległości pomiędzy elementami w podciągach równe są $h$

po takiej operacji tablica jest h-posortowana

#### Kluczowe twierdzenie

>Jeśli na k-posortowanej tablicy a[1..n] wykonamy h-sortowanie to tablica nadal pozostanie k-posortowana

Dowód: #todo 

#### Metoda Shella - opis
```python
# h_list - posortowana rosnąco tablica gdzie h_list[0] = 1
# t - tablica do posortowania
def shell_sort(h_list: list[int], t: list[int])
	for h in reverse(h_list):
		h-sort(t, h)
```
Pod koniec zawsze sortujemy z h=1, co sprawi że tablica będzie 1-posortowana=posortowana

Teraz pytanie: Jak dobrać ciąg kroków?
Pratt, 1971 $$1,2,3,4,6,8,9,\dots,2^p3^q$$
Długość ciągu - $O(\log^2n)$

dla danego kroku $2^p3^q$ wiemy że tablica jest już 
- $2^{p+1}3^q$-posortowana 
- $2^p3^{q+1}$-posortowana

Co oznacza że podciąg o kroku $2^p3^q$ jest już 2- i 3-posortowany 
Co wiemy o liczbie w inwersji w takim ciągu?
**Jest mniejsza od n/2**, dlaczego? #todo (do wykminienia samemu chyba xD trzeba rozrysować taki ciąg)

więc `h-sort` wykonuje się w czasie $O(n)$
Zatem cały algorytm Shella z krokami Pratta zajmuję $O(n\log^2n)$



## Bubble sort
xD 
- liczba porównań $n(n-1)/2$
- liczba zamian $Inv(a)$ (*pesymistyczne $O(n^2)$*)
- [[ASD Wykład 1 - Algorytmy i Sortowanie#Algorytm w miejscu|w miejscu]]
- [[ASD Wykład 1 - Algorytmy i Sortowanie#Stabliny algorytm sortowania|stabilny]]

## Selection sort

Iterując od końca
Z prefixu tablicy wybieramy maksymalny element i wkładamy go na koniec aktualnego prefixu

- liczba porównań $n(n-1)/2$
- liczba zamian $n-1$
- [[ASD Wykład 1 - Algorytmy i Sortowanie#Algorytm w miejscu|w miejscu]]

### Usprawnienie - Heap sort
#### Kopiec zupełny
Jest to pełne [[Drzewo binarne|drzewo binarne]] w którym mamy zachowaną własność: Rodzic jest niemniejszy/niewiększy (kopiec typu MAX/MIN) od swoich dzieci

Taki kopiec można zaimplementować w tablicy w której dziećmi węzła $a[i]$ są węzły $a[2i]$ oraz $a[2i+1]$

Dla ustalenia uwagi rozważajmy kopiec typu MAX

##### Dodawanie elementu od dołu (`upHeap`)
Zakładamy że mamy kopiec w tablicy na pozycjach $a[1..n-1]$ i chcemy dołożyć element $n$

Porównujemy go z elementem $a[\lfloor n/2\rfloor]$ który jest jego rodzicem i jeżeli jest większy to zamieniamy żeby zachować porządek kopcowy

Powtarzamy to dopóki rodzic nie będzie niewiększy lub trafimy do korzenia

Operacja taka ma koszt $O(\log n)$ ponieważ taka jest wysokość drzewa


##### Dodawanie elementu od góry (`downHeap`)

Jeżeli zamieniamy wartość w korzeniu to może się zdarzyć że zaburzymy porządek kopcowy przez zamian na mniejszy element

Wtedy możemy znowu przechodzić drzewo analogicznie do przykładu z budową kopca, tylko tym razem robimy to od góry, i za każdym razem zamieniamy nowy element z większym dzieckiem

Ta operacja ma także koszt $O(\log n)$
#### Heap sort - opis

Mając tablicę $a$ którą chcemy posortować, chcemy zbudować w niej kopiec zupełny typu MAX

Wiemy że na elementach powyżej indeksu $\lfloor n/2\rfloor$ mamy już zachowany porządek kopca ponieważ żaden z tych elementów nie posiada dzieci

Teraz mozemy iterować do początku tablicy, na każdym kolejnym elemencie stosując operację `downHeap`

Taka iteracja ma koszt $O(n)$ 
Dlaczego? #todo 

*(Coś w stylu że dla pierwszych $\sim n/4$ elementów mamy tylko jedną możliwą zamianę z synem, dla $\sim n/8$ dwie, i tak dalej, to się jakoś sumuje do $2n$ xD)*

Po tej iteracji mamy już zbudowany kopiec w całej tablicy 

---
Teraz przechodzimy do właściwego sortowania
iterując od tyłu tablicy zamieniamy aktualny element z pierwszym elementem tablicy który jest maksimum w kopcu, następnie poprawiamy kopiec operacją `downHeap`

Koszt tej iteracji jest rzędu $O(n\log n)$

**Zatem koszt całego algorytmu jest równy** $$O(n\log n)$$

## Merge sort
Metoda  [[Dziel i zwyciężaj]]

Dzielimy tablicę na pół, rekurencyjnie sortując obie połówki
Następnie scalamy oba posortowane ciągi, podstawowo scalanie odbywa się w tablicy pomocniczej

Tak naprawdę nie musimy używać wywołań rekurencyjnych, możemy od dołu scalać ciągi długości 2,4,8...

- liczba porównań $O(n \log n)$
- liczba przypisań $O(n \log n)$
- [[ASD Wykład 1 - Algorytmy i Sortowanie#Stabliny algorytm sortowania|stabilny]]

### Merge sort w miejscu (bez tablicy pomocniczej)
Nie zostało wytłumaczone na nagranym wykładzie :<
Da się to zrobić ale w praktyce rzadko się korzysta ponieważ bardzo zwiększa się stała przy $n \log n$

## Quick sort
Metoda  [[Dziel i zwyciężaj]]

Wybieramy ze zbioru element dzielący `p = pivot(a)`
dzielimy elementy na 
- `s1` = zbiór elementów mniejszych od `p` 
- `s2` = zbiór elementów większych od `p` 

naszym wynikiem jest `qs(s1), p, qs(s2)`

- liczba porównań: suma głębokości w drzewie obliczeń `qs`

Kiedy mamy najmniej porównań? gdy drzewo obliczeń jest pełnym drzewem binarnym, czyli `pivot(a)` zawsze dzieli tablicę na pół, wtedy ilość porównań jest rzędu $O(n\log n)$

Kiedy mamy najwięcej porównań? gdy drzewo obliczeń jest listą, czyli `pivot(a)` jest skrajnym elementem tablicy, wtedy ilość porównań jest rzędu $\Theta(n^2)$

Jeżeli pesymistyczna złożoność jest $O(n^2)$ to dlaczego nazywamy to sortowanie szybkim?

Spójrzmy na oczekiwaną ilość porównań gdy `pivot(a)` losuje element z tablicy z jednakowym prawdopodobieństwem
 #todo
 No ogólnie wychodzi średnio $n \log n$ z bardzo dobrą stałą $2/\log e \approx 1.4$ xD