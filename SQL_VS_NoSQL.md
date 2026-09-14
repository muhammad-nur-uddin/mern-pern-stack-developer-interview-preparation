<h1 align="center">Database Interview Questions</h1>

## 🎯 Database Fundamentals

## Q01. What is a database and why is it necessary?

A database is a system used to store, organize, manage, and retrieve data for an application.

A database is necessary because applications need to store different types of data, such as users, products, orders, and payments. We also need to create, read, update, and delete this data when required.

A database keeps the data persistent, makes it easier to manage, and allows multiple users or applications to work with the data. That is why a database is an important part of most real-world applications.

## Q02. What is a DBMS?

DBMS stands for Database Management System. It is a software system that is used to store, manage, retrieve, and update data in a database.

It works between the application and the database. When an application wants to read, insert, update, or delete data, the DBMS handles these operations.

A DBMS also helps with data security, data consistency, and managing access for multiple users.

## Q03. What is the difference between DBMS and RDBMS?

DBMS is a software system that is used to store and manage data in a database. RDBMS is a type of DBMS that stores data using related tables.

In an RDBMS, we can create relationships between tables and use features such as primary keys, foreign keys, and constraints.

So, the main difference is that DBMS is a general concept, while RDBMS is a specific type of DBMS that follows the relational model.

## Q04. What are the different types of DBMS?

There are different types of DBMS based on how they organize and store data. The main types are Hierarchical DBMS, Network DBMS, Relational DBMS or RDBMS, Object-Oriented DBMS, and NoSQL DBMS.

An RDBMS stores data in tables and allows relationships between those tables. A NoSQL database can use different data models, such as documents, key-value pairs, wide-columns, or graphs.

For example, MySQL and PostgreSQL are RDBMS databases, while MongoDB is a document-based NoSQL database.

## Q05. What is a table in DBMS?

A table is a structure in a relational database that stores data in rows and columns.

A column represents a specific type of data, such as a name, email, or age. A row represents one complete record in the table.

A relational database can have multiple tables, and we can create relationships between those tables when needed.

## Q06. What is data redundancy in a database?

For example, if a user's name and email are stored again and again with every order, the same user information is being duplicated.

This can use extra storage and make updates more difficult. If we update the data in one place but forget another place, it can cause data inconsistency. In relational databases, normalization is commonly used to reduce unnecessary data redundancy.

## Q07. What is the difference between SQL and NoSQL databases?

The main difference between SQL and NoSQL databases is how they store and organize data.

SQL databases are usually relational databases. They store data in tables with rows and columns, and we can create relationships between different tables. They usually use a structured schema.

NoSQL databases do not use the traditional relational table model. They can store data as documents, key-value pairs, graphs, or wide columns, and they usually provide a more flexible data structure.

PostgreSQL and MySQL are examples of SQL databases, while MongoDB and Redis are examples of NoSQL databases.

The choice between SQL and NoSQL depends on the application's data structure, relationships, consistency requirements, and scaling needs.

## Q08. Why are NoSQL databases popular today?

NoSQL databases are popular because they can provide flexible data structures and can work well for applications that need to scale.

Many NoSQL databases do not require a strict relational schema, so it can be easier to handle data when its structure changes. They can also support horizontal scaling, which is useful for applications with large amounts of data and high traffic.

Because of these features, NoSQL databases can be a good choice for some modern, real-time, and large-scale applications. However, it does not mean that NoSQL is always better than SQL. The choice depends on the requirements of the application.

## Q09. What are the different types of NoSQL databases?

There are four main types of NoSQL databases: Document, Key-Value, Wide-Column, and Graph databases.

A Document database stores data as documents, such as MongoDB. A Key-Value database stores data as key-value pairs, such as Redis. A Wide-Column database uses a column-based structure and is useful for large-scale distributed data, such as Cassandra. A Graph database stores data as nodes and relationships, such as Neo4j.

The right type depends on the data structure and requirements of the application.

## 🎯 Data Modeling & Normalization

## Q10. What is normalization in databases?

Normalization is the process of organizing data in a relational database to reduce unnecessary data duplication and improve data consistency.
We usually normalize a database by dividing a large table into smaller related tables and creating relationships between them.
This reduces repeated data, makes updates easier, and helps prevent data inconsistency. Common normal forms include 1NF, 2NF, and 3NF.

## Q11. What are the different normal forms?

