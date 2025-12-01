## The lecture

![[9.1 7-9-stickyBit-SGID-SUID@WinDroidSY Telegram.pdf]]
***
### 1- Sticky bit
When the sticky bit is set on a directory, only the root user, the owner of the directory, and the owner of a file can remove files within said directory.
#### To set the Sticky Bit:
```bash
chmod +t <folder>
chmod 1777 <folder>
```

> [!INFO] Note
> If we're inside the folder, we can write
> ```bash
> chmod +t .
> ```

***
### 2- SUID       
SUID is a special permission assigned to a file. These permissions allow the file being executed to be executed with the privileges of the owner. For example, if a file was owned by the root user and has the setuid bit set, no matter who executed the file it would always run with root user privileges.
#### To set the SUID:
```bash
chmod u+s <file>
chmod 4777 <file>
```

> [!WARNING]
> Make sure the file is executable

***
### 3- SGID
When the Set Group ID bit is set, the executable is run with the authority of the group. For example, if a file was owned by the users’ group, no matter who executed that file it would always run with the authority of the user’s group.
#### To set the SGID:
```bash
chmod g+s /opt/script
chmod 2777 /opt/script
```
***
