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
- Fundamental: https://www.cs.rutgers.edu/~pxk/416/

## Tell me about your self.

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

in the best case all the element is equal -> O(n)

in the wost case the array is sorted -> O(n2)

average O(n Log n)

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

[Operating system three easy peieces](http://pages.cs.wisc.edu/~remzi/OSTEP/)


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

**When some data can not fit into the memory it will need to access disk which is the slowest part of a mordern computer**

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


> TCP proxy
[How to build a TCP proxy](https://robertheaton.com/2018/08/31/how-to-build-a-tcp-proxy-1/)

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

> [symmetric-vs-asymmetric-encryption-what-are-differences](https://www.ssl2buy.com/wiki/symmetric-vs-asymmetric-encryption-what-are-differences)

> `List out some symetric cryptography algorithms`

> `List out some asymetric cryptography algorithms`

> `What is public key cryptography?`

> `How is JWT?`

> `Server to server authentication?`

### HTTPS

> `How https works ?` **[important]**

> `Describe SSL/TLS handshake` **[important]**

After building a TCP connection, the client started the handshake with sending information like SSL version, cipher suites, and compression method.
The server then checks for the highest SSL version that is supported by both of them.
The server also chooses the compression method and the cipher suite from the client’s option.
After this exchange, the server sends a certificate (public key) to the client.
The client confirms the certificate, creates pre-master secret for the session, and encrypts the session with the server’s public key.
The server receives pre-master secret and decrypt it with the private key.
Both parties agree on a single cipher suite and generate the session keys (symmetric keys) to encrypt and decrypt the information during an SSL session.
Finally, both client and server exchanges encrypted message to ensure that the future messages will be encrypted.

> `how certificate was issue ?` **[important]**

`Server, domain information, issuer, expire time  + hash algorithm => hash data `

`hash data + private key of CA => signature`

sinature + server, domain information, issuer, expire time + server public key  tạo thành TLS/SSL certificate

> `Explain how ssl certificate signature was verified` **[important]**

When brower receive ssl cert, it know who is the issuer then it will use the public key of issuer which is already installed in browser

it do the hash again:

`Server, domain information, issuer, expire time  + hash algorithm => hash data`

`public key + signature => hash data `

if 2 hash data is matched then the certificate is verified.


> `Explain how certificate authority chain work?` **[important]**

if cert is not issued by root CA but the intemediate CA. Then the verify process will continue with that intemediate certificate.
If the verify process can go all the way to the root CA then the cerificate is verified.


> [What happend under the hood when you type google.com in your browser](https://stackoverflow.com/a/42154314/2803909)

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

> Note to utilize mysql index
- Column must be isolation, it mean that the column must not be part of an expression or be inside a function call in query
- Prefix index and selective index: the good thing is to choose the long enough to give good selective and short enough to use less space
- Selective = cardinality / row -> the greater selective the better to chose (choose the prefix give the selective closest to the selective of using full column)
- Selective of unique index is 1 -> it is very good
- key and index in mysql is the same



### Replica
> Properties of replica?
- Many replicas can connect to a single master and stay in sync with it, and a
replica can, in turn, act as a master.
- Newer replica can sync data from old master but not in the opposite direction.
- too many replica is not good because too much data duplicated needlessly.

> How replica can help?
- Data distribution
- Load balancing
- Backups
- High availability and failover
- Testing MySQL upgrade

> How replica works?
- Master records changes to it binary log 
- Replica copies the master binary log to it relay log
- The replica replay the event in the relay log, applying change to its own data.
- The logging process happened right before the database tell the engine to commit the transaction.

> How many way to implement replica?
- Statement replica and row base replica

### Sharding

> `What is sharding? `

Sharding is the process of breaking up large tables into smaller chunks called shards that are 
spread across multiple server.

> Pros and cons ?

Can easier to scale and scale more efficiently. 
Network of smaller and cheaper server is more cost effective than single big server in long term. 
Sharding can increase total cluster storage capacity, speed up processing, and offer higher avalability at lower cost.

Database does not support so we need to implement it in application layer. Application must have additional sharding logic to
know exactly where data located and how to fetch it.
Manage are more complicated. Now any action on database like backup, restore, alter schema, migration must be carefully coordinate to ensure all shard have the same copy.

> All sharding architecture:

**Hash-based sharding**

**Range-based sharding**

**Geo-based sharding**

> `How to implement sharding in MySQL?` 

### Partition

> `What is database partition?`

> `Sample partition database in MySQL?`

### Database engine

> `MyISAM vs InoDB ?` **[important]**

### Scale MySQL 

> `How to scale MySQL?`
- dont have time and dev then buy more hardware.
- optimize performance: enable slow query log and then analyze it to optimize.

### SQL
- [SQL](./database/sql.md)
- [Order of execution in SQL query](https://www.sisense.com/blog/sql-query-order-of-operations/) **[important]**
- LEFT JOIN
- RIGHT JOIN
- INNER JOIN
- CASE WHEN


> `HAVING VS WHERE ?`
Having work on aggregate data while where not, 
```
SELECT SalesOrderID,
         SUM(UnitPrice* OrderQty) AS TotalPrice
FROM     Sales.SalesOrderDetail
GROUP BY SalesOrderID
HAVING   TotalPrice > 5000 
```
In the above query, HAVING can see TotalPrice while WHERE can not do that

> `Multiple aggregation in single SQL query ?`

> `Join multiple table`
```
select s.name "Student", c.name "Course"
from student s, bridge b, course c
where b.sid = s.sid and b.cid = c.cid 
```

```
SELECT s.name as Student, c.name as Course 
FROM student s
    INNER JOIN bridge b ON s.id = b.sid
    INNER JOIN course c ON b.cid  = c.id 
ORDER BY s.name 
```

- `Complexity of SQL query`

### Advanced MySQL

> `MySQL Query cached?` 
> `Partition`
> `Store code inside MySQL`
> `Fulltext searching`
> `Optimize SQL query`

- Dont use select * , only select neccessary field
- Dont use where to join, use inner join specificly
-

### Replication

> `Setup replicate`
> `Replicate under the hood`

### Scale MySQL - replicate, partitioning, sharding

> `Scaling Up`
> `Scaling out`
- Functional partitioning
- Data sharding
- Choose a partition key
- Multiple partition key
- Query accross shards


### Concept
- [ ] Describe database master slave process
- [ ] `Describe ACID` **[important]**
- [ ] first, second, third nomalization
- [ ] `explain how index in Database work` **[important]**
- [ ] partitions database
- [ ] shared lock/exclusive lock
- [ ] isolation
- [ ] dirty/non-repeatable reads
- [ ] `clustered index, primary index, unique index` **[important]**
- [ ] `composite index and how they was implemented` **[important]**
```
MySQL allow you to create index on multiple columns, up to 16 columns. 
This index is call composite index

MySQL create composite index by concat value of column in the order of column in index and then use it as key

Beside of using multiple column index you can add an extra column as long as that column is short, reasonably unique and be indexed

`
SELECT * FROM tbl_name
  WHERE hash_col=MD5(CONCAT(val1,val2))
    AND col1=val1 AND col2=val2;
`
```

## Software design

> Docs

- https://www.freecodecamp.org/news/how-to-system-design-dda63ed27e26/
- https://engineering.linkedin.com/distributed-systems/log-what-every-software-engineer-should-know-about-real-time-datas-unifying
- https://www.educative.io/courses/grokking-the-system-design-interview/3j6NnJrpp5p
- https://github.com/donnemartin/system-design-primer
- https://www.quora.com/What-are-the-best-resources-to-learn-how-to-build-scalable-large-software-systems

- [ ] API design

> `System high performance`
**is similary to how fast a car.**

> `System scalability: `
**System scalability is the ability to grow system capacity by add more resource.**
Poor scalability system will rich the limit point and can grow further.

**System scalability is the degree to which you can add more cars and more lands with out slowing the traffic.**

> `System capabilities`
The system's capability is the ammount of work system can perform in a given amount of time. 
System maximum throughput is not the system's capacity. The actual system capacity is 
the throughput system can achieve while still delivering acceptable performance.

**System capacity = number of lanes * maximum safe speed**

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


> How to ensure your final round interview lands you the job ?

- The hiring manager does not make the final round interview invitation for the fun of it.
- The final round interview is to either gauge your cultural fit with the team or compare you with another qualified finalist. 
- You can't rely on people to make the right assumption about you, so it would be better for you to speak it out for them. ( but not too much )
- You should show that you are very self awareness. You acknowledge your weakness and showing the concrete steps you have taken to bridge the gap.
- Don't be afraid to ask questions.
- In conclusion, final round interview is about balance: your strength and your weakness, asking and answering question, personality and profesionalism.

> Question to ask interviewer in the interview

- These questions are to show the level of your interest in the job, how much research you have done about the role and the organization.
- The question in the final round interview should show your in-depth knowledge of the industy, the role, the orgainization. So your question should reflect this high level of preparedness and research.


> Some sample question to ask in the final round interview 

- What kind of person do you think makes the ideal colleague here? 
  => show the interviewer that you already concern about being a good fit into the team.
  => give you an opertunities to reiterate about your personality, character trait, soft skill that make you not just an acceptable employee who can get the job done but a pleasant coworker who the other team members will
     look forward to spending time with every day.

- What is the onboarding process look like?

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
21. **Subtract a by b** trừ a cho b
22. **n(n+1)/2** n time n plus 1 over 2
23. **Cartesian product** Tích đề các
24. **What do we need to power 2 by to get 16?** 
25. **I will get into doing something**
26. Hello, can you here me? can you here me very well?
27. So do I, So is it, So is she, Me too 
28. Sorry, I just don't get it.
29. In the case the array is sorted then in each iteration of quicksort the array only shrink by 1 element 
30. Using where to join will create cartesian product or cross join -> all possible combinations of variables are created. 
