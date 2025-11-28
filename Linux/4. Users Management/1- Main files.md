| **File name**  | **Contain**                      |
| -------------- | -------------------------------- |
| `/etc/passwd`  | (Users)                          |
| `/etc/group`   | (Groups)                         |
| `/etc/shadow`  | (Encrypted passwords)            |
| `/etc/gshadow` | (Encrypted passwords for groups) |
***
## 1- Return password

 ```bash
 cat /etc/passwd
 ```
returns something like this
```bash
root:x:0:0:root:/root:/bin/bash
```

| root             | x                   | 0         | 0        | root                       | /root               | /bin/bash                                     |
| ---------------- | ------------------- | --------- | -------- | -------------------------- | ------------------- | --------------------------------------------- |
| name of the user | user has a password | user's ID | group ID | Information about the user | home user directory | default shell that use to execute the command |
>[!Note] Note
> The `ID` from 0-999 is reserved by the system.
> All `user's ID` starts from 1000.

***
## 2- Return groups

```bash
 cat /etc/group
 ```
returns something like this
```bash
root:x:0:
```

| root              | x            | 0   |
| ----------------- | ------------ | --- |
| name of the group | has password | ID  |
***
## 3- Add user

```bash
useradd <username>
```
### Options:
- `-d` specify the home directory
- `-m` create the directory
- `-G` add sub-groups
#### Example
```bash
useradd user4 -d /opt/user4 -m -G addition
```
***
## 4- Change password

```bash
passwd <username>
```
***
