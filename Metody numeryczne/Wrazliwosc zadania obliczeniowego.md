# Wrazliwosc zadania obliczeniowego

## Zadanie obliczeniowe
Dana jest funkcja $f: D \rightarrow W$, wyznaczyć $y = f(x)$
zakładamy że $W$ jest skończonego wymiaru

Przykład: 
oblicz $y = cos(x^2)$
oblicz $y = A\cdot x$ gdzie A to macierz

## Wrażliwość

Chcemy obliczyć $y = f(x)$ ale na komputerze dysponujemy tylko $x(1+\epsilon)$ ponieważ liczba jest reprezentowana w arytmetyce zmiennopozycyjnej

Błąd chcielibyśmy ograniczyć 
$$||f(\hat{x})_ - f(x)|| \leq C ||\hat{x} - x||$$
C = wrażliwość

## Współczynnik wzmocnienia błędu


$$cond_{abs}(f,x,\epsilon) = \sup_{||\Delta|| \leq \epsilon}\frac{||f(x + \Delta) - f(x)||}{||\Delta||}$$

Czyli patrząc na wszystkie zaburzenia niewiększe niż $\epsilon$  funkcja zwraca największy błąd względny

To pasuje jako definicja wrażliwości bo po przeliczeniu wychodzi że

$$||f(\hat{x}) - f(x)|| \leq cond_{abs}(f,x,\epsilon) ||\hat{x} - x|| \text{ dla } ||\hat{x} - x|| \leq \epsilon$$ 

>Dowód: mnożymy lewą stronę przez $\frac{||\hat{x} - x||}{||\hat{x} - x||}$ i możemy dodać supremum bo na pewno nie zmniejszy się wynik 

Idealizacja:

$$cond_{abs}(f,x) = \lim_{\epsilon \rightarrow 0^+}\sup_{||\Delta|| \leq \epsilon}\frac{||f(x + \Delta) - f(x)||}{||\Delta||}$$

gdy f jest różniczowalna to 
$$cond_{abs}(f,x) = ||f'(x)||$$

---
Analogicznie możemy zdefiniować wrażliwość błędu względnego

$$cond_{rel}(f,x) = \lim_{\epsilon \rightarrow 0^+}\sup_{||\Delta|| \leq \epsilon}\frac{\frac{||f(x + \Delta) - f(x)||}{||f(x)||}}{\frac{||\Delta||}{||x||}}$$


gdy f jest różniczowalna to 
$$cond_{rel}(f,x) = ||f'(x)|| \frac{||x||}{||f(x)||}$$

---

zatem dla $\hat{x} \approx x$
#### Absolutna
$$||f(\hat{x}) - f(x)|| \lesssim cond_{abs}(f,x) ||\hat{x} - x||$$ 

gdy f różniczkowalna to
$$||f(\hat{x}) - f(x)|| \lesssim ||f'(x)|| \cdot ||\hat{x} - x||$$ 

>Intuicja: błąd możemy szacować przez przybliżenie liniowe funkcji w punkcie, ponieważ zakładamy że $\hat{x}$ i $\hat{x}$ są blisko siebie

#### Relatywna

$$\frac{||f(\hat{x}) - f(x)||}{||f(x)||} \lesssim cond_{rel}(f,x) \frac{||\hat{x} - x||}{||x||}$$ 

gdy f różniczkowalna to
$$\frac{||f(\hat{x}) - f(x)||}{||f(x)||} \lesssim ||f'(x)|| \frac{||x||}{||f(x)||}  \frac{||\hat{x} - x||}{||x||} = ||f'(x)|| \frac{||\hat{x} - x||}{||f(x)||}   $$ 


## Terminologia

Zadanie **Dobrze uwarunkowane** gdy $cond(P,x)$ jest nieduże (rzędu 1)
Zadanie **Źle uwarunkowane** gdy $cond(P,x)$ jest bardzo duże


## Uwarunkowanie układu równań liniowych
zadanie: 
Rozwiązać układ równań $Ay = b$
$$f : S \times \mathbb{R}^N \rightarrow \mathbb{R}^N: f(A,b) = A^{-1} b$$
S = macierze nieosobliwe

Ustalamy zaburzenia danych
$$\frac{|| \tilde{A} - A||}{||A||} \leq \epsilon$$
$$\frac{|| \tilde{b} - b||}{||b||} \leq \epsilon$$

Pytanie
$$\frac{|| \tilde{y} - y||}{||y||} \leq C \cdot \epsilon$$
Jakie jest C?

Twierdzenie

$$\frac{|| \tilde{y} - y||}{||y||} \leq 4 ||A|| \cdot ||A^{-1}|| \cdot \epsilon$$

nazwijmy $cond(A)=||A|| \cdot ||A^{-1}||$



