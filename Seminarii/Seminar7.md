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

Complexitate: O([E] + [V]log[V])

Algoritm:

Pas 1: Se marcheaza toate distantele cu infinit.

Pas 2: Se considera pentru prima iteratie nodul curent nodul sursa iar distanta corespunzatoare 0. Se updateaza distanta catre toti vecinii nevizitati ai nodului, daca suma distre calea directa intre cele 2 noduri si valoarea nodului curent e mai mica decat vechea valoare a nodului vecin. Se viziteaza nodul curent si se seteaza nodul curent ca nodul cu cea mai mica valoare, nevizitat inca. si se reia Pasul 2.

Obs. Pentru extragerea nodului curent se poate folosi o structura de tip min-heap.

## APM

Se da un graf neorientat cu costuri. Se cere determinarea unui arbore avand muchii din graf astfel incat suma muchiilor sa fie minima.

Obs. Cate muchii va avea? Se poate mereu?

### Algoritmul lui Prim

Pas 1: Se alege un nod random din graf si se adauga in arbore.

Pas 2: Din multimea muchiilor ce unesc varfuri din arbore cu cele neadaugate inca se alege cea de cost minim. Se adauga muchia la arbore si nodul ca facand paret din cele marcate in arbore.

Pas 3: Se repeta pasul 2 pana ce toate nodurile sut marcate.

Complexitate: 

O(V^2) - naive
O(E logV) - cu heapuri

### Algoritmul lui Kruskal

Pasul 1: Adauga toate muchiile intr-un min-heap dupa costuri. Si considera fiecare nod individual in prpria componenta.

Pasul 2: Extrage cea mai mica muchie din heap. Daca conecteaza 2 noduri din aceasi componenta ignora muchia, altfel o considera componenta a arborelui si cele 2 componente conexe sunt reunite in una singura.

Pasul 3: Repeta pasul 2 pana cand toate nodurile sunt in aceasi componeta.
 
Implementare:cu ajutorul multimilor de paduri disjuncte - explicatie pe scurt

Complexitate O(E log E)


## Trie

Motivatie: Vreau sa retin o multime de cuvinte despre care ma intereseaza: prefixe comune, frecventa, altele..

Structura folosita este un K-arbore (un arbore in care fiecare nod are K fii), unde K este lungimea alfabetului folosit. Fiecarei muchii i se asociaza o valoare reprezentand o litera a alfabetului. Fiecari nod i se asociaza cuvantul obtinut de la radacina urmarind literele muchiilor de pe drum.

Obs. Memoria necesara depinde de numarul de prefixe comune si lungimea acestora (daca multe cuvinte au acelasi prefix, acesta va fi stocat o singura data, diferenta fiind facuta doar de sufixele care se ramifica).

Aplicatii:

- Structura de stocare a unui dictionar cu determinare de prefixe comune, frecventa
- Sortare lexicografica
- Cautare predictiva

TO DO: Poza

TO DO: Probleme
