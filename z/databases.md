
>CRUD - Create, Read, Update, and Destroy.

Every CRUDdy command in SQL contains a few parts - the action ("statement"), the table it should run on, and the conditions ("clauses"). If you just do an action on a table without specifying conditions, it will apply to the whole table and you'll probably break something.

>[!warning]
>`DELETE FROM users` without a `WHERE` clause, which removes all your users from the table.

## Create 

```sql
INSERT INTO users (name, email) VALUES ('foobar', 'foo@bar.com');
```


## SELECT

```sql
SELECT DISTINCT species
FROM friends_of_pickles
WHERE height_cm > 50;
```

#### ORDER BY

Can you run a query that sorts the **friends_of_pickles** by _height_cm_ in descending order?
```sql
SELECT *
FROM friends_of_pickles
ORDER BY height_cm DESC;
```

#### LIMIT

Return the single row of the tallest **friends_of_pickles**
```sql
SELECT *
FROM friends_of_pickles
ORDER BY height_cm DESC LIMIT 1;
```

#### COUNT`(*)`

```sql
SELECT COUNT(*) FROM friends_of_pickles;
```

returns the total number of rows in the table **friends_of_pickles**

#### SUM `(*)`

Can you find the total **num_books_read** made by this family?
```sql
SELECT SUM(num_books_read)
FROM family_members;
```

#### AVG

Can you find the average **num_books_read** made by each family member?
```sql
SELECT AVG(num_books_read)
FROM family_members;
```

#### MAX

Can you find the highest num_books_read that a family member makes?
```sql
SELECT MAX(num_books_read)
FROM family_members;
```

#### GROUP BY

For example,
```sql
SELECT COUNT(*), species 
FROM friends_of_pickles 
GROUP BY species;
```

would return the number of rows for each species.

#### IS NOT NULL OR IS NULL

Can you return all of the rows of **family_members** where _favorite_book_ is not null?
```sql
SELECT *
FROM family_members
WHERE favorite_book IS NOT NULL;
```


## UPDATE

If `WHERE` clause finds multiple rows then they'll all get updated.
```sql
UPDATE users
SET name='barfoo', email='bar@foo.com'
WHERE email='foo@bar.com';
```


## IN

Using the `WHERE` clause, we can find rows where a value is in a list of several possible values.  
  
```sql
SELECT * FROM friends_of_pickles WHERE species IN ('cat', 'human');
```

would return the **friends_of_pickles** that are either a cat or a human.

