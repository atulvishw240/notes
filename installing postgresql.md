
## Environments and pipelines

In the context of application development, an environment is the collection of tools, configurations and conventions that developers write and run code with.
(OS + vscode + rbenv + etc.)

There are four basic types of environments that are typically set up together:
1. Development environment 
2. Test environment
3. Staging environment
4. Production environment


## Environment variables

- **Definition:** Variables stored at the **Operating System (OS)** level rather than inside your source code.
- **Purpose:** Keeps sensitive data (API keys, passwords) out of your codebase and **Git/GitHub history**, where it could be publicly exposed.
- **Security:** Since these variables exist only on the machine where the app is running, they are inaccessible to outside users or version control.
- **Rails Integration (`RAILS_ENV`):**
    - Rails checks this variable to determine if it is in **Development**, **Test**, or **Production** mode.
    - **Default Behavior:** If no variable is found, Rails automatically assumes you are in **Development**.
- **Usage:** Commonly used to store **PostgreSQL credentials** so your app can connect to the database securely.
