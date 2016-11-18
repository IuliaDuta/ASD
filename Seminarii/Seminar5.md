---
layout: item
permalink: /Seminarii/Seminar5
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

build(int nod, int l, int r, x)

- in nodurile interioare: apelam recursiv pe fiii nodului si reunim valorile in nodul curent
- in frunze: updatam valoarea

``` C++
build(nod, l, r){
	daca r - l == 1 //sunt in frunza
		suma[nod] = a[l];
		return ;
	}
	mid = (l+r)/2;
	build(2 * nod, l, mid);
	build(2 * nod + 1, mid, r);
	suma[nod] = suma[nod * 2] + suma[nod * 2 + 1];
}
```

**Update**

- modificam valoarea de pe pozitia pos cu x
- la fel ca la constructie, dar updatam un singur element, iar restul sumelor care il contine cresc cu diferenta fata de valoarea initiala

``` C++
update(pos, x, nod, l, r){
	suma[nod] += x - a[pos];
	if(r - l == 1){	//	sunt in frunza pos
		a[pos] = x;
		return ;
	}
	mid = (l + r)/2;
	if(pos < mid)
		modify(pos, x, 2 * nod, l, mid);
	else
		modify(pos, x, 2 * nod + 1, mid, r);
}
```

**Query**

- interogam suma/min/max pe un interval
- daca intervalul din nod e inclus in intervalul dorit intoarcem valoarea din nod
- daca intervalul e disjunct cu intervalul din query intoarcem 0
- daca e inclus in fiul stang apelam recursiv pe stanga => val1
- daca e inlus in fiul drept apelam recursiv pe stanga => val2
- intoarcem val1 + val2

``` C++
query(st_q, dr_q, int nod, l, r){
	if(st_q >= r or l >= dr_q)	return 0
	if(st_q <= l && r <= dr_q)	return suma[nod]

 mid = (l+r)/2;
	val1 = query(st_q, dr_q, nod * 2, l, mid)
 val2 = query(st_q, dr_q, nod * 2 + 1, mid, r)
 return val1 + val2
}
```

## Arbori indexati binar (AIB)

**Motivatie:** Aceasi ca in cazul arborilor de intervale

**De ce?** Mai rapid si mai usor de implementat. :)

**Explicatie suma**

QUERY:

- se foloseste un vector v[i] - suma pe (i - 2^k, i]. (pozitiile divizibile cu 2^k stochează suma ultimelor 2^k elemente)
- cu ajutorul lui calculam sumele partiale [1..y]
- descompunem pe y ca suma de patrate iar suma se obtine ca suma de v[k] k se obtine din y eliminand succesiv cate un bit de 1

``` C++
void Add(int x, int quantity)
{
    int i;
 
    for (i = x; i <= N; i += zeros(i))
        AIB[i] += quantity;
}
```

UPDATE:

``` C++
int Compute(int x)
{
    int i, ret = 0;
 
    for (i = x; i > 0; i -= zeros(i))
        ret += AIB[i];
    return ret;
}
```

## Coduri Huffman

Exista codificari: 

- cu lungime fixa: mai putin eficient din punct de vedere al lungimii
- cu lungime variabila

**De ce Huffman?** Ne dorim un arbore optim (minimizeaza suma w * lg_pana_la_frunza)

**Algoritm**
Arbore Huffman: Arbore binar avand ca frunze datele de intrare insotite de ponderi, iar muchiile sunt codificate astfel:

- muchia stanga: 0
- muchia dreapta: 1

TO DO: IMAGINE

La fiecare pas vom impreuna nodurile cu cele mai mici ponderi=> un nod interior cu ponderea suma fiilor sai.

**Observatii**

- Arborele nu este unic din cauza cazurilor de egalitate intre ponderi
- Decodificarea unui mesaj este unica (are proprietatea prefix: codul niciunei litere nu este prefix al altei litere)
- e optim

