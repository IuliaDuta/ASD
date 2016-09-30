---
layout: item
permalink: /Seminarii/Seminar2/
---

## Seminar 2

Acest seminar propune mai multe **tipuri de sortari** precum si aplicatii ale acestora.

### Insertion Sort

<font color="red">Complexitate: O(n<sup>2</sup>)</font>

Iteram prin vector si la fiecare pas j avem sortat vectorul A[1..j-1] si cautam locul lui A[j].

``` C++

for j = 2 to len
  key = A[j]
  i = j - 1
  while i > 0 and A[i] > key
      A[i + 1] = A[i] //deplasam totul la dreapta pt a-i face loc
      --i
   A[i + 1] = key
   
```

### Merge Sort

<font color="red">Complexitate: O(n log n)</font>

Foloseste paradigma **divide and conquer**
    divide: imparte inputul A[1..n] in 2 parti egale
    conquer: sortam recursiv cele doua jumatati
    combine: aplicam merge pe cele 2 subsiruri sortate (liniar)
  
  ``` C++
  
  Merge_Sort(A, p, r)
  
    if p < r
      q = (p + r) / 2
      Merge_Sort(A, p, q)
      Merge_Sort(A, q + 1, r)
      Merge(A, p, q, r)
    
```

a

### Quick Sort

<font color="red">Complexitate: O(n log n)</font>

La fiecare pas gasim pozitia pivotului in sirul sortat

divide: partitioneaza inputul A[p..r] in A[p..q-1] si A[q+1..r] cu proprietatea ca 
              A[p..q-1] <= A[q] si A[q] <= A[q+1..r]
conquer: sortam ambele subsiruri apeland recursiv quicksortul
combine: alipim sirurile

Partitia se poate face in mai multe moduri:
  -Hoare
  -Lomuto
  -cu pivot mobil
  -randomizat (mai eficient pe cazul mediu)
  -median of 3
  
 ``` C++

Quick_Sort(A, p, r)
  q = Partition(A, p, r)
  Quick_Sort(A, p, q - 1)
  Quick_Sort(A, q+1, r)
  
Partition:
  pivot = A[r]
  i = p - 1
  for j = p to r - 1
    if A[j] < pivot
      ++i
      swap A[i] A[r]
  swap A[i + 1] A[r]
  return i + 1
  
```

### Bucket Sort

<font color="red">Complexitate: O(n)</font>

presupune ca elementele sunt generate dupa o distributie uniforma in [0, 1)

Inputul este impartit in k bucketuri. 
Fiecare din bucket contine lementele din itervalul [i / k, (i+1) / k) si se sorteaza cu insertion sort

functioneaza cand suma patratelor dimensiunii bucketului e liniar

### Counting Sort

<font color="red">Complexitate: O(n)</font>

presupune ca elementele sunt in intervalul [0, k]

Se calculeaza frecventa elementelor. Punem elemente pe pozitia corespunzatoare,.
  c[x] - numarul de elemente <= x

```C++

Counting_Sort
  for j = 1 to n
    c[a[j]]++
  for i = 1 to k
    c[i] = c[i] + c[i - 1]
  for j = n to 1
    b[c[a[j]]] = a[j]
    c[a[j]]--;

```

### Radix Sort

- folosit in sortarea pachetelor de carti
- folosit in sortarea elementelor cu multiple campuri

Se sorteaza numerele succesiv dupa cifre, de la cea mai nesemnificativa spre cea mai semnificativa.
Sortarea folosita la fiecare pas trebuie sa fie **stabila**. (nu schimba ordinea cartilor apartinand anterior aceleiasi categorii)

```C++

Radix_Sort
  for i = 1 to d
    sortez stabil numerele dupa cifra a i-a in ordinea importantei
    

```


  
  
  
  
  
  
  
 
  

