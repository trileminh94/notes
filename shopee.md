# Topics

- reference: https://forthright48.com/interview-with-shopee-garena/

## Datastructure and algorithm

### Datastructure

- Array
- Linked List
- Double linked list
- Heap
```
- array based datastructure parent greater than its children
- construct: 
    + top down: add new element to array and up heap
    + bottom up: recursive to build sub heap and then join 2 heap by a node 
      and then down heap bubbling
- heap sort: 
    + in place heap sort: build heap in place and repeat swap the root to 
      the last element then down heap bubbling
```

- Binary tree
- Binary search tree
- Trie
- AVL Tree
- Stack
- Queue
- 2 Ended queue
- Graph
- Hashtable

#### sample question

- `Please build a data structure to cache results from SQL query `
- Binary tree traversal, inorder, iterative

### Algorithms `( time complexity for each )`
- bubble sort ( useful to find K largest or smallest element - modify to make outer loop run only k time)
```
for (i = n-1; i > 0; i--) {
    for (j = 0; j < i; j++) {
        if (arr[j] < arr[j+1]>) {
            swap
        }
    }
}
```
- insertion sort
```

for (i = 0; j < n; i++) {
    val = arr[i]
    for (j = i-1; j > 0; j--) {
        if arr[j] > val {
            arr[j+1] = arr[j]
        } else {
            arr[j+1] = val
            break;
        }
    }
}
```
- selection sort
```
seperate array into 2 part: sorted and unsorted
loop n time, each time find the smallest element in the unsorted part and then
move the seperator to the right one step
```
- quick sort
- merge sort
- heap sort
- Time and Space Complexity analysis

- `references: https://www.youtube.com/channel/UCNsGQ_oLlH89HoKd5uyoAEQ/videos`

#### sample question

```
 Step to do: 
    1. Clarify the requirements
    2. Do some sample 
    3. Suggest some solution from naive to optimal
    4. Analyze the pros, cons and complexity of each one
    5. Choose one algorithm
    6. Code
    7. Run by your self
    8. Find the way to improve performance
```

- Find k th most occured character
- Find square root of number without built in function.
- Implement linked list. Delete node with O(1).
- reverse a linked list
- verify a binary search tree
- given a list of number, find the first K minimum number

## Operating system
- [ ] `process` **[important]**
- [ ] `thread` **[important]**
- [ ] `schedule process ( mutex, semaphore)` **[important]**
- [ ] schedule thread
- [ ] context switch
- [ ] file system
- [ ] `virtual memory` **[important]**
- [ ] `Little and big endian`

## Networking

- [ ] how the intenet work

### IP - internet protocol

- [ ] how IP work

### TCP
refer https://www.homenethowto.com/

- [ ] `how TCP work` **[important]**
- [ ] `structure of headers`
- [ ] `properties of connections (*)`
- [ ] `TCP handshake` **[important]**
- [ ] TCP proxy
- [ ] `terminate connections`
- [ ] `TCP congestion control` **[important]**

### UDP
- [ ] how UDP work 

### HTTP

## Web security

- [ ] how https works
- [ ] how to defend DDOS
- [ ] `cryptography`
- [ ] ` how to store password `
```
Never store raw password, store hashed instead and use Bcrypt instead of md5
and careful about SQL injection
```

### HTTPS

- [ ] `how https works` **[important]**
- [ ] `SSL/TLS handshake` **[important]**

## Database

### SQL

- [Order of execution in SQL query](https://www.sisense.com/blog/sql-query-order-of-operations/) **[important]**
- LEFT JOIN
- RIGHT JOIN
- INNER JOIN
- CASE WHEN
- `Complexity of SQL query`

### Concept
- [ ] Describe database master slave process
- [ ] ACID
- [ ] first, second, third nomalization
- [ ] `explain how index in Database work` **[important]**
- [ ] partitions database
- [ ] shared lock/exclusive lock
- [ ] isolation
- [ ] dirty/non-repeatable reads
- [ ] `clustered index, primary index, unique index` ***[important]**
- [ ] `composite index and how they was implemented` **[important]**
```
MySQL allow you to create index on multiple columns, up to 16 columns. 
This index is call composite index
```

## Software design
- [ ] API design

## Behavieral
- [ ] `talk about your career ( who do you want to be in the next 5 years at shopee ? )`
- [ ] Why do you choose shopee?
- [ ] Tell me the reason you leave your previous company
- [ ] your expectation to work in shopee
- [ ] tell me about project you learn the most
- [ ] what project you do, your role and contribution
- [ ] salary you expect (4000 SGD = 66.885.410 VND before tax)
- [ ] Do you have any question? 
- [ ] Describe the hard problem you faced and how you overcome?
- [ ] Do I have any experience?
- [ ] When did I start programming?
- [ ] Did I ever interview at any other company? I told him about Google and WAP.
- [ ] What will I do if Google suddenly asks me to join them? Will I leave Garena?
- [ ] What is my opinion about overtime work?
- [ ] What is my opinion about meetings?
- [ ] What is my expected salary?
- [ ] What is my opinion about the interview process?
- [ ] Do I know what Garena does?
- [ ] Why do I want to work here?


## Common phrases use to answer common question

1. Index will benefit your query
2. You can analyze different use cases of your sytem and try to come up with the order of columns that benefit most of your use cases.     



