# 数据结构与算法

# Data Structures

## Lists

### Array Lists

A list could be defined as a structure array (static):

```
struct{
    int Number;
    char Name[20];
    float Score[10];
}Array_List[20];
```

### Linked Lists

```
struct Node;
typedef struct Node * PtrToNode ; 
typedef PtrToNode List;
typedef PtrToNode Position;

struct Node{
    int Element;
    Position Next;
}
```

The functions see course04:
- MakeEmpty()
- IsEmpty()
- IsLast()
- Find()
- FindPrevious()
- Delete()
- Insert()
- InsertBefore()
- DeleteList()
- Header()
- First()
- Advance()
- Retrieve()

### Doubly Linked Lists

Singly linked lists are not efficient to conduct a backward traverse. 

```
typedef struct DlNode{
    int Element;
    struct DlNode *Prior, *Next;
} *PtrToNode

typedef PtrToNode DlList;
typedef PtrToNode Position;
```

### Circularly Linked Lists

It is convenient to have the last cell keeping a pointer back to the first. Traverse more efficiently. 

## Stacks

A stack is a list with the restriction...

Fundamental operations: Top, Push, Pop

LIFO

### Linked List Implementation

```
struct Node;
typedef struct Node * PtrToNode;
typedef PtrToNode Stack;

struct Node{
    int Element;
    PtrToNode Next;
};

Stack CreateStack(void){ 
    Stack S;
    S = (PtrToNode ) malloc sizeof struct Node);
    if(S==NULL){
        printf (“Out of n”);
        return NULL;
    }
    S->Next = NULL;
    return S;
}
```

#### Push

```
void Push(int X, Stack S){
    PtrToNode TmpCell
    TmpCell = PtrToNode ) malloc sizeof struct Node));
    if(TmpCell == NULL){
        
    }
    else{
        TmpCell ->Element = X;// 1
        TmpCell ->Next = S -> Next;// 2
        S->Next = TmpCell;// 3
    }
}
```

#### Pop

```
void Pop(Stack S){
    PtrToNode FirstCell;
    if(IsEmpty(S))
        printf(“Empty stack and nothing to n”);
    else{
        FirstCell = S -> Next;// 1
        S->Next = S ->Next -> Next;// 2
        free(FirstCell ); // 3
    }
}
```

### Array Implementation

Dynamically Allocated Array

```
int *array;
array = (int*)malloc(sizeof(int)*MaxSize)
```

#### Push

```
void Push(int X, Stack S){ 
    if(IsFull(S))
        printf(“Full n”);
    else{
        S ->TopOfStack ++;
        S->Array[S->TopOfStack] = X;
    }
}
```

#### Pop

No need to clean the top cell. 

```
void Pop(Stack S){ 
    if(IsEmpty(S))
        printf(“Empty n”);
    else
        S->TopOfStack --;
}
```

### Applications

迷宫，8皇后

## Queues

FIFO

```
struct QueueRecord{
int Capacity;
int Front;
int Rear;
int Size;
int *Array;
};
```

### Enqueue

Circular Array

```
void Enqueue(int X, Queue Q){
    if(IsFull(Q))
        printf(“Full \n”);
    else{
        Q->Size ++;
        Q->Rear = Succ(Q->Rear, Q);
        Q->Array[Q->Rear] = X;
    }
}

int Succ(int Position, Queue Q){ 
    if(++Position == Q->Capacity)
        Position = 0;
    return Position;
}
```

### Dequeue

```
int Dequeue(Queue Q){
    int X;
    if(IsEmpty(Q)){
        printf(“Empty \n”);
        return -10000;
    }
    else{
        Q->Size --;
        X = Q->Array[Q->Front]
        Q->Front = Succ(Q->Front, Q);
        return X;
    }
}
```

### Applications

waiting queues, Access to shared resources, Multiprogramming

洪水算法，shortest path in a maze

## Trees

### Binary Trees

```
typedef struct TreeNode *PtrToNode;
typedef struct PtrToNode Tree;
struct TreeNode{
    int Element;
    Tree Left;
    Tree Right;
}
```

#### Traversal

- Depth-first
    - Inorder traversal 中序遍历 LDR
    - Postorder 后序遍历 LRD
    - Preorder 先序遍历 DLR

- Breadth-first
    - Level-order traversal

### Treaded Binary Trees

- Inorder Treaded Binary Trees
    - If a node has a NULL left child, we make its left child point to its Inorder predecessor
    - If a node has a NULL right child, we make its right child point to its Inorder successor.

### Binary Search Trees

Every node is assigned with an unique key value.

For every node, X, in the tree, the values of all the keys in its LEFT sub tree are SMALLER than X;

