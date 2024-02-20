## Connecting Django with MySQl Client

- To connect our project to mysql client we have to install package called `mysqlclient`

```bash
pypenv install mysqlclient
```


- Then to connect to the MySQL server use the following command insert the password you gave when installing `mysql`

```bash
mysql -u root -p
```
- Then it asks you to insert password then insert correct password

- Then go to the configuration file(setting.py) adn change the default database as follows 
- Enter your own database name, username, password, database engines(mysql if you want to use mysql)
![Change default database](../Images/change%20database.png)


- You will get unapplied migrations

![Unapplied migrations](../Images/unapplied%20migrations.png)

- Then migrate them

```bash
python manage.py migrate
```

