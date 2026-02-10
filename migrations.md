
A Rails migration is a script that sets up or modifies a database’s schema in a reversible and re-appliable way. Migrations use schema-altering SQL commands under the hood, similar to how the Model makes SQL queries for you.

**Two ways to create a migration**:
1. `$ rails generate model YourModeNameHere`
2. `$ rails generate migration NameYourMigration`

**To run the migration**: `$ rails db:migrate`

>[!question] Why migrations are useful?

- If you decide to deploy to the web, you will run those same migrations and the production database will be there waiting for you… even if it’s a different type of database!
- If you screwed something up `$ rails db:rollback`

**Reversibility**: For each method that you use in the migration, you want to specify how to reverse it if you have to. The reverse of adding a table is dropping that table, of adding a column is removing the column and so on.

Many methods have a really obvious reverse case, so you don’t need to explicitly state it and can set up the whole migration file using the **change** method. But some of them do not, so you will need to separately specify  **up** and **down** methods.

>Active Record knows which migrations to run because it prepends the migrations file with a UTC timestamp `YYYYMMDDHHMMSS`

---