There are several normal forms in database normalization, including 1NF, 2NF, 3NF, and BCNF.

First Normal Form, or 1NF, means that each column should contain atomic values, and each cell should contain a single value.

Second Normal Form, or 2NF, means the table is already in 1NF and there is no partial dependency on a part of a composite key.

Third Normal Form, or 3NF, means the table is already in 2NF and there is no transitive dependency between non-key attributes.

BCNF, or Boyce-Codd Normal Form, is a stricter version of 3NF where every determinant must be a candidate key.

The main purpose of these normal forms is to reduce unnecessary data duplication and prevent insert, update, and delete anomalies.

## Q12. What is denormalization?

Denormalization is the process of intentionally storing some duplicate or redundant data in a database to improve read performance and simplify queries.

In a normalized database, we reduce duplication and keep related data in separate tables. However, this can sometimes require multiple joins when reading data.

With denormalization, we may store some related data together so that common read queries can be faster or simpler. The trade-off is that it requires more storage and we need to keep the duplicated data consistent when it changes.

## Q13. What is the difference between ACID and BASE properties?

ACID and BASE are two different approaches to handling consistency and reliability in database systems.

ACID stands for Atomicity, Consistency, Isolation, and Durability. It provides strong guarantees for transactions and helps keep database operations reliable and predictable. For example, in a bank transfer, if one operation fails, the whole transaction can be rolled back.

BASE stands for Basically Available, Soft State, and Eventually Consistent. It is commonly used to describe distributed systems that focus more on availability and scalability. After an update, different replicas may temporarily have different data, but they can become consistent over time.

So, ACID focuses more on strong transaction guarantees, while BASE focuses more on availability, scalability, and eventual consistency in distributed systems.

## Q14. What are the ACID properties in DBMS?

ACID stands for Atomicity, Consistency, Isolation, and Durability. These are important properties of database transactions.

**Atomicity** means that a transaction is treated as one unit. Either all of its operations succeed, or the transaction is rolled back.

**Consistency** means that a transaction takes the database from one valid state to another valid state while following the defined rules and constraints.

**Isolation** means that concurrent transactions are properly isolated so that their intermediate changes do not cause incorrect results.

**Durability** means that once a transaction is committed, its changes are preserved even if the system crashes or fails.

## 🎯 Joins & Relationships

## Q15. What is an Entity-Relationship Diagram (ERD)?

An ERD, or Entity-Relationship Diagram, is a visual representation of a database structure and the relationships between different entities.

It shows entities, their attributes, and the relationships between them. It is mainly used during database design to plan which tables are needed, what fields they should contain, and how the tables are connected.

For example, one user can have many orders, so an ERD can show a one-to-many relationship between the User and Order entities.

## Q16. What are the different types of SQL joins?

SQL JOINs are used to retrieve related data from multiple tables.

The main types of SQL joins are **INNER JOIN, LEFT JOIN, RIGHT JOIN, FULL OUTER JOIN, CROSS JOIN, and SELF JOIN**.

An INNER JOIN returns only matching rows from both tables. A LEFT JOIN returns all rows from the left table and matching rows from the right table. A RIGHT JOIN does the opposite. A FULL OUTER JOIN returns all rows from both tables and uses NULL where there is no match. A CROSS JOIN returns every possible combination of rows from the two tables. A SELF JOIN joins a table with itself, which is useful for relationships such as employees and their managers.

## Q17. What is the difference between a Primary Key, Foreign Key, and Unique Key?

A **Primary Key** uniquely identifies each row in a table. Its values cannot be duplicated or NULL.

A **Foreign Key** is a column that references a Primary Key or a suitable Unique Key in another table. It is used to create relationships between tables and maintain referential integrity.

A **Unique Key** ensures that the values in a column or a combination of columns are not duplicated. Unlike a Primary Key, it is mainly used to enforce uniqueness and does not represent the main identity of the row.

For example, `users.id` can be a Primary Key, `orders.user_id` can be a Foreign Key, and `users.email` can be a Unique Key.

## Q18. What is a schema in DBMS?

A schema is the logical structure or blueprint of a database. It defines how the data is organized and what database objects are present.

It can define tables, columns, data types, relationships, keys, and constraints.

A schema does not represent the actual data. It defines the structure in which the actual data is stored.

For example, if a `users` table has `id`, `name`, and `email` columns, and `id` is the primary key, this structure is part of the database schema.

## Q19. What are constraints in DBMS?

