# Algotytmy numerycznie poprawne

Problem zadanie obliczeniowe (zdefiniowane tak samo jak w [[Wrazliwosc zadania obliczeniowego#Zadanie obliczeniowe]])

algorytm to przekształcenie które używając sekwencji operacji elementarnych przekształca $x \rightarrow f(x)$

zwykle będzie skończoną sekwencją operacji

wynik będzie obarczony błędem reprezentacji w fl
realizacja algorytmu wymaga operacji w fl które też dodają błędy reprezentacji

## Algorytm numerycznie poprawny

$y = f(x)$ 
$\tilde{y} = fl(A(fl(x))= f(\tilde{x})$

Czyli, chcemy żeby nasz algorytm produkował wyniki które są dokładnymi wynikami funkcji dla zaburzonych danych

czyli chcemy żeby $fl(A(fl(x))$ = $A(fl(x))$

algorytmy numerycznie poprawne mogą być szacowane przez wrażliwość problemu [[Wrazliwosc zadania obliczeniowego#Współczynnik wzmocnienia błędu]]

