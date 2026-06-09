
The bottom layer of any web application is the database and it handles all the remembering (username and password)

A **relational database** is a database organized according to the _relational model_ of data. In simple terms, the relational model defines a set of relations and connections, between them in order to determine how the data stored in them can interact.

A **relational database management system**, or **RDBMS**, is essentially a software application, or system, for managing relational databases. There are many relational database management systems such as [SQLite](http://www.sqlite.org/), [MS SQL](http://www.microsoft.com/en-us/server-cloud/products/sql-server/default.aspx), [PostgreSQL](http://www.postgresql.org/) and [MySQL](http://www.mysql.com/).

**SQL**, which stands for _Structured Query Language_, is the programming language used to communicate with a relational database.

>SQL is a little different to other programming languages you may have encountered. SQL is a **declarative** language; when you write a SQL statement you describe _what_ needs to be done, but not exactly _how_ to do it -- the exact details of how the query is executed are handled internally by the RDBMS you are using.


>[!important] E.F. Codd is the father of relational model


Finding a way to visualize what’s going on when you do SQL queries is pretty important. We actually think of Excel tables moving in our heads and combining with each other and reshuffling as necessary.

## Schema

The setup information for your database is stored in a special file called the “**Schema**”, and this is updated whenever you make changes to the structure of your database.

You can index a column with `CREATE INDEX`. This sorts the table ahead of time based on the column which you'll search upon (like usrename). This results in faster search responses.

---

Every CRUDdy command in SQL contains a few parts – the action (“statement”), the table it should run on, and the conditions (“clauses”). If you just do an action on a table without specifying conditions, it will apply to the whole table and you’ll probably break something.