Constraints are rules that a database uses to control the data stored in a table. They help maintain data accuracy, validity, and consistency.

Common constraints include **PRIMARY KEY, FOREIGN KEY, UNIQUE, NOT NULL, CHECK, and DEFAULT**.

A PRIMARY KEY uniquely identifies each row. A FOREIGN KEY maintains a relationship between tables. A UNIQUE constraint prevents duplicate values. NOT NULL ensures that a value must be provided, CHECK enforces a specific condition, and DEFAULT provides a value when no value is given.

## 🎯 SQL Query & Optimization

## Q20. What is a subquery in SQL?

A subquery is a SQL query written inside another SQL query.

We usually use a subquery when the result of one query is needed by another query.

For example, if we want to find employees whose salary is higher than the average salary, we can use a subquery to calculate the average salary first. Then the outer query can use that result to find the employees.

## Q21. What is the difference between DELETE, TRUNCATE, and DROP? in SQL?

DELETE removes rows from a table, and we can use a WHERE condition to remove specific rows. The table structure remains.

TRUNCATE removes all rows from a table, but the table structure remains. We cannot use a WHERE condition with TRUNCATE.

DROP removes the entire table from the database, including its data and structure.

In simple terms, DELETE removes rows, TRUNCATE removes all rows, and DROP removes the entire table.

## Q22. What is an index and what are its types?

An index is a data structure that helps a database find data faster.

When a column has an index, the database can usually use the index to find matching data instead of scanning the entire table or collection. This can make read and search queries faster.

Common types include single-column indexes, composite indexes, unique indexes, primary key indexes, and full-text indexes.

However, indexes also have a cost. They use extra storage, and the database needs to maintain them when data is inserted, updated, or deleted.

## Q23. What is the difference between a clustered and a non-clustered index?

The main difference between clustered and non-clustered indexes is how the index is related to the table data.

With a clustered index, the table data is organized according to the index order. Therefore, a table can usually have only one clustered organization.

With a non-clustered index, the index is a separate structure from the table data. It stores indexed values and references to the actual rows. A table can have multiple non-clustered indexes.

However, the exact behavior of clustered and non-clustered indexes can be different depending on the database system.

## Q24. What are query optimization strategies?

Query optimization is the process of improving a SQL query so that the database can return the result faster and use fewer resources.

Common strategies include using proper indexes, selecting only the required columns instead of using SELECT \*, filtering data with WHERE, using efficient joins, and limiting large result sets with pagination or LIMIT.

We can also use EXPLAIN or an execution plan to see how the database executes a query and find performance problems. Good indexing and database design can also improve query performance.

## Q25. What is a transaction and what are its states in DBMS?

A transaction is a logical unit of work that contains one or more related database operations.

All required operations should complete successfully before we commit the transaction. When we commit it, the changes become final. If any operation fails, we can roll back the transaction and undo its changes.

The main transaction states are Active, Partially Committed, Committed, Failed, and Aborted. A transaction is Active while its operations are running. After all operations are completed, it becomes Partially Committed. If the transaction is successfully committed, it becomes Committed. If an error occurs, it becomes Failed, and after rollback, it becomes Aborted.

## Q26. What is a deadlock in DBMS?

A deadlock is a situation where two or more transactions are waiting for each other to release locked resources, so none of them can continue.

For example, Transaction 1 may lock Row A and wait for Row B, while Transaction 2 locks Row B and waits for Row A. Both transactions are waiting for each other, so they cannot continue.

The database can detect the deadlock and usually aborts or rolls back one of the transactions so that the other transaction can continue.

## Q27. What is a database cursor?

A database cursor is a mechanism that allows us to process the rows of a query result one at a time.

A cursor keeps a current position in the result set, and we can use FETCH to move from one row to another. A cursor is usually declared, opened, fetched from, and then closed.

We can use a cursor when each row needs to be processed separately. However, when possible, set-based SQL operations are usually better because processing rows one by one can be slower.

## Q28. What is referential integrity?

Referential integrity is a rule in a relational database that ensures a foreign key always refers to a valid record in another table. Usually, it is maintained using a foreign key constraint. It prevents invalid or non-existing references between related tables and keeps the relationship between the tables consistent.

## Q29. What are the phases of the DBMS query processing cycle?

The DBMS query processing cycle generally has three main phases. First, the query is parsed and validated to check its syntax and meaning. Then, the query optimizer finds an efficient execution plan for the query. Finally, the DBMS executes that plan, accesses the required data, and returns the result to the user.

