## Permissions to numbers

| read    | 4   | r   |
| ------- | --- | --- |
| write   | 2   | w   |
| execute | 1   | x   |
***
## 1- Change permissions

```bash
chmod <numbers> <file|folder>
```
### Example 
Make file w/ permission `-rw-r----`
```bash
chmod 640 f1.txt
```
***
## 2- Change owner

```bash
chown <username>:[...<group-name>] <file|folder>
```
### Example
```bash
chown tech1:teachers f1.txt
```
***
## 3- Permission by symbols

| Owner user | u   |
| ---------- | --- |
| Group      | g   |
| Others     | o   |
```bash
chmod u+x f.txt
chmod ug+rw f.txt
chmod o-r f.txt
```
