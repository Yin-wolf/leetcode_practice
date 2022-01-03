# Time Complexity

## Understanding by code

**Example 1**: For Loop

In all the cases below the TC will O(n)

```c++
for(i = 0, i < n, i++){
    // statement will be executed n times
    // Here the TC will be O(n)
}
```

```c++
for(i = n, i > 0, i--){
    // statement will be executed n times
    // Here the TC will be O(n)
}
```

```c++
for(i = 0, i < n, i += x){
    // statement will be executed n/x times 
    // Here the TC will be O(n)
}
```

**Example 2**: Nested For Loop type 1

In the case below the TC will O(n^2)

```c++
for(i = 0, i < n, i++){ // n + 1
    for(j = 0, j < n, j++){ // n (n+1)
    // statement will be executed n * n times
    // Here the TC will be O(n^2)
    }
}
```

**Example 3**: Nested For Loop type 2

In the case below the TC will O(n^2)

```c++
for(i = 0, i < n, i++){ // [0,1,2,...,n]
    for(j = 0, j < i, j++){ // [null,(0,1[null]),(0,1,2[null]),..., n - 1]
    // statement will be executed (n^2 + 1)/2 times
    // Here the TC will be O(n^2)
    }
}
```

**Example 4**: Nested For Loop type 3

In the case below the TC will O(root(n))

```c++
p = 0

for(i = 1, p < n, i++){ // this will continue till k
    p = p + i; // the loop will stop when p > n, hence p = k(k+1)/2 > n. This means k^2 > n => k = root(n)
}
```

**Example 5**: Nested For Loop type 4

In the case below the TC will O(log(n)base2)

```c++
for(i = 1, i < n, i * 2){ // In every iteration, i increases by power of 2.. 2^k times
    // Statement execution will stop when i >= n, hence 2^k >= n => k = log(n)base2
}
```

**Example 6**: Nested For Loop type 5

In the case below the TC will O(log(n)base2)

```c++
for(i = n, i >= 1, i = i / 2){ // In every iteration, n value decreases by (n/2^k)
    // Statement execution will stop when i < 1>, hence n/(2^k) = 1 => k = log(n) base 2
}
```

**Example 7**: Nested For Loop type 6

In the case below the TC will O(log(n)base2)

```c++
for(i = 0, i*i < n, i++){ // In every iteration, i*i happens
    // Statement execution will stop when i*i >= n, i^2 = n, i = root(n)
}
```
