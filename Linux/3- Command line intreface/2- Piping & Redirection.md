- **Piping:** forward the output of some command to another
- **Redirection**: forward the output of some command to file

## I- Redirection `>`
```bash
echo "Hello World" > myfile.txt
ls /etc/ > file.txt
```
- `>` override the file
- `>>` append to the end of file
```bash
echo "Text1" > text.txt
echo "Text2" >> text.txt
```
***
## II- Piping `|`
```bash
cat /etc/passwd | grep elias | wc -l
```
