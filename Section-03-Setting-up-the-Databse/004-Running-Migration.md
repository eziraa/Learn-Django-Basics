## Running Migrations

- Migrations contain a set change on the model
- It is like commit in version control system
- Remember our model is still not reflectd in database
- So to reflect those changes we use the following command

```bash
python manage.py migrate
```

- If you want to see tables of SQLite database you can use extension called (SQLite) for vscode

- After you installed the extension then open command pallet by using shortcut( CTRL + SHIFT + P)
- The type `Open SQl database` and open it select you database
- Then it will be added in your explorer in the left side below your main project

- Then you see the table by right click on the table and click show table

- You can see SQL format of your migration
- Let us see SQL format of the 2nd migration in store app 

```bash
python manage.py sqlmigrate store 0002
```