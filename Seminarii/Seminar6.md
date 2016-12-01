---
layout: item
permalink: /Seminarii/Seminar6
---

## Seminar 6

Acest seminar prezinta **Tabele de dispersie**.

## General

**Motivatie**

Dorim sa implementam un dictionar de date (cheie, valoare), cu acces rapid si timp redus la inserare/stergere.
Exemplu: vector de frecventa pentru numere intr-un range foarte mare.

**Metoda directa**
Stocam un vector de dimensiune MAX_VALUE si stocam informatia pe pozitia cheii, asemeni vectorului de frecventa. 

Probleme: 
- dimensiune mare
- numere negative
- stringuri

**Implementare**
Se foloseste o structura care are la baza:
- o tabela de dispersie de dimensiune m ~ numarul de intrari din dictionar ( << dimensiunea spatiului)
- o functie de dispersie: h : - K -> {0 .. m} care mapeaza cheia la o regiune din tabela de dispersie.
                              - valoarea cheii k nu mai e stocata pe pozitia k, ci pe pozitia h(k), avand valoarea maxima mult mai mica (m)

<img src="/ASD/images/hash_general.jpg"  height="220">

**Complexitate**

Ideal: O(1) pe toate operatiile
Probleme: pot aparea coliziuni care cresc timpul la operatia de cautare.

Coliziunea - atunci cand 2 chei distincte k1, k2 sunt mapate la aceasi zona din tabela: h(k1) = h(k2) cu k1 =/= k2

## Fuctii de dispersie

h :  K -> {0 ..m - 1}

1. Modul

**h(k) = k % m**

Obs:

- m sa nu fie putere a lui 2 (se uita doar la ultimii p biti) - usor de creat coliziuni
- m sa nu fie putere a lui 10 (se uita doar la ultimele cifre) - usor de creat coliziuni
- indicat ca (m, k) = 1, deci m prim departe de 2^p sau 10^s

2. Multiplicativ

**h(k) = [m * (k * A mod 1)]**, cu 0 < A < 1

(x mod 1) - partea fractionara a lui x luata ca intreg
Aplicare: 
- se calculeaza dimensiuea lui k (w biti)
- se inmulteste k cu (A * 2^w) - alegem deci m = s / 2^w
- se iau primii p biti din ultimii w => maparea

<img src="/ASD/images/multiplication-hashing.jpg"  height="220">

3. Folding

k = k1 k2 k3 .. kr

**h(k) = (k1 + k2 + .. + kr) % (10^l)**

4. **(k) = [k * k / (10^c1)] % (10^c2)**

- calculeaza k^2 si ia c2 cifre din mijlocul numarului

## Rezolvarea coliziunilor

1. Prin inlantuire

Fiecare casuta i din tabela de hashing tine o lista inlantuita de valori corespunzatoare tuturor coliziunilor cu valoarea i.

Atunci cand cautam cheia k parcurgem lista corespunzatoare lui h(k) cautand cheia noastra.

Worst Case: O(n) - toate cheile creaza aceasi coliziune si trebuie parcursa toata lista

<img src="/ASD/images/chaining.png"  height="220">

2. Prin adresare directa(deschisa)

Fiecare casuta tine exact o cheie, m este deci mai mare ca numarul de intrari din dictionar.
Avem prin functie o modalitate de tratare a coliziunilor

h: K x {0..m - 1} -> {0 .. m-1}
h(k, i) - in ce este mapat k daca am intalnit a i-a coliziune

<img src="/ASD/images/Double_hash.png"  height="220">

**Adresare liniara**

h(k, i) = (h'(k) + i) % m

- calculam h'(k)
- Daca casuta este goala -> completam
- Daca casuta este ocupata -> cautam prima casuta neopcupata din tabela (privita ciclic)

**Adresarea patratica**

h(k, i) = (h'(k) + i * i)  % m

- calculam h'(k)
- Daca casuta este goala -> completam
- Daca casuta e ocupata -> incrementam i-ul si cautam in casuta h(k, 1). Daca e ocupata repetam pasul pana gasim o casuta goala

**Double hashing**

h(k, i) = (h1(k) + i * h2(k)) % m

Obs.

- se alege h2 - impar
- se alege m putere a lui 2

## Hashing pe stringuri

- dictionarele nu asociaza intotdeauna valori unor chei de tip intreg. Ele pot fi alte structuri de date. Exemplu: stringuri

Exemple de functii de hashing pe stringuri:

- nuamrul de caractere al stringurlui
- (Suma din a^i * xi) % size cu (a, size) = 1
- Suma codului ascii in perechi de cate 2/4

## STL

- dictionarele de date sunt implementate si in libraria STL:

unordered_map<tip_cheie, tip_valoare> mymap

! Structurile folosite pe post de cheie trebuie sa aiba o functie de hashing implementata - operator() - si operatorul de egalitate - operator== -.

Elementele se acceseaza usor, ca intr-o tabela obisnuita:

mymap[cheie] = valoare

## Cuckoo hashing

## Rolling hash






   

