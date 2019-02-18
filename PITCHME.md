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
  ◺      ◿ │              │
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

✔ Defined structure

✔ Faster than flat file

✖ Navigation through the hierarchy only (up-down)

✖ "Programmer perspective" needed

Note:
 - ~1960s
 - It's logical model
 - Actual disk storage is different
 - Domain databases: LDAP, Active Directory

---

### Historical Databases (Navigational)

  ```text
  John    ──  Alice ── Maggie   Rob
   │           │        │        │
  Richard ──  Scott    Susie ── Nancy
  ```

✔ Relaxed navigation

✔ Very fast

✖ Still pre-determined navigation (no ad hoc queries)

✖ "Programmer perspective" needed

Note:
- Still used - IBM Information Management System 1966 - v15 (2017)
- http://wiki.c2.com/?NetworkDatabase
- https://stackoverflow.com/questions/3422221/what-exactly-is-the-problem-with-hierarchal-and-network-models-of-databases
- NoSql relation

---

### Relational (RDBMS) Databases

@ul
- E. F. Codd in 1970 (IBM)
- Relational model of data
- Based on formal (math) rules
    - Optimal database design (NF)
    - Data access optimization
- User friendly
- Very popular
- MySQL, Oracle, MS SQL, Sybase, MS Access, etc.

@ulend

Note:
 - User friendly as abstractions and SQL

---

### RDBMS Concepts (Table)

- Database = tables + table cross-reference + keys

![SQL](img/db1.png)

---

### RDBMS Concepts (Keys)

- Primary Key (PK) is an unique identifier for an entity
- Keys are needed to make relations

![SQL](img/db2.png)

---

### Structured Query Language (SQL)

@ul
- SQL = Structured Query Language
- ANSI Standard
- Declarative language
    - Focus on what to do, not how to do
- User friendly
    - Abstractions for non-programmers
    - English like language
- Pure SQL applications (MS Access)
    - Not fancy, but no programming needed

@ulend

---

### Structured Query Language Examples (Table)

- Create table
    - CREATE TABLE families (f_name char, s_name char, child_count int);
- Delete table
    - DROP TABLE families;

Note:
 - Drop table = NoSql :)

---

### Structured Query Language Examples (Data)

- Insert new data
    - INSERT INTO families VALUES ("Philip", "Zimmer", 3);
- Query for data
    - SELECT f_name, s_name FROM families WHERE child_count > 2;
- Modify existing data
    - UPDATE families SET f_name="Jonas" WHERE s_name = "Jhn"

---

### ACID (Transaction Control)

@ul
- Who sees what changes and when
- Transaction = operations in a bundle
- ACID (transaction control)
    - Atomic:       Operations succeed or roll-back (state before)
    - Consistent:   Database is in correct state when trans. finished
    - Isolated:     Transactions do not disturb/effect another
    - Durable:      Results are permanent, even if error'd
- 4 ACID levels
    - Speed vs consistency

@ulend

Note:
- Transaction with one operation
- Automatic ACID modes

---

### RDBMS Drawbacks

![Arch](img/client-server-db.png)

@ul
- Scaling is hard (ACID)
    - Expensive
    - 'Free' solutions are not mature for 9...9%
    - Synchronization penalty
- Non-structured data is hard to store
    - NoSql for rescue
- For majority of uses SQL is just enough

@ulend

Note:
 - ACID -> math -> need to synchronize to guarantee correctness
 - Column stores

















---





### NoSQL Databases

@ul
- Schema/structure definition is optional 
    - Store anything 
    - Mix data w/i collections
- Non-trivial queries are hard
    - Model database based on the proposed usage
    - Need to know what to use for
- Performance
    - Very good for expected use cases
    - Bad for unexpected use cases
- Networked systems    

@ulend

Note:
 - Store mixed data within 'table'
 - Navigational database (history)

---

### CAP Theorem

@ul
- Eric Brewer (~1997)
- CAP theorem (Reliability)
  - Consistency:         A read receives the most recent data or an error
  - Availability:        A request receives a (non-error) response with (old) data
  - Partition tolerance: System operates when network is not reliable
- Choose two
- Most systems support configurable CAP modes

@ulend

---

### NoSQL Databases (Historical)

- XML Database
    - Wasteland
- Object Store
    - Programmer's database

Note:
 - XML - noman's land 
 - Object store

---

### NoSQL Databases (Key-Value)

  ```text
        123  ↠ firstName = "Arthur" ⌁ surName = "Legend" 
        8874 ↠ color = "Black       ⌁ make = "Ford"
          . . . 
  ```

✔ Very Fast

✔ Simple to use

✖ Access by keys

✖

Note:
 - caches
 - Mix storage
 
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
- Operational Expertise
- Network
- Multiple servers
- 

@ulend

---

### NoSql and RDBMS

  Term      |  NoSql     | RDBMS      
------------|------------|------------
Consistency | Weak       | Strong
Performance | Varies     | Good
Language    | Custom     | SQL
DevOps      | Complex    | Simpler
Node Count  |  >3        |  1
Example     | DocStore   | HR app

---

@snap[midpoint text-center]

#### Use whatever is the best for the given problem

@snapend

Note:
- Mix Sql and NoSQL

---

### Future Directions

- NewSQL     (SQL ↔ NoSQL convergence)

@ul
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

## Thank You
#### Questions?

@snapend
