# BrainFuckInterpreter

### Basic add modular (destructive):
```
, > ,
a   b

[-<+>] <
```
Info:
```
[START]: on CELL 1
[ROOM]: 2 CELLS
[FINISH]: on CELL 0
[RESULT]: on CELL 0
[DESTRUCTIVE?]: YES
```
___

### Basic add modular (non-destructive):
```
, > , <
a   b

[>>+>+<<<-] >>> [<<<+>>>-] <<
[>+>+<<-] >> [<<+>>-] <
```
Info:
```
[START]: on CELL 0
[ROOM]: 4 CELLS
[FINISH]: on CELL 2
[RESULT]: on CELL 2
[DESTRUCTIVE?]: NO
```
___

### Basic subtract modular (destructive):
```
, > ,
a   b

[-<->] <
```
Info:
```
[START]: on CELL 1
[ROOM]: 2 CELLS
[FINISH]: on CELL 0
[RESULT]: on CELL 0
[DESTRUCTIVE?]: YES
```

___

### Factorial modular (WIP):
```
++++++++
> , <
  a

[->------<] > convert from ASCII value to actual number

[[->+>+<<]>>-] < spread out the number ("7" becomes "7"0"6"0"5"0"4"0"3"0"2"0"1"0"0...)

--  put the spread out number back together ("7"0"6"0"5"0"4"0"3"0"2"0"1"0"0... becomes "7"6"5"4"3"2"1"0"0...)
[
  ++
  [<<]>>
  [>]>[[-<+>]>>]
  <<<
  --
]
++
```
Info:
```
[START]: on CELL 1
[ROOM]: "a" CELLS
[FINISH]: on CELL ?
[RESULT]: on CELL ?
[DESTRUCTIVE?]: ?
```
___

### Basic subtract modular (non-destructive):
```
, > , <
a   b

[>>+>+<<<-] >>> [<<<+>>>-] <<
[>->+<<-] >> [<<+>>-] <
```
Info:
```
[START]: on CELL 0
[ROOM]: 4 CELLS
[FINISH]: on CELL 2
[RESULT]: on CELL 2
[DESTRUCTIVE?]: NO
```

___

### Basic if statement modular (destructive):
```
, > , <
a   b

[->-<] > SETUP

[ if (a !== b)
  do stuff
  
  return to cell 1
  [-] <->
]

<+

[ else
  do stuff
  
  return to cell 0
  [-]
]
```
Info:
```
[START]: on CELL 0 (before SETUP) or CELL 1 (after SETUP)
[ROOM]: ? CELLS
[FINISH]: on CELL ?
[RESULT]: on CELL ?
[DESTRUCTIVE?]: YES
```
