## 1. Lexical Analysis
- First phase of compiler
- Process of converting sequence of characters to sequence of tokens
- Go to SQL doc to get tokens

```
int x=2+3
```
To
```
INT ID ASSIGN OP NUM 
ADD OP NUM SEMICOLON
```
### Note
> **lexems**: the values of tokens
### Role of lexical analyzer
- Identify tokens
- Insert lexems into symbol table
- Remove all white spaces
- Returns tokens to praser
### How to build lexers?
There are tools that generate lexer
Example: ANTLR4

### ANTLR
support multiple target language
- Take a grammar
- Take input (code) like tokens, etc.
- Give a `.java` file 

![[Screenshot 2025-11-06 140729.png]]
### Two types of grammar
- Lexer grammar
- Parser grammar

![[Screenshot 2025-11-06 141623.png]]
```G4
GREETING: ('Hello'|'Greeting')
ID: [a-zA-Z]+
WS: [\t\r\n]+->skip
```
- Left hand side: token
- Right hand side: Regular Expressions (RG) 
Example:
- Token: Greeting
- RG: 'Hello' or 'Greeting'