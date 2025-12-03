Use `$?` variable to check if the command if it ran correctly or not
```bash
echo $?
```
- After each command
- It will return
	- `0` ran correctly
	- `1` error
#### Example
```bash
cat /etc
echo $?
```
It will return `0`

## Usage
In scripts to check if the command ran correctly or not
```bash
if [ $? -ne 0 ]
then
	echo "Failure"
	exit
fi
```