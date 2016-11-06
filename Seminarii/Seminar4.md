---
layout: item
permalink: /Seminarii/Seminar4
---

## Seminar 4

Acest seminar prezinta 2 structuri de date importante: **Arborii binari de cautare echilibrati AVL** si **Heapurile** .

## Arbori binari de cautare echilibrati AVL

Arbore binar de cautare in care inaltimile fiului stang si fiului drept al fiecarui nod difera prin cel mult +/- 1.

**Consecinta:** Inaltimea unui AVL e log n
**Implementare:** in fiecare nod se tine valoarea, fiul stang, fiul drept si diferenta de inaltime intre fii.

**Vizualizare operatii:** [aici](https://visualgo.net/bst) -> AVL Tree

**Inserare**

Pasul 1: Se insereaza, ca in BST, la locul potrivit conform algoritmului de cautare in arbore. Diferenta de inaltime intre cei 2 poate deveni acum +/- 2 .

Pasul 2: Rebalansam cu ajutorul **rotatiilor**

Exista 4 tipuri de rotatii:

- stanga
- dreapta
- stanga-dreapta
- dreapta-stanga

**Rotatia stanga**

-atunci cand se insereaza in staga nodului din stanga

<img src="/ASD/images/leftRotation.png"  height="220">

**Rotatia dreapta**

-atunci cand se insereaza in dreapta nodului din dreapta

<img src="/ASD/images/RightRotation.png"  height="220">

**Rotatia stanga-dreapta**

-atunci cand se insereaza in dreapta nodului din stanga

<img src="/ASD/images/LeftRightRotation.png"  height="220">

**Rotatia dreapta-stanga**

-atunci cand se insereaza in stanga nodului din dreapta

<img src="/ASD/images/RightLeftRotation.png"  height="220">

Exemplu:

<img src="/ASD/images/AVLTree.jpg"  height="220">

insert 14, 3, 45, 7, 15

**De ce??**

- utile pentru queryuri succesive de inserare, cautare, stergere

**STL**
set:  std::set<int> myset;

## Heapuri

- arbore binar aproape complet (ultimul nivel poate fi incomplet, dar completarea se face de la stanga la dreapta) in care fiecare nod e mai mare/ mai mica ca ambii fii.

Variante:

- max-heap: fiecare nod mai mare ca fiii sai.
- min-heap: fiecare nod mai mic ca fiii sai.

**Implementare:** Se construieste ca un vector in care:

  - parinte(i) -> pozitia i/2
  - left(i) -> pozitia 2*i
  - right(i) -> pozitita 2*i+1
  
  <img src="/ASD/images/heapTreeArray.png"  height="220">
  
  **De ce?**
  
  - sortare de tip heapsort
  - coada cu prioritati cand avem multe extrageri/ interogari de maxim/minim.
  
  **STL**
  
  priority_queue: std::priority_queue<int> mypq;
  

  **Max-heapify**
  
  -reface structura de max-heap intr-un nod pentru care subarborii respecta conditia de max-heap, dar nodul nu e mai mare ca ambii fii.
  
  Pasul 1: cautam maximul intre left(i) si right(i)
  
  Pasul 2: interschimbam nodul curent cu cel mai mare dintre acestea
  
  Pasul 3: reapelam max-heapify pt acesta.
  
  Complexitate: O(log n)
  
  **Construirea unui heap dintr-un vector nesortat**
  
  Pasul 1: se stocheaza elementele intr-un vector
  
  Pasul 2: pt i = len(A)/2 .. 1 apelam max_heapify(A, i)
  
  Complexitate O(n)
  
  **Decapitarea heapului**
  
  Pasul 1: punem ca radacina nodul de pe ultima pozitie din vector si reducem cu 1 dimensiunea
  
  Pasul 2: apelam max-heapify
  
  Complexitate O(log n)
  
  **Inserarea**
  
  Pasul 1: Incrementam cu o unitate lungimea vectorului. Inseram elementul pe ultima pozitie din vector.
  
  Pasul 2: Urcam in heap atata timp cat A[i] > A[i / 2] cu interschimbare
  
  Complexitate: O(log n)

  ** HeapSort**
  
  Pasul 1: Construim heapul pornind de la vectorul nesortat
  
  Pasul 2: Decapitam max-heapul, dar lasam elementul scos pe ultima pozitie din vector, izolat de arbore (lungimea efectiva a vectorului scade cu o unitate la decapitare, insa elementul inca este acolo).
  
  <img src="/ASD/images/heapSort.jpg"  height="350">


