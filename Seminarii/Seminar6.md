---
layout: item
permalink: /Seminarii/Seminar6
---

## Seminar 6

Acest seminar prezinta **Tabele de dispersie**.

##Hashuri

**Motivatie**

Dorim sa implementam un dictionar de date (cheie, valoare), cu acces rapid si timp redus la inserare/stergere.

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

TO DO: imagine

**Complexitate**

Ideal: O(1) pe toate operatiile
Probleme: pot aparea coliziuni care cresc timpul la operatia de cautare.

Coliziunea - atunci cand 2 chei distincte k1, k2 sunt mapate la aceasi zona din tabela: h(k1) = h(k2)



