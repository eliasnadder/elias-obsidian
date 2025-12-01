```bash
#!/bin/bash

## $1

read -p "Enter the 2nd Mumber" secnum
if [ $1 -gt $secnum ]
then
	echo "greater than"
else
	echo "less than"
echo "Parameter greater than Input"
echo "Parameter Less than or equal Input"
```

> [!INFO] Other options
> `-ls` less than
> `-eq` equal
> `-ne` not equal