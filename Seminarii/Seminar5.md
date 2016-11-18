---
layout: item
permalink: /Seminarii/Seminar4
---

## Seminar 5

Acest seminar prezinta urmatoarele concepte **Arbori de intervale**, **Coduri Huffman** .

## Arbori de intervale

arbore binar echilibrat, in care:
 
- fiecare nod interior este asociat unui interval
- fiecare frunza este asociata unei pozitii din vector

TO DO: IMAGINE

**Cand folosesc?** Am un sir de numere si queryuri pe intervale (suma, maxim, minim), intercalate cu queryuri de update pe element.

**Implementare:** La fel ca la heap. Se construieste ca un vector in care:

  - parinte(i) -> pozitia i/2
  - left(i) -> pozitia 2*i
  - right(i) -> pozitita 2*i+1

Numar maxim de noduri: 4*n

**Vizualizare operatii:** [aici](http://visualgo.net/segmenttree)

**Constructie**

-




