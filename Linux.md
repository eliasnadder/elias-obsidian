 linux mutli user system

Users types:
- regular user
- system user
- admin
Each user has:
- username
- home directory
- UID
- default shell
normal user ID starts from 1000
system user ID starts from 100
## Command
`pwd`:
Where am I
`sudo adduser <name>`: create a user (Only for root)
- The users locate in `/home`
`sudo cat /etc/shadow`: passwords folder
`sudo cat /etc/passwd`: user folder
`sudo -i`: go to root
### Folders:
`bin` folder: command folder
`var` folder: variable folder