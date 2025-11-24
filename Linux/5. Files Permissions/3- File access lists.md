Give a permission to a user that is not the owner of the file/folder or not in the file/folder group.
## 1- Give permissions
```bash
setfacl -m u:<username>:<permissions> <file>
```
### Example
```bash
setfacl -m u:eng1:rwx f1.txt
```
***
## 2- To delete access list

```bash
setfacl -x u:<username>:<permissions> <file>
```
### Example
```bash
setfacl -x u:eng1:rwx t1.txt
```
### A- To delete all access lists on file

```bash
setfacl -b <file>
```
### Example
```bash
setfacl -b t1.txt
```
***
## 3- To see applied access lists

```bash
getfacl <file>
```
### Example
```bash
getfacl t1.txt
```