## Q30. What are the different types of backups in DBMS?

The main types of database backups are Full, Incremental, and Differential backups. A Full backup copies the entire database. An Incremental backup copies only the data that has changed since the last backup. A Differential backup copies all the data that has changed since the last Full backup. Full backups are easier to restore, while Incremental backups usually need less storage and time.

## Q31. What is hash indexing?

Hash indexing is an indexing technique that uses a hash function to map a key to a specific bucket. It is very efficient for exact-match searches because the database can quickly find the required bucket. However, it is generally not suitable for range queries because the data is not stored in sorted order.

## 🎯 MongoDB Fundamentals

## Q32. What is MongoDB?

MongoDB is a NoSQL and document-oriented database. Instead of storing data in tables and rows like a relational database, MongoDB stores data in collections and documents. The documents are stored in BSON format, which is similar to JSON.

The main features of MongoDB are flexible schema, powerful querying, indexing, replication, and horizontal scaling through sharding. A flexible schema allows documents in the same collection to have different structures. Replication helps provide high availability, while sharding helps distribute large amounts of data across multiple servers.

## Q33. Why is MongoDB considered a NoSQL database?

## Q34. What is the importance of the \_id field in MongoDB documents?

The `_id` field is a unique identifier for every document in a MongoDB collection.

If we do not provide an `_id` when inserting a document, MongoDB usually generates an `ObjectId` automatically. MongoDB also creates a unique index on the `_id` field, which makes lookups by `_id` efficient.

The `_id` field works as the unique identity of a document, similar to a primary key in a relational database.

## Q35. What is the difference between embedding and referencing in MongoDB?

Embedding and referencing are two ways to model related data in MongoDB.

With **embedding**, related data is stored inside the parent document as a nested document or an array. It is useful when the related data is small and is usually accessed together with the parent document.

With **referencing**, related data is stored in a separate document or collection, and the parent document stores an identifier that points to it. This is useful when the related data is large, is accessed independently, or can be shared by many documents.

The choice depends on the data structure and how the application usually reads and updates the data.

## Q36. What are the query and projection operators in MongoDB?

## Q37. What are the pagination techniques in MongoDB?

## Q38. How does indexing affect query performance in MongoDB?

## Q39. What are the MongoDB index types?

## Q40. How can you analyze query performance using explain("executionStats")?

## Q41. How can you optimize MongoDB for high read traffic?

## Q42. How does MongoDB handle security and access control?

## Q43. What are MongoDB transactions?

## Q44. What is the MongoDB Aggregation Framework?

## 🎯 Mongoose ODM

## Q45. What is Mongoose?

## Q46. What are Mongoose schema types and options?

## Q47. How are relationships handled in Mongoose?

## Q48. What is populate() in Mongoose?

## Q49. When should you use embedding vs. referencing in Mongoose?

## Q50. What is Mongoose middleware (hooks)?

## Q51. What is the difference between pre-hooks and post-hooks?

## Q52. What are lean queries in Mongoose?

## Q53. What does .lean() do in Mongoose?

## 🎯 MySQL vs PostgreSQL

## Q54. What are the architectural differences between MySQL and PostgreSQL?

MySQL and PostgreSQL are both relational databases, but their architectures are different. MySQL commonly uses a thread-based server model and has a pluggable storage engine architecture, such as InnoDB. PostgreSQL commonly uses a process-based server model and has a more integrated storage architecture. PostgreSQL is also highly extensible and supports custom data types, functions, and extensions. Both databases use MVCC-based mechanisms to handle concurrent transactions.

## Q55. What are the key differences between MySQL and PostgreSQL?

MySQL and PostgreSQL are both relational database systems, but they have some important differences. MySQL is popular for its simplicity, web applications, and pluggable storage engines such as InnoDB. PostgreSQL provides more advanced SQL features, complex query support, advanced data types, and strong extensibility. MySQL uses MVCC through InnoDB, while PostgreSQL has its own MVCC implementation. The better choice depends on the application's requirements and workload.

## Q56. How do MySQL and PostgreSQL handle transactions?

Both MySQL and PostgreSQL support ACID transactions. In MySQL, transaction handling mainly depends on the storage engine, and InnoDB is the main transactional storage engine. InnoDB uses MVCC, locking, and transaction logs. PostgreSQL has an integrated transaction system and uses MVCC, locks, and Write-Ahead Logging for consistency and recovery. In both databases, we can use COMMIT to make a transaction final and ROLLBACK to undo its changes.

## 🎯 Prisma ORM

## Q57. What is Prisma?

Prisma is a modern ORM and database toolkit for Node.js and TypeScript. It makes it easier for an application to work with relational databases. We can use Prisma Client to query the database, Prisma Schema to define our data models, and Prisma Migrate to manage database schema changes. Prisma itself is not a database; it works with databases such as PostgreSQL and MySQL.

## Q58. What are the core components of Prisma?

The three main components of Prisma are Prisma Client, Prisma Schema, and Prisma Migrate. Prisma Client is used to query the database from the application. Prisma Schema is used to define models, fields, and relationships. Prisma Migrate is used to manage and apply changes to the database schema.

## Q59. What is Prisma Schema (schema.prisma)?

Prisma Schema is a file, usually called schema.prisma, where we define the database connection, Prisma Client generator, and our data models. In the models, we can define fields, relationships, and constraints such as primary keys and unique fields. Prisma uses this schema to generate Prisma Client and manage database schema changes through Prisma Migrate.

## Q60. What is Prisma Client?

Prisma Client is a generated, type-safe database client for JavaScript and TypeScript applications. It allows us to interact with the database and perform operations such as creating, reading, updating, and deleting data. Prisma Client is generated based on the models defined in the Prisma Schema, so we can work with the database without writing raw SQL for every operation.

## Q61. What is Prisma Migrate?

Prisma Migrate is a database migration system provided by Prisma. It helps us apply and track changes made to the Prisma Schema in the actual database. For example, if we add a new field or table to our Prisma Schema, Prisma Migrate can create a migration and apply that change to the database.

## Q62. What is Prisma Studio?

Prisma Studio is a visual database management interface provided by Prisma. It allows developers to view and manage database records through a browser interface. It is mainly useful during development and debugging because we can easily inspect and edit the data without writing SQL queries manually.

## Q63. How are schema definitions and relationships created in Prisma?

In Prisma, schema definitions are created using models and fields in the schema.prisma file. Relationships are created using relation fields and foreign keys. For example, if one user can have many posts, the User model can have a posts Post[] field, while the Post model can have an author User relation and an authorId foreign key. The @relation attribute defines which fields are used for the relationship.

## Q64. How does Prisma prevent SQL injection?

Prisma helps prevent SQL injection by using parameterized queries in its normal query APIs. User input is treated as a value instead of being directly added to the SQL query string. This keeps the input separate from the SQL structure. However, when using raw SQL, developers must still use parameterized and safe queries because unsafe string concatenation can still create SQL injection risks.

## Q65. What are Prisma performance best practices?

Some important Prisma performance best practices are selecting only the required fields, avoiding unnecessary database queries, using pagination for large datasets, and adding proper indexes for frequently queried fields. We should also avoid N+1 query problems and keep transactions as short as possible. For slow queries, we can use query logging and database execution plans to find the problem.

## Q66. What are the limitations of Prisma?

Prisma has some limitations. For simple CRUD operations, it is very convenient, but complex or database-specific queries may sometimes require raw SQL. Because Prisma is an ORM, it also adds an abstraction layer between the application and the database, so we may not always have direct access to every database-specific feature. Prisma also does not automatically make our application fast. We still need to use proper indexes, write efficient queries, and optimize the database when necessary.

## 🎯 Database Optimization & Scaling

## Q67. What are the different database scaling strategies?

There are several common strategies for scaling a database. Vertical scaling means increasing the resources of the existing database server, such as CPU, RAM, or storage. Horizontal scaling means adding more database servers and distributing the workload between them. Replication keeps multiple copies of the same data on different servers, which can help with read performance and availability. Sharding divides a large dataset into smaller parts and stores those parts on different servers.

## Q68. What is vertical scaling (scale-up)?

Vertical scaling, also called scale-up, means increasing the resources of an existing database server. For example, we can increase its CPU, RAM, or storage when the database workload grows. We do not add more database servers; instead, we make the current server more powerful. It is usually easier to implement, but it has a limit because a single server can only be upgraded to a certain level.

## Q69. What is horizontal scaling (scale-out)?

Horizontal scaling, also called scale-out, means increasing the capacity of a database system by adding more servers instead of making one server more powerful. The workload can be distributed across multiple servers. Replication, read replicas, and sharding are common approaches used for horizontal scaling. It is useful when we need to support a large amount of data or a high number of requests.

