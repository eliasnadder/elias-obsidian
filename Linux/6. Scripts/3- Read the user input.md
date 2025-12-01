- Read user input and store it in a param
```bash
read <param>
```
- Add a hint to a user
```bash
read -p "Text" <param>
```
***
### Example
```bash
#!/bin/bash

#Read input from user

read -p "Insert Username: " username
read -s -p "Insert Password: " password

echo "The user: " $username
echo "The Pass: " $password
```

> [!ERROR] Note 
> option `-s` is for password to make it invisible
