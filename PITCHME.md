@snap[midpoint text-center]
## Database Concepts 
####  A Historical Perspective
@snapend

Note:
 - https://gitpitch.com/kk-sw/database-concepts/master?grs=github&t=moon#/

---

### Historical Databases (No Database)

- All data is stored in memory
- It's a start

✔ Fast

✔ Store anything in any format

✖ No persistent and durable storage

  
---

### Historical Databases (Flat File)

  ```text
  Ted Scott ▫ $100 ▫ Apple ☷ Ai Joe ▫ $900 ▫ Peach ☷
  ◺      ◿  │              │
    field   │              │
    value   │              └─ record separator   
            └─ field separator
  ```

✔ Persistent

✔ Store anything (records can be different)

✖ Low-level access, programmer needed

✖ Complex queries are hard and slow

Note:
 - Still used for small data sets in some domains
 - Explain indexing
 
---

### Historical Databases (Hierarchical)

  ```text
         CTO
        ╱   ╲
      Head1 Head2 
     ╱    ╲
   Mngr1  Mngr2    
  ``` 

✔ Defined structure?

✔ Faster than flat file??

✖ Navigation through the hierarchy only

✖ Inability to support ad hoc queries

Note:
 - It's logical model
 - Actual disk storage is different
 
---

### Historical Databases (Navigational)

  ```text
  John    ──  Alice ── Maggie   Rob 
   │           │        │        │
  Richard ──  Scott    Susie ── Nancy
  ``` 

✔ Relaxed navigation 

✔ Very fast 

✖ Still pre-determined navigation (rigid schema)

✖ Inability to support ad hoc queries

Note:
- Still used
- http://wiki.c2.com/?NetworkDatabase
- https://stackoverflow.com/questions/3422221/what-exactly-is-the-problem-with-hierarchal-and-network-models-of-databases

---

### Relational (RDBMS) Databases 

@ul
- E. F. Codd in 1970 (IBM)
- Relational model of data  
- User friendly (SQL)
- Based on formal rules (math)
    - Optimal database design (NF)
    - Data access optimization
- Very popular
- MySQL, Oracle, MS SQL, Sybase, etc.

@ulend

---

### RDBMS Concepts

- Database = tables + table cross-reference + indexes

![SQL Conc](img/db1.png)

---

### Structured Query Language (SQL)

@ul
- Structured Query Language (SQL)
- ANSI Standard
- Declarative language

@ulend

---

### Structured Query Language Examples

@ul
- Create table
    - CREATE TABLE families (f_name char, s_name char, child_count int);
- Query for data
    - SELECT f_name, s_name FROM families WHERE child_count > 2;
- Modify existing data
    - UPDATE families SET f_name="Jonas" WHERE s_name = "Jhn"
- Insert new data
    - INSERT INTO families VALUES ("Philip", "Zimmer", 3);

@ulend

---

### ACID (Transaction Control)

@ul
- What to see and when
- Isolation of the operations at the same time !!!!!!!!!!
- ACID (transaction control)
    - Atomic:       All operations in a transaction succeed or every operation is rolled back.
    - Consistent:   On the completion of a transaction, the database is structurally sound.  
    - Isolated:     Transactions do not contend with one another. 
    - Durable:      The results of applying a transaction are permanent, even in the presence of failures.
- 4 levels of ACID
    - Speed vs trust

@ulend

---

### RDBMS Drawbacks

@ul
- 
- Cost
@ulend

Note:
 - Column stores







---



### NoSQL Databases  

@ul
- No predefined schema/structure 
    - Store anything
- Non-trivial queries are hard
- Model database based on the proposed usage
    - Need to know what to use for     
- Performance

@ulend

---

### CAP Theorem  

@ul
- CAP theorem (Reliability)
  - Consistency: Every read receives the most recent write or an error
  - Availability: Every request receives a (non-error) response with some (even old) data
  - Partition tolerance: operate when network is not reliable
- Choose two
- Most system support multiple CAP modes

@ulend
  
---

### NoSQL Databases (Historical) 

- XML Database
- Object Store
  
---
  
### NoSQL Databases (Key-Value)  

    ```text
        123 : { f_name = "Arthur", s_name = "Legend" }
        ... : ...
    ```

✔ Very Fast

✔ Simple to use

✖ Access by keys

✖ 
    
---
  
### NoSQL Databases (Document)  

- xxx
    ```text
    Example
    ```
- Products

✔ 

✔ 

✖ 

✖ 

---
  
### NoSQL Databases (Wide Column)  

- xxx
    ```text
    Example
    ```
- Products

✔ 

✔ 

✖ 

✖ 

---
  
### NoSQL Databases (Graph)  

- xxx
    ```text
    Example
    ```
- Products

✔ 

✔ 

✖ 

✖ 

---
  
### NoSQL Databases (Time)  

- xxx
    ```text
    Example
    ```
- Products

✔ 

✔ 

✖ 

✖ 


---

### NoSql Drawbacks

@ul
- 
- 
@ulend
  
---
  
### Future Directions  

@ul  
- NewSQL     (SQL ↔ NoSQL convergence)
- MAU        (commodity hardware)
- NIC/RDMA   (cross memory access)
- RAM store  (very fast) 
- FPGA       (custom hardware)
@ulend

Note:
 - https://blog.acolyer.org/2017/11/23/kv-direct-high-performance-in-memory-key-value-store-with-programmable-nic/
 - RDMA – Remote Direct Memory Access



 
---

@snap[midpoint text-center]
#### Use whatever is the best for the given problem 
@snapend

Note:
- Sql + NoSQL
- Caches

---

@snap[midpoint text-center]
## Thank You
#### Questions? 
@snapend
