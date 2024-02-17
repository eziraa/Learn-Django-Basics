## Connecting Django with MySQl Client

- To connect our projedct to mysql client we have to install package called `mysqlclient`

```bash
pypenv install mysqlclient
```


- Then to cennect to the MySQL server use the following command insert the password you gave when installing `mysql`

```bash
mysql -u root -p
```
- Then it asks you to insert password then insert cerrect password

- Then go to the cofiguration file(setting.py) adn change the default database as follows 
- Enter your own database name, username, password, database engines(mysql if you want to use mysql)
![Change default database](../Images/change%20database.png)


- You will get unapplied migrations

![Unapplied migraions](../Images/unapplied%20migrations.png)