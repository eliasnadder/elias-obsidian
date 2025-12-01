### I- Create a parameter
To create a parameter, write
```bash
name_of_parameter = $no_parameter
```
#### For Example
```bash
username=$1
password=$2
address=$3
```
***
### II- Invoke the parameter
```bash
$parameter
```
#### Example
```bash
echo $username
```
***
### III- Run the file
```bash
<file> value_parameter1 value_parameter2 ...
```
#### Example
```bash
./script elias 12345
```
***
### IV- Full example
```bash
# File name: script
#!/bin/bash
username=$1
password=$2

echo "Username is: " $username
echo "Password is: " $password
```

```bash
chmod +x script
./script elias 12345
```
***
