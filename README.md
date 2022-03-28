# EFP (Excel Formula Parser)
Using EFP (Excel Formula Parser) you can get an Abstract Syntax Tree (AST) from Excel formula.

## Installation

```bash
go get github.com/go-exp/efp
```

## Example

```go
package main

import "github.com/go-exp/efp"

func main() {
    ps := efp.ExcelParser()
    ps.Parse("=SUM(A3+B9*2)/2")
    println(ps.PrettyPrint())
}
```

Get AST

```text
SUM <Function> <Start>
    A3 <Operand> <Range>
    + <OperatorInfix> <Math>
    B9 <Operand> <Range>
    * <OperatorInfix> <Math>
    2 <Operand> <Number>
 <Function> <Stop>
/ <OperatorInfix> <Math>
2 <Operand> <Number>
```
