> [!ERROR] 
> If the file has permission `-rw-rw-rw-` and the folder has permission `drwxrwxr-x`, the `others` cannot delete the file from the folder even use force in the `rm` command

> [!ERROR]
> If the file has permission `-rw-rw-r--` (has `w` or not) and the folder has permission `drwxrwxrwx`, the `others` can delete the file from the folder by using force in the `rm` command (and cannot without force)
