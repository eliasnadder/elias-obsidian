## Text editors
- VI (Recommended)
- nano
- pico

## VI editor
### I- Create & Open
To create and open a new file at the same time
```bash
vi <file>
```
![[Screenshot 2025-11-10 210413.png]]
- Give the info of the created file

<hr>
### II- Write
press `esc` and `i` to start write
![[Screenshot 2025-11-10 211020.png]]
The mode changed and we can start editing
To close, press `esc` then write 
- `:w` to write on the file 
- `:wq` to write & quite
- `:q!` quite without save editing 
![[Screenshot 2025-11-10 211724.png]]

<hr>
### III- Search
`esc` + `/<text>` to search
![[Screenshot 2025-11-10 212723.png]]
- to move between results, press `n`
- to back to a previous result, press `shift + n` or `N`

<hr>
### IV- Move to specific line
`esc` + `:<number of line>`

<hr>
### V- Copy & Past
#### A. Copy one line
set the pointer on the line you need to copy it
**Copy:** `esc` + `yy`
Past: `esc` + `p`
#### B. Copy multi-lines
**Copy:** `esc` + `<number of lines - 1>y`
**Past:** `esc` + `p`
##### Note
> `esc` + `<number of lines>yy` copy from a line to previous
#### C. From specified line to the end of the file
1. Set a pointer on the line
2. `esc` + `yG`

<hr>
### VI- Delete lines
#### A. One line
1. Set a pointer on the line
2. `esc` + `dd`
#### B. Multi-lines
1. Set a pointer on the line
2. `esc` + `<number of lines - 1>d`
##### Note
> `esc` + `<number of lines>dd` delete from a line to previous
#### C. From specified line to the end of the file
1. Set a pointer on the line
2. `esc` + `dG`

<hr>
### VII. Undo
`esc` + `u` 