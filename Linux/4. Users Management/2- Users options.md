## 1- Create a new group

```bash
groupadd <group-name>
```
***
## 2- Update user `usermod <username>`

### Change user information
```bash
usermod <username> -c "Text"
```
### Change user home directory
```bash
usermod <username> -d <path> -m
```
- `-m` to create the folder
### Change user primary group
```bash
usermod <username> -g <group-name>
```
### Add user to another group
```bash
usermod <username> -G [<group-name>, ...]
```
#### Note
> Make sure to add the primary group as the first group when add another groups

***
## 3- View user group

```bash
groups <username>
```
***
## 4- Switch between users

```bash
su <username>
```
***