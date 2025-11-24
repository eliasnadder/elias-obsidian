![[1.1 5-1-more-commands@WinDroidSY Telegram.pdf]]
***
```bash
find <path> -name "<file>"
```
- It's case sensitive 
- To ignore case sensitive
```bash
find <path> -iname "<file>"
```
***
```bash
wc <path to file>
```
- It returns number of the lines, words, and characters
**Options:**
- `-l` returns no. lines
- `-w` returns no. words
- `-c`  returns no. characters
```bash
wc -l <file>
```
```bash
wc -w <file>
```
```bash
wc -c <file>
```
***
```bash
which <command>
``` 
***
```bash
grep "text" <file>
```
***
```bash
more <file>
``` 
^fbf7bf
- scroll only to down by `space`
***
```bash
less <file>
```
- scroll up and down by arrows
- better than [[#^fbf7bf|more]] 
- Exit by type `q`
***
