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

- Foloseste paradigma **divide and conquer**
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

### Quick Sort


  
  
  
  
  
  
  
 
  

