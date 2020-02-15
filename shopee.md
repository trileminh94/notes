# table of contents
1. [Datastructure and algorithm](#Datastructure-and-algorithm)
2. [Operating system](#Operating-system)
3. [Networking](#Networking)
4. [Web security](#Web-security)
5. [Technology](#Technology)
6. [OOP](#OOP)
7. [Database](#Database)
8. [Software design](#Software-design)
9. [Behavieral](#Behavieral)
10. [Common phrases use to answer common question](#Common-phrases-use-to-answer-common-question)

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
- device and conquer
- `dynamic programming` **[important]**
```
1. recursion
2. store (memoize)
3. bottom-up

time comlexity is O(M * N)
space complexity can be O(M * N) or O(M) if we use a single demension array instead of 2 demension arrays
```
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

### Process
- [ ] `process` **[important]**
- [ ] `schedule process ( mutex, semaphore)` **[important]**

### Thread
- [ ] `thread` **[important]**
- [ ] schedule thread
- [ ] context switch

### Memory management
- [ ] `virtual memory` **[important]**
- [ ] `Little and big endian`

### File system
- [ ] file system

## Networking

- [ ] how the intenet work

### IP - internet protocol

- [ ] how IP work
- [ ] properties of IP protocol

```
1. Best effort service
2. Unreliable
3. do not garantee datagram delivery
4. do not garantee the integrity of datagram
```

### TCP
refer 
1. https://www.homenethowto.com/
2. [TCP](./networking/transport_layer/tcp.md)

> `how TCP work` **[important]**
> `structure of headers`
> `properties of connections (*)`

TCP connection is not in the intermediate network element, it is only in the two end systems
TCP connection is full-duplex connection. Data send back and ford on the same connections.
TCP connection is point to point connection, not multiple cast.



> `TCP handshake - three-way handshake` **[important]**

1. they must send some preliminary


> `Sending data process`

Client process pass a stream of data through the socket.
Once data pass through the socket, TCP will direct that data stream to the
connection's send buffer. 
TCP will grab chunks of data from the send buffer and pass data to the network layer. 
MSS - maximum segment size
MSS was set by first determining the length of the largest link-layer (MTU maximum transmission unit)

TCP grab each chunk of client data with TCP header to form TCP segment and pass down to the network layer. 
Network layer will seperate and ecapsulate TCP segment to IP Datagram.


- [ ] TCP proxy
- [ ] `terminate connections`
- [ ] `TCP congestion control` **[important]**
- [ ] `TCP flow control` **[important]**
- [ ] `TCP timer, TCP timeout and retransmition` **[important]**
- [ ] `Estimate the right round-trip time (RTT)` 

### UDP
- [ ] how UDP work 

### HTTP

## Web security

- [ ] how https works
- [ ] how to defend DDOS

### Cryptography

> `How to store password in database?`

Store hash instead of raw password, don't use MD5, use Bcrypt. Careful about SQL injection.

> `What is RSA algorithm?`
> `What is AES algorithm?`
> `Symetric vs asymetric cryptography algorithm`

1.[Ref](https://www.ssl2buy.com/wiki/symmetric-vs-asymmetric-encryption-what-are-differences)

> `List out some symetric cryptography algorithms`
> `List out some asymetric cryptography algorithms`
> `What is public key cryptography?`
> `How is JWT?`
> `Server to server authentication?`

### HTTPS

- [ ] `How https works ?` **[important]**
- [ ] `Describe SSL/TLS handshake` **[important]**
- [ ] `Explain how certificate authority chain work?` **[important]**
- [ ] `how certificate was issue ?` **[important]**
- [ ] [What happend under the hood when you type google.com in your browser](https://stackoverflow.com/a/42154314/2803909)

### HTTP2

- [ ] `what is http2?` **[important]**

## Technology

### GRPC and thrift protocol

- [ ] `How do you use GRPC?` **[important]**
- [ ] `Load balance`
- [ ] `Connection pool`
- [ ] `Thrift vs GRPC` **[important]**

### Kubernetes

- [ ] `Describe k8s components ?` **[important]**

### Kafka

- [ ] `Explain kafka ?` **[important]**

### NIO

- [ ] `What is NIO and event loop?` **[important]**

### Scribe log and data pipeline

> `How scribe log works?`

> `What is data pipeline?`

> `Describe zalo log data pipeline?`

## OOP

-[ ] [Explain SOLID ](https://itnext.io/solid-principles-explanation-and-examples-715b975dcad4) **[important]**

S: Single responsibility

O: Open close principles - open for extension and close for modification

L: Liskov substitution principle - replace instance of parent type by 
instance of child type without altering **the correctness of the program**

I: Interface segregation principle - no client should be forced to depend on methods it does not use.

D: Dependency inversion - High level should not depend on low level modules. Both depend on abstractions, Abstractions should not depend on details. Details should depend on abstractions.

**By applying these SOLID principles, we get to benefit from a reusable, maintainable, scalable and easy testable codebase.**


## Database

### order of execution

- https://www.sisense.com/blog/sql-query-order-of-operations/

### Indexing

- [] https://www.freecodecamp.org/news/database-indexing-at-a-glance-bb50809d48bd/

### Sharding

> `What is sharding? `

> `How to implement sharding in MySQL?` 

### Partition

> `What is database partition?`

> `Sample partition database in MySQL?`

### Database engine

> `MyISAM vs InoDB ?` **[important]**

### SQL
- [SQL](./database/sql.md)
- [Order of execution in SQL query](https://www.sisense.com/blog/sql-query-order-of-operations/) **[important]**
- LEFT JOIN
- RIGHT JOIN
- INNER JOIN
- CASE WHEN
- `Complexity of SQL query`

### Concept
- [ ] Describe database master slave process
- [ ] `Describe ACID` **[important]**
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
3. If you create an index in col1 and composite index in col1, col2 then only the composite index should be fine. Col1 alone can be serve by composite index itself since it's a left side prefix  of the index.   
4. Odd: lẻ - even : chẵn
5. perform such action any number of time
6. `In the first iteration` 
7. Coin denomination : menh gia dong xu
8. How many different ways you can get this value if you only have ..... ? 
9. Similary, this will be ..... , this will be ...... , ....  ( dung de noi tuong tu cho nhung gia tri khac thi co ket qua)
10. Basicly, Fundamentaly
11. Let's introduce 2 to the picture ( truong hop dynamic programming, xet toi dong tiep theo)
12. 4 can be represented as 4 it self or 3 + 1 or 2 + 2 or 2 + 1 + 1 or the addition of 4 number 1 
13. Number of way to represent an integer number as addition of positive integers
14. If I have the ammount of 5 and I need to make change for. If I only have 1 2 5 coins, how many unique ways to do that?
15. If the total is zero then no matter how many coins you gave me, I am going to be able to make changes 1 way which is nothing.
16. I subtract one from here and I go here
17. There are 4 ways to make change for 5 given the coins 1 2 and 5
18. `This is accomplished as follows` - no duoc thuc hien nhu sau
19. This is but one simple example of how to correct a violation of this principle, however, this situation can manifest in a broad variety of ways, and is not always easy to identify.
20. **Either of the two processes participating in a tcp connection can end the connection.**

