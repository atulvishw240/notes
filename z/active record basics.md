
## What is an ORM

>Object-Relational-Mapping provides a nice interface between our application code and databases.

Rails is actually seven Ruby gems that work harmoniously together. Active Record is, to put it inelegantly, the gem that takes care of all the database stuff.

Its advantage is if you switch from one database to another, you don’t actually need to change any major application code, just some configuration files. (`config/database.yml`)

## Rails models

A ruby file which inherits from **Active Record**.

## What is Active Record

The term "Active Record" also refers to a software architecture pattern. Active Record in Rails is an implementation of that pattern. 

### The Active Record Pattern

an object that wraps a row in a database table, encapsulates the database access, and adds domain logic to that data.

## Active Record as an ORM Framework

Active Record gives us the ability to do the following using Ruby objects:

- Represent models and their data.
- Represent associations between models.
- Represent inheritance hierarchies through related models.
- Validate models before they get persisted to the database.
- Perform database operations in an object-oriented fashion.

## Convention over Configuration in Active Record

**Naming Conventions** : A model's class named **Book** maps to a database table named **books**.
**Schema conventions** :
- **Primary keys** : default **id** (`bigint`) column
- **Foreign keys** : `singularized_table_name_id`. Ex: `order_id`

## Creating Active Record Models

`ApplicationRecord` is the base class for all Active Record models in your app. To create a Book model. This create a **Book** model, mapped to **books** table in the database.
```ruby
class Book < ApplicationRecord
end
```

Database tables in Rails are typically created using **Active Record Migrations**. Ex:
`$ bin/rails generate migration CreateBooks title:string author:string`

`$ bin/rails generate model Book title:string author:string` will generate the **Book** model and corresponding migration.

Active record can also be used to perform **CRUD** operations to a database.


