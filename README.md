# costume-party
##SQL Commands for Creating Database + User
We create a db for every project and a specific user in the db for that project. This is for security purposes.
```
create database costume_party;
create user 'prodba'@'localhost' identified by 'yellowpencil';
grant all privileges on costume_party.* to 'prodba'@'localhost';
```