## Q70. How can database reads be scaled using read replicas?

We can scale database reads by creating read replicas of the primary database. The primary database usually handles write operations, and its data is replicated to the read replicas. We can then send read requests to the replicas instead of sending all reads to the primary database. This distributes the read workload and helps the system handle more read traffic.

## Q71. What are database sharding strategies?

Database sharding means dividing a large database into smaller parts called shards and storing them on different servers. Common sharding strategies include range-based, hash-based, and directory-based sharding. Range-based sharding divides data based on value ranges. Hash-based sharding uses a hash function to decide the shard. Directory-based sharding uses a lookup directory to find which shard contains the data.

## Q72. What is range-based sharding?

Range-based sharding divides data into different shards based on ranges of a shard key. For example, users with IDs from 1 to 1000 can be stored in one shard, and users with IDs from 1001 to 2000 can be stored in another shard. It is useful for range queries, but it can create an unbalanced load if some ranges receive much more traffic.

## Q73. What is hash-based sharding?

Hash-based sharding uses a hash function on the shard key to decide which shard should store the data. It usually distributes data more evenly across shards and can reduce the chance of one shard becoming overloaded. However, it is not as good for range queries because nearby values can be stored on different shards.

## Q74. What is directory-based sharding?

Directory-based sharding uses a separate directory or lookup system to keep information about where data is stored. The directory maps a key or data item to a specific shard. When the application needs some data, it first checks the directory and then sends the request to the correct shard. It gives more control over data distribution, but the directory must be maintained and kept available.

## 🎯 Concurrency & Isolation Levels

## Q75. What are transaction isolation levels?

Transaction isolation levels define how multiple transactions behave when they run at the same time. They control what data one transaction can see from another transaction. The four standard isolation levels are Read Uncommitted, Read Committed, Repeatable Read, and Serializable. Read Uncommitted provides the lowest isolation, while Serializable provides the highest isolation. Higher isolation can prevent more concurrency problems, but it can also reduce performance and concurrency.

## Q76. What is Read Uncommitted?

Read Uncommitted is the lowest standard isolation level. It allows one transaction to read data that another transaction has not committed yet. Because of this, dirty reads can happen. It provides more concurrency, but it gives weaker data protection.

## Q77. What is Read Committed?

Read Committed means that a transaction can only read data that has already been committed by other transactions. Therefore, dirty reads are prevented. However, if another transaction changes and commits the same row, reading that row again can return a different value. So, non-repeatable reads can still happen.

## Q78. What is Repeatable Read?

Repeatable Read means that a transaction can read the same row multiple times and get a consistent result during that transaction. Even if another transaction updates and commits that row, the first transaction can continue to see its consistent version of the data. It prevents non-repeatable reads.

## Q79. What is Serializable isolation?

Serializable is the strongest standard transaction isolation level. It controls concurrent transactions so that their result is equivalent to running them one after another. It provides strong protection against concurrency problems, but it can reduce concurrency and performance because the database needs more coordination between transactions.

## Q80. What are dirty reads, non-repeatable reads, and phantom reads?

Dirty read হলো যখন একটি transaction অন্য transaction-এর uncommitted data পড়ে। Non-repeatable read হলো যখন একই transaction-এর মধ্যে একই row দুইবার পড়ে ভিন্ন value পাওয়া যায়। Phantom read হলো যখন একই transaction-এর মধ্যে একই condition দিয়ে query করলে নতুন matching rows দেখা যায়। এই সমস্যাগুলো control করার জন্য transaction isolation levels ব্যবহার করা হয়।

## Q81. What is optimistic locking?

Optimistic locking is a concurrency control technique where we do not lock the data when we read it. Instead, we keep a version number or timestamp with the data. When we update the data, we check whether the version is still the same. If another transaction has already changed the data, the update fails and we handle it as a conflict. It is useful when conflicts are not very common.

## Q82. What is pessimistic locking?

Pessimistic locking is a concurrency control technique where we assume that conflicts may happen between transactions. So, we lock the data before modifying it. If another transaction tries to modify the same locked data, it usually has to wait until the lock is released. It is useful when conflicts are expected to happen often.

## Q83. What is the difference between optimistic and pessimistic locking?

