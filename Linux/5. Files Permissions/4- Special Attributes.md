Add an attribute to a file to prevent delete
***
![[8.1 7-8-special-attributes@WinDroidSY Telegram.pdf]]
***
## 1- Add attribute
### A- Add immutable attribute
A file is set with `i` attribute, cannot be modified (immutable). Means no renaming, no symbolic link creation, no execution, no writable, only superuser can unset the attribute.
```bash
chattr +i <file>
```
### B- Add append attribute
A file is set with `a` attribute, can only be open in append mode for writing.
```bash
chattr +a <file>
```

>[!NOTE] Note
>And to add at the end of file
> `echo "Text" >> <file>`

---
## 2- Show attribute

```bash
lsattr <file>
```
***
## 3- Remove attribute
### A- Remove immutable attribute
```bash
chattr -i <file>
```
***
[For more attribute](https://wiki.archlinux.org/title/File_permissions_and_attributes#File_attributes)
