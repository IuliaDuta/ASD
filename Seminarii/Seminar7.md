---
layout: item
permalink: /Seminarii/Seminar7
---

## Seminar 7

Acest seminar prezinta elemente de **Grafuri**

## BFS - in latime

Parcurgerea de tip BFS viziteaza nodurile unui graf pe nivele, in functie de distanta fata de un nod initial.

Foloseste o structura de tip coada.

**Algoritm**

Pas 1: se initializeaza toate distantele cu 1, mai putin nodul initial cu distanta 0

Pas 2: se itroduce primul nod intr-o coada q si se marcheaza ca vizitat

Pas 3: Se extrage primul nod din coada N. Se insereaza in coada toate nodurile vecine cu N, nevizitate inca, iar distanta este distanta pana la N + 1.

Pas 4. Se repeta Pasul3 pana cand coada devine goala.

!Obs. Algoritmul determina distanta minima intre un nod si toate celelalte din graf

!!Obs. In cazul unui arbore parcurgerea obtinuta incepand cu radacina este o parcurgere pe nivele

**Complexitate:** O(|V| + |E|)

<img src="/ASD/images/bfs.jpg"  height="220">


## DFS - in adancime

Parcurgerea de tip DFS viziteaza nodurle pana la frunze apoi se intoarce la celelalte.

**Algoritm** 

La nodul i: Se viziteaza toti vecinii lui i inca nevizitati si pentru fiecare se apeleaza recursiv procedura.

Complexitate: O(|V| + |E|)

Aplicatii:

- Determinati componetele conexe dintr-un graf
- Traversarea unui graf


<img src="/ASD/images/dfs.jpg"  height="220">


## Dijkstra

Se da un graf cu costuri asociate arcelor. Se cere distanta minima de la un nod la toate celelalte noduri.

Complexitate: O(|E| + |V|log|V|)

## APM

## Trie