The main difference is how they handle conflicts. With optimistic locking, we usually do not lock the data when we read it. Instead, we use a version number or timestamp and check for changes when we update the data. With pessimistic locking, we lock the data before modifying it, so another transaction usually has to wait if it wants to modify the same data. Optimistic locking is useful when conflicts are rare, while pessimistic locking is useful when conflicts are more common.

## 🎯 Distributed Systems & Data Architecture

## Q84. What is the CAP theorem?

The CAP theorem is a principle about distributed systems. It says that during a network partition, a distributed system cannot guarantee strong consistency and availability at the same time while also providing partition tolerance. When a partition happens, the system usually has to choose between consistency and availability. This is why we often talk about CP and AP systems.

## Q85. What are Consistency, Availability, and Partition Tolerance?

Consistency means that after a successful write, the system provides a consistent and up-to-date result for later reads. Availability means that the system continues to respond to requests even when some nodes have problems. Partition tolerance means that the system can continue to operate when communication between some nodes is lost because of a network partition. When a partition happens, a distributed system generally has to choose between strong consistency and availability.

## Q86. What is the difference between CP and AP systems?

CP and AP are two approaches in the CAP theorem. A CP system prioritizes consistency when a network partition happens. If the system cannot guarantee consistent data, it may reject or delay some requests. An AP system prioritizes availability, so it continues to respond to requests during a network partition, even if the returned data may be temporarily stale.

## Q87. What is the PACELC theorem?

PACELC is an extension of the CAP theorem. It says that when a network partition happens, a distributed system has to make a trade-off between consistency and availability. Else, when there is no partition, the system still has to make a trade-off between latency and consistency. So, PACELC explains trade-offs both during a partition and during normal operation.

## Q88. How does PACELC extend the CAP theorem?

PACELC is an extension of the CAP theorem. CAP says that when a network partition happens, a distributed system has to make a trade-off between consistency and availability. PACELC adds that when there is no partition, the system may still have to make a trade-off between latency and consistency. So, PACELC explains trade-offs both during a network partition and during normal operation.

## Q89. What happens when an asynchronous read replica lags behind the primary node?

When an asynchronous read replica lags behind the primary, the replica may contain older data than the primary. This is called replication lag. If the application reads from the replica during this time, it may return stale data. The replica usually catches up when the pending changes are replicated from the primary. Therefore, reads that require the latest data may need to be sent to the primary.

## Q90. How can replication lag and read-your-own-writes consistency be handled?

Replication lag can cause a user to read old data from a replica immediately after a write. To handle read-your-own-writes consistency, we can route reads to the primary for some time after a write. We can also choose a replica only after it has caught up with the required update. In some systems, replication positions can be used to check this. If strong consistency is more important, synchronous replication can also be used, but it may increase write latency.

## 🎯 Deep-Dive Indexing Mechanics

## Q91. What is a B-Tree?

A B-Tree is a self-balancing tree data structure that stores multiple sorted keys in each node. It is commonly used for database indexes because it can support fast searching, range queries, and sorting. Since the tree remains balanced, its height stays relatively small, so search usually has O(log n) behavior.

## Q92. What is an LSM-Tree?

LSM-Tree stands for Log-Structured Merge-Tree. It is a data structure commonly used for write-heavy workloads. New data is first stored in an in-memory structure called a Memtable. When the Memtable becomes full, the data is written to disk as a sorted file called an SSTable. Later, multiple SSTables are merged through a process called compaction. This can provide very good write performance, but reads may need to check multiple files.

## Q93. What is the difference between a B-Tree and an LSM-Tree?

B-Tree and LSM-Tree are both data structures used by database systems to store and access data efficiently. A B-Tree keeps data in a balanced and sorted tree structure, so it usually provides good read and range query performance. An LSM-Tree first stores new writes in memory, then writes them to sorted files on disk and merges those files through compaction. Therefore, LSM-Trees are often better for write-heavy workloads, while B-Trees are commonly useful for read-heavy and mixed workloads.

## Q94. What is a covering index?

A covering index is an index that contains all the columns needed by a query. Because the index has all the required data, the database can get the result directly from the index without going back to the main table. This can improve query performance by avoiding an additional table lookup. However, large indexes need more storage and can increase the cost of write operations.

## Q95. What is an index-only scan?

An index-only scan is a query execution method where the database gets all the required data directly from an index without reading the main table. It can improve performance because it avoids an additional table lookup. However, the database optimizer decides whether an index-only scan is the best option for the query.

