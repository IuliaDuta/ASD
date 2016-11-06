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

**Vizualizare operatii:** https://visualgo.net/bst -> AVL Tree

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




