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
 
 ### Cautarea unui nod
 
 <font color="red">Complexitate: O(h)</font>
 
 ``` C++

Search(nod, val)
   if(x == null || key[nod] == val)
      return x
   else
      if(val < key[nod])
         return Search(left[nod], val)
      return Search(right[nod], val)
      
```

### Minim/Maxim

 <font color="red">Complexitate: O(h)</font>
 
 minim: cel mai din stanga - merg doar pe left
 maxim: cel mai din dreapta - merg doar pe right
 
 ### Inserare
 
 <font color="red">Complexitate: O(h)</font>
 
 <img src="/ASD/images/insert_BST.bmp"  height="220">
 
 Se aplica cautarea in arborele binar si cand ajung la null inserez in acel loc nodul
 
 ### Stergere
 
 <font color="red">Complexitate: O(h)</font>
  
 <img src="/ASD/images/delete_nod_BST.gif"  height="220">
 
 Distingem 3 cazuri:
 
 - nodul de sters nu are fii:
    doar se sterge respectivul nod
  
 - nodul de sters are un fiu:
    ridicam fiul in locul nodului de sters
    
 - nodul de sters are 2 fii:
    ii cautam succesorul, stergem succesorul din arbore si inlocuiesc nodul de sters cu valoarea succesorului
    
 Creare arbore: worst case/ best case?
 Sortare cu arbore de cautare binar
 
 
 
 
 
 
 
