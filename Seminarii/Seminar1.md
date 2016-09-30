---
layout: item
permalink: /Seminarii/Seminar1/
---

## Seminar 1

Acest seminar introduce concepte de baza legate de **stive** si **cozi** si o introducere in **complexitatea** timp si spatiu a unor algoritmi.


### Stive si cozi


- structuri de date ce stocheaza informatie, dar accesul se face pe baza unor reguli proprii.

| Stiva                         | Coada                         |
| ------------------------------|:-----------------------------:| 
| - LIFO                        | - FIFO                        | 
| - push/pop/top                | - enqueue/dequeue/head/tail   |  
| - stiva de vase               | - coada de la magazin         |

#### Probleme: underfow/overflow

#### Stiva

``` C++
  typedef struct {
    int content[100];
    int top;
  
    int pop(){						
      int x = content[top];
      if(top >= 0){
          --top;
      }
      return x;
    }
  
    void push(int val){
      ++top;
      content[top] = val;
    }
  
    bool isempty(){
      return (top < 0);
    }
  } my_stack;
```

**Probleme:**. -memoria alocata inutil (O(max elemente la un moment))

**STL**

Implementare de baza:

``` C++

stack<int> mystack;


- top()
- pop()
- push(val)
- empty()
```

#### Coada

Implementare de baza:

``` C++
typedef struct{						
    int content[100];				
    int head;
    int tail;

    int dequeue(){
        int x = content[head];
        if(head <= tail)
            ++head;
        return x;
    }

    void enqueue(int val){
        ++tail;
        content[tail] = val;
    }

    bool isempty(){
        return (head > tail);
    }
}myqueue;

```

**Problema:**  


-memorie muulta (O(nr_elemente_total))

**Solutie:** 


-solutie: coada circulara / stl
    
**STL:**


``` C++
queue<int> q;

- push(int)
- pop()
- front()
- empty()
```

Coada circulara:

``` C++
	int dequeue(){
        int x = content[head];
        if(head == length)
            head = 1;
		++head;
        return x;
    }

    void enqueue(int val){
        ++tail;
		if(tail == length + 1)
			tail = 1
        content[tail] = val;
    }
	
```

### Probleme


- 2 stive dintr-un vector [click](http://www.geeksforgeeks.org/efficiently-implement-k-stacks-single-array/)
- coada din 2 stive (Queue)
- stiva din doua cozi
- parantezare corecta / Editor
- Trompeta
- STPAR [click](http://www.spoj.com/problems/STPAR/)
- ONP [click](http://www.spoj.com/problems/ONP/)
- Maximum Element [click](https://www.hackerrank.com/challenges/maximum-element)
 		sau [click](http://www.geeksforgeeks.org/design-a-stack-that-supports-getmin-in-o1-time-and-o1-extra-space/))
- sort stack with recurson [click](http://www.geeksforgeeks.org/sort-a-stack-using-recursion/)
- Evaluating arithmetic expressions

**Memorie:** 


-memorie: O(maxim_asteptat) <- riscuri

#### Dequeue


- In aceasta structura, valorile pot fi inserate sau eliminate atat pe la inceputul, cat si pe la sfarsitul deque-ului, toate aceste operatii avand loc in timp O(1) amortizat.

```C++

dequeue<int>
push_back
push_front
pop_back
pop_front

```

### Probleme:


- dequeue [click](http://www.infoarena.ro/problema/deque)

### Extra:

- In-place Linked List Reverse (park)
- Delete Node
- K-th to the last node
- Largest stack
- Find cycle
- Clone a linked list with next and random pointer