For every node, X, in the tree, the values of all the keys in its RIGHT sub tree are LARGER than X.

Delete 有点烦……

The ideally efficient BST should be BALANCED. 

### AVL Trees

the most popular binary search trees satisfying a balance condition.

that, for every node in the tree, the height of the left and right sub trees can differ by AT MOST 1. 

Insertion 贼烦…… rotation

### B-trees

## Graphs

Adjacency list/matrix

Topological Sort

### Shortest-Path Algorithm

BFS, DFS

- Unweighted graph
    - queue
- Weighted graph
    - Dijkstra

Critical Path
- Earliest completion time
- Latest completion time
- Slack times

All-pairs shortest path
- Using adjacency matrix

Floyd-Warshall algorithm

Network flow

Minimum Spanning Tree
- considering cost weighted graph, if we are asked to traverse the graph with lowest cost, then a MST will be constructed. 
- Prim's algorithm
- Kruskal's algorithm

# Algorithms

Iteration version is better than recursion version. 

## Algorithm Analysis

Correctness/Effectiveness, Readability, Robustness, Efficiency (time, space)

## Searching

### Binary Search

对于已经sorted的数据，always search in half, O(logN)

### Interpolation Search

## Sorting

### Straight Selection Sort

找到最小的，换到最前

```
void selection_sort(int A[], int N){
    int i , j, min, temp;
    for(i = 0; i < (N 1); i ++){ 
        min = i;
        for (j = (i+1); j < N; j++){ 
            if(A[j] < A[min])
                min = j; 
        }
        if(i!= min){ 
            temp = A[i];
            A[i] = A[min];
            A[min] = temp;
        }
    }
}
```

$O(N^2)$

#### Bubble Sort

```
void BubbleSort(int A[], int N) { 
    int j, P; 
    int Tmp; 
    for(P=1; P<N; P++) { 
        for(j=0; j<N-P; j++) { 
            if(A[j] > A[j+1]) { 
                Tmp = A[j]; 
                A[j] = A[j+1]; 
                A[j+1] = Tmp; 
            } 
        } 
    } 
} 
```

### Insertion Sort

在第p步，保证前p个元素是顺序的。

```
void InsertSort(int A[], int N) { 
    int j, P; int Tmp; 
    for(P=1; P<N; P++) { 
        Tmp = A[P]; 
        for(j=P; (j>0)&&(A[j-1]>Tmp); j--){ 
            A[j] = A[j-1]; 
        } 
        A[j] = Tmp; 
    } 
}
```

$O(N^2)$

Binary Insert Sort 

---

**Adjacent Swap**

---

### Shell Sort

increment sequence. k从大到小直到1，每次 $h_k$-$sort$ 都用insertion sort. 

A popular but poor choice of increment sequence: $h_k = \frac{1}{2}h_{k+1}$

```
void ShellSort(int A[], int N) {  
    int i, j, Increment; 
    int Tmp; 
    for(Increment=N/2; Increment>0; Increment=Increment/2) {  
        for(i=Increment; i<N; i++) {  
            Tmp = A[i]; 
            for(j=i; j>=Increment; j=j-Increment) {  
                if(Tmp<A[j–Increment]) 
                    A[j]=A[j-Increment]; 
                else 
                    break; 
            } 
            A[j] = Tmp; 
        } 
    } 
}
```

### Merge Sort

recursively merge-sort the first half and second half. divide-and-conquer. 

time: $O(NlogN)$, space: $O(N)$

### Quick Sort

time: $O(NlogN)$, space: $O(1)$

It's important to pick a suitable pivot v. A safe course is merely to choose the pivot RANDOMLY, but has extra cost. 

picking three elements randomly and using the median of the three as pivot

### Table Sort

只交换编号，不交换数据，因为数据比较大。

rearrange the data

---

**Pairwise comparison**

---

### Bucket Sort

需要已知取值范围。建一个范围大小的数组，然后往里填数 O(N)

### Radix Sort

从个位开始每个位数都 Bucket Sort

### External Sorting

### Pancake Sort

### Topological Sort

## Hashing

### Hash Function

mod(key, TableSize)

### Collision resolutions

#### Seperate Chaining

重复的存成list

#### Open Addressing

如果碰到collision，就找下一个空着的填上。

- Linear Probing
- Quadratic Probing
- Double Hashing

#### Rehashing

If the current hash table gets too full, build another table that is normally about twice as big and scan the original hash table and insert to the new table

#### Public Overflow Cache

If a collision occurs, then put the newly collided element into an extra overflow table. 


---

[Back to top](#数据结构与算法)
