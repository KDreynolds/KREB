
# **Programming Language Design Document**

## **Grammar Definitions**

### **Variable Declaration**
```bnf
<variable_declaration> ::= <type> <identifier> "=" <expression> ";"
<type> ::= "int" | "string" | "float" | "bool"
<identifier> ::= [a-zA-Z_][a-zA-Z0-9_]*  (* Variable names *)
<expression> ::= <literal> | <identifier> | <operation>
<literal> ::= <number> | <string>
<number> ::= [0-9]+
<string> ::= "\"[^"\n]*\""
<operation> ::= <expression> <operator> <expression>
<operator> ::= "+" | "-" | "*" | "/"  (* Basic math operators *)
```

### **Function Declaration**
```bnf
<function_declaration> ::= "fx" <identifier> "(" <parameter_list> ")" ":" <block>
<parameter_list> ::= <parameter> ("," <parameter>)*
<parameter> ::= <type> <identifier>
<block> ::= <statement>+
<statement> ::= <variable_declaration> | <expression> | <return_statement>
<return_statement> ::= "return" <expression> ";"
```

### **Control Flow**
```bnf
<if_statement> ::= "if" "(" <expression> ")" ":" <block> ["else" ":" <block>]
<loop_statement> ::= "for" "(" <variable_declaration> ";" <expression> ";" <expression> ")" ":" <block>
                   | "while" "(" <expression> ")" ":" <block>
```
