---
layout: item
permalink: /Seminarii/Seminar3/
---

## Seminar 3

Acest seminar introduce concepul de **Arbore binar de cautare**, **cautare binara**, **cautare ternara**, **rmq**

## Arbori binari de cautare

Arbore binar in care nodurile indepliesc conditiile: 
- key[x] <= key[root], pt orice x din subarborele stang al nodului root
- key[x] >= key[root], pt orice x din subarborele drept al nodului root

Implementare: pt fiecare nod tin partinte[nod], left[nod], right[nod]

 <img src="/ASD/images/2000px-Binary_search_tree.svg.png"  height="220">
 
 - parcurgerea in inordine determina sortarea numerelor
 
 
**Cautarea unui nod**
 
 <font color="red">Complexitate: O(h)</font>
 
 
```C++

Search(nod, val)
   if(x == null || key[nod] == val)
      return x
   else
      if(val < key[nod])
         return Search(left[nod], val)
      return Search(right[nod], val)
```

**Minim/Maxim**

 <font color="red">Complexitate: O(h)</font>
 
 minim: cel mai din stanga - merg doar pe left
 maxim: cel mai din dreapta - merg doar pe right
 
**Inserare**
 
 <font color="red">Complexitate: O(h)</font>
 
 <img src="/ASD/images/insert_BST.bmp"  height="220">
 
 Se aplica cautarea in arborele binar si cand ajung la null inserez in acel loc nodul
 
**Stergere**
 
 <font color="red">Complexitate: O(h)</font>
  
 <img src="/ASD/images/delete_nod_BST.gif"  height="320">
 
 Distingem 3 cazuri:
 
 - nodul de sters nu are fii:
    doar se sterge respectivul nod
  
 - nodul de sters are un fiu:
    ridicam fiul in locul nodului de sters
    
 - nodul de sters are 2 fii:
    ii cautam succesorul, stergem succesorul din arbore si inlocuiesc nodul de sters cu valoarea succesorului
    
 Creare arbore: worst case/ best case?
 Sortare cu arbore de cautare binar
 
 ## Cautare binara
 
 
 <font color="red">Complexitate: O(log n)</font>
 
 **Problema:** Se da o lista de numere sortata, se cere sa se caute un element in lista.
 
 Se aplica nu doar pe siruri sortate, ci pe functii crescatoare 
 Se poate aplica si pentru next smallest, nest largest element
 
 **Algoritm**
 Se compara valoarea cu elementul aflat in mijlocul sirului. 
 Daca val > v[mid]: se continua cautarea in jumatatea dreapta a sirului
 Daca val < v[mid]: se continua cautarea in jumatatea stanga a sirului
 
```C++

BinarySearch(val, left, right)
   if(left > right)
      if(v[right] == x)
         return right + 1
      return -1
   mid = (left + right) / 2    /// left + (right - left) / 2 pt a evita overflowul
   if(v[mid] <= x)
      return BinarySearch(val, mid + 1, right)
   else
      return BinarySearch(val, left, mid - 1)
          
```
 

**Cautare binara pe biti**

Este mai rapida

```C++

long long binary_search()
    long long i, pas ;
    for(pas = 1; pas < K; pas <<= 1);
    for(i = 0; pas; pas >>= 1)
    {
        if(( v[i + pas] <= k - 1)
            i += pas;
    }
    return i + 1;

```
 
## Cautare ternara

 <font color="red">Complexitate: O(log n)</font>
 
Calculeaza maximul/ minimul intr-o functie unimodala (cu un singur punct cel mai marecel mai mic)

 <img src="/ASD/images/ternary.png"  height="220">

**Algoritm:**

Se fragmenteaza inputul in 3 subsegmente egale pri alegerea a 2 puncte:

mid1 = left + (right - left) / 3
mid2 = right - (right - left) / 3

daca f(mid1) <  f(mid2): continui cautarea pe [mid1, right]
daca f(mid1) >  f(mid2): continui cautarea pe [left, mid2]
daca f(mid1) =  f(mid2): continui cautarea pe [mid1, mid2]

**Implementare:**

```C++

ternarySearch(f, left, right)
   if(right - left < eps)
      return (left + right) / 2
   mid1 = left + (right - left) / 3
   mid2 = right - (right - left) / 3
   
   if(f(mid1) < f(mid2))
      return ternarySearch(f, mid1, right)
   if(f(mid1) > f(mid2))
      return ternarySearch(f, left, mid2)
   if(f(mid1) - f(mid2) < eps)
      return ternarySearch(f, mid1, mid2)

```
 
### Probleme:

- Se da un sir de numere sortat. Cate perechi de numere au suma k
- Se da un sir sortat care a fost rotit circular la dreapta cu un numar de pozitii. Sa se determine pozitia de la care a fost rotit
- Se da un sir sortat care a fost rotit circular la dreapta cu un numar de pozitii. Sa se determine pozitia de la care a fost rotit. Sa se gaseasca o valoare v in acest sir
- Proc [click](http://www.infoarena.ro/problema/proc) 
- Inflight Entertainment - PI
- Sa se determine mediana comuna a 2 vectori: de aceasi lungime. de lungimi diferite
- Sa se determine al k-lea cel mai mic numar din interclasarea a 2 siruri sortate
- Sa se gaseasca elementul c intr-un sir aproape sortat (a fost sortata, dar ulterior cateva din elementele adiacente au fost inversate)


### RMQ

Se da un sir de n numere. Se cere sa se raspunda la queryuri de tipul: care este cel mai mic element din intervalul [l, r]

[link](https://www.topcoder.com/community/data-science/data-science-tutorials/range-minimum-query-and-lowest-common-ancestor/)

