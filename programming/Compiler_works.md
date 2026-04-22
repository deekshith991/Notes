
# how compilers are made

## LEXING
converting the file into tokens of and stroing the type text Line:column
| Type         | Text     | Line/Column |
|--------------|----------|-------------|
| FN           | 'fn'     | (0:1)       |
| IDENTIFIER   | 'main'   | (1:2)       |
| (            | '('      | (1:3)       |
| )            | ')'      | (1:4)       |
| :            | ':'      | (1:5)       |
| INT          | 'int'    | (1:7)       |
| ...          | ...      | ...         |
| ;            | ';'      | (7:6)       |
| RETURN       | 'return' | (8:2)       |
| INT_LITERAL  | '0'      | (8:4)       |
| ;            | ';'      | (8:5)       |
| }            | '}'      | (9:1)       |
| EOF          | ''       | (9:2)       |

converts the data into .ast->abstract syntax tree
lokks at token if it is unsure looks ahead.


for expresion we need to consider the binding power where we 
