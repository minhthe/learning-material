##### Heap sort
1. Steps:
- build max-heap
- add A\[0] to the sorted array
- swap(A\[0], A\[n])
- n--;
- max_heapify()
- return to step 2
2. Runtime: O(nlogn). Space: O(1)
3. - Fast worst case, efficient space usage
   - Comparison based
   - Unstable
   
##### Counting sort
1. Integer sorting algorithm
2. Steps:
- build C\[A\[i]] = number of value A\[i] in A
- C\[i] += C\[i-1]
- 
```cpp
    for(int i = n-1; i >= 0; i--) {
        C[A[i]]--;
        B[C[A[i]] = A[i];
    }
```
3. Runtime: O(k+n). Space: O(k)

##### Insertion sort
1. Best case O(n), worst case O(n^2)
2. Best for mostly sorted list
3. At each step, sublist \[0..i-1] is sorted, we insert \A[i] to this sorted list

##### Selection sort
1. At each step, choose the smallest item in unsorted list and move to
sorted list
2. O(n^2)
3. Make max O(n) swap

##### Quicksort
1. Device and Conquer
```cpp
int partition(vector<int> &a, int low, int high) {
    int pivot = low + rand() % (high -low);
    swap(a[high], a[pivot]);
    int pivotValue = a[high];
    int i = low - 1;
    for(int j = low; j < high; j++)
        if (a[j] <= pivotValue) {
            i++;
            swap(a[j], a[i]);
        }
    swap(a[i+1], a[high]);
    return i+1;
}

void qsort(vector<int> &a, int low, int high) {
    if (low < high) {
        int p = partition(a, low, high);
        qsort(a, low, p-1);
        qsort(a, p+1, high);
    }
}
```
2. Best case O(nlogn), worst case O(n^2)
