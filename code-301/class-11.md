# Mongo and Mongoose

## NoSQL vs SQL

Source *(Article)*: [The Geek Stuff: NoSQL vs SQL](https://www.thegeekstuff.com/2014/01/sql-vs-nosql-db/?utm_source=tuicool)

* Fill in the chart below with five differences between SQL and NoSQL databases:

| SQL | NoSQL |
|----|----|
| Relational | Non-relational|
| Predefined Schema | No schema |
| Scale Vertically | Scale Horizontally |
| Table based | Document based |
| Good for complex queries | Not good for complex queries |

* What kind of data is a good fit for an SQL database?
  * SQL databases are a good fit for non-hierarchical data.
* Give a real world example.
  * This would include a key list of users being related to a list of server roles. You can simply point to which roles are assigned to which users in a third table, instead of writing one or the other multiple times.
* What kind of data is a good fit a NoSQL database?
  * Hierarchical data.
* Give a real world example.
  * Storing multiple detail within a document that has username first, like purchases or additional settings details that can be placed inside their own nested containers within the user container.
* Which type of database is best for hierarchical data storage?
  * NoSQL databases.
* Which type of database is best for scalability?
  * SQL, since it allows for more stable operations, and keeps data fairly atomized and contained as it scales upward.

## SQL vs NoSQL or MySQL vs MongoDB

Source *(video)*: [SQL vs NoSQL or MySQL vs MongoDB](https://www.youtube.com/watch?v=ZS_kXvOeQ5Y)

* What does SQL stand for?
  * Structured Query Language
* What is a relational database?
  * A relational database is a database with certain assumptions that works with the Structured Query Language. The 'relational' part refers to having multiple tables which relate to each other.
* What type of structure does a relational database work with?
  * Tables that store data. A database can include multiple tables.
* What is a ‘schema’?
  * A 'schema' is a clear and strict set of rules for which data can be stored in a table and how it should look when stored. A schema is defined by the fields of an entry.
* What is a NoSQL database?
  * A database composed of collections and documents. Documents in the same collection can use different schema from each other.
* How does it work?
  * A database is composed of documents, which contain collections that look similar to JSON. There is no schema and relational data does not play a major role, though it is possible to set up.
* What is inside of a Mongo database?
  * Documents and collections. Documents are similar to SQL Tables, and collections are similar to SQL rows.
* Which is more flexible - SQL or MongoDB? and why.
  * Mongo DB. Because there is no schema requirement for collections, data can be stored in whatever schema we want without having to create different collections for different schema.
* What is the disadvantage of a NoSQL database?
  * As a result of MongoDB's ability to store anything anywhere, it is common to have duplicate data within the database. Updates to data may have to be performed in multiple places in a database

## Things I want to know more about

Really just how to use these tools. The idea of database management sounds exciting, but also seems like it would be horribly monotonous and taxing if implemented poorly. Hopefully I can gain good judgement of when to use each type of database to avoid suboptimal results.