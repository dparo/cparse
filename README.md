# cparse
C parser in pure JavaScript

## Installation

`TODO put this on npm`

## Usage

### CommonJS
```javascript
var cparse = require('./cparse.js');
var ast = cparse("void main() { int answer = 6 * 7; }");
console.log(JSON.stringify(ast, undefined, 4));
```

### Browser
```html
<script src="cparse.js"></script>
<script>
var ast = cparse("void main() { int answer = 6 * 7; }");
console.log(JSON.stringify(ast, undefined, 4));
</script>
```

## AST Format
Parsing code:
```C
int answer = 6 * 7;
```

outputs following AST:
```JSON
[
    {
        "type": "GlobalVariableDeclaration",
        "modifier": [],
        "pointer": 0,
        "name": "answer",
        "valueType": "int",
        "value": {
            "type": "BinaryExpression",
            "operator": "*",
            "right": {
                "type": "Literal",
                "value": 7
            },
            "left": {
                "type": "Literal",
                "value": 6
            }
        }
    }
]
```

##License
```
"THE BEER-WARE LICENSE":

Jakob Löw <eragonjml@googlemail.com> wrote this code. As long as you retain this notice you
can do whatever you want with this stuff. If we meet some day, and you think
this stuff is worth it, you can buy me a beer in return.
```