## Q96. When can a query be satisfied entirely from an index without accessing the table/heap?

A query can be satisfied entirely from an index when the index contains all the columns needed for filtering and returning the result. The database must also be able to determine that the required rows are visible without reading the main table or heap. When these conditions are met, the database can use an index-only scan.

## 🎯 Connection Management & Caching

## Q97. What is connection pooling?

Connection pooling is a technique where a group of database connections is created in advance and kept in a pool. When the application needs a connection, it takes an available connection from the pool. After the query is finished, the connection is returned to the pool instead of being closed. This reduces the cost of creating new connections and helps the application handle many requests efficiently.

## Q98. Why do databases fail under sudden traffic spikes without connection pooling?

Without connection pooling, a sudden traffic spike can cause many requests to create new database connections at the same time. A database has a limited number of connections, so the connection limit can be reached quickly. New requests may then wait, time out, or fail. Connection pooling keeps a limited number of connections and reuses them, which helps protect the database and handle traffic more efficiently.

## Q99. What are caching strategies?

Caching strategies define how an application stores, reads, and updates data in a cache. Common strategies include cache-aside, read-through, write-through, and write-behind. Caching can make frequently accessed data faster to read and can reduce the load on the database.

## Q100. What is cache-aside (lazy loading)?

In the cache-aside strategy, the application first checks the cache. If the data is found, it returns the data from the cache. If the data is not found, the application reads it from the database, stores it in the cache, and then returns it.

## Q101. What is write-through caching?

In write-through caching, when the application writes or updates data, the data is written to both the cache and the database. This helps keep the cache up to date, but the write operation can have more overhead because both systems need to be updated.

## Q102. What is write-behind caching?

In write-behind caching, data is first written to the cache and then written to the database asynchronously later. This can make write operations faster, but there is a risk of data loss if the cache fails before the data is written to the database.

## Q103. What are cache stampede/thundering herd, cache penetration, and cache breakdown?

A cache stampede, also called a thundering herd, happens when many requests go to the database at the same time after a popular cache entry expires. Cache penetration happens when requests repeatedly ask for data that does not exist in either the cache or the database. Cache breakdown usually refers to a hot cache entry becoming unavailable or expiring, which causes many requests to reach the database. Techniques such as locking, negative caching, TTL jitter, and input validation can help prevent these problems.

## 🎯 Production Node.js & ORM Nuances

## Q104. What is the N+1 query problem?

The N+1 query problem happens when we use one query to get N records and then run another query for each of those records. This results in N+1 database queries. It can increase database load and make the application slower because of many database round trips. We can avoid it by using joins, relation loading, or other efficient query techniques provided by the ORM.

## Q105. How can the N+1 query problem be solved?

We can solve the N+1 query problem by avoiding separate database queries inside a loop. We can use ORM relation loading, SQL joins, or batch queries to fetch related data more efficiently. In Prisma, we can use include to load related data. The main goal is to replace many individual queries with a smaller number of efficient queries.

## Q106. What are database migrations in zero-downtime deployments?

In a zero-downtime deployment, database migrations should be designed so that the application can continue running while the database schema changes. A common approach is to first make a backward-compatible change, such as adding a new column. Then we deploy code that uses the new structure and migrate the existing data. After all application instances use the new structure, we can remove the old structure. This is commonly called the expand-and-contract pattern.

## Q107. What is the expand-and-contract pattern?

The Expand-and-Contract pattern is a safe way to change a database schema during a zero-downtime deployment.

First, we expand the database by adding the new column or structure without removing the old one. Then, we update the application so that it can work with the new structure. We migrate the existing data if needed, and switch the application to the new structure. Finally, when we are sure that the old structure is no longer being used, we contract the database by removing it.

For example, if we want to replace a name column with full_name, we first add full_name, migrate the data, update the application to use full_name, and later remove name.

The main goal is to keep the old and new application versions compatible and avoid downtime during the migration.

## Q108. Why should you avoid renaming or dropping a column in a single migration while older application instances are still running?

We should avoid renaming or dropping a column in a single migration while older application instances are still running because those old instances may still use the old column.

For example, if the old application uses the `name` column and we rename it to `full_name`, the old application will still try to read or write `name`, and its queries may fail.

A safer approach is to first add the new column, deploy compatible application code, migrate the data, and switch all application instances to the new column. After that, we can remove the old column.

This prevents breaking the older application versions and helps us achieve a zero-downtime deployment.
