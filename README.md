# soma v0.0.1

Javascript-like language that transpiles to Lua.

**NOTE:** None of this is implemented.

### Keywords
- `class {}` declaration
- `function() {}` declaration
- `@` instead of `this`
- `or` instead of `||`
- `and` instead of `&&`
- `let` for variable declaration (block-scoped)
- `global` transpiles to `_G`
- `export` for module exports
- `import` for module imports
- `import()` for require-like syntax

### Operators
- `~=` operator for "not equal"
- `?=` operator sets variable if nil
- `?.` operator for nil-safe accessors
- `?` operator shorthand for `~= nil`
- `!` operator to convert value to boolean
- `#` operator for string/table length

### Class
- `extends` keyword
- `constructor` keyword
- `get` and `set` keywords

### Expressions
- `a = 1` returns `1`

### Variables
- `let a, b = 1` sets `b` to `1`
- `let (a, b) = (1, 2)` sets `a` to `1` and `b` to `2`
- `let (a, b) =` works with function call on right-hand side too

### Literals
- `[]` built-in array structure
- `{}` map literals require braces
- `/.+/g` regex literals
- `do { }` blocks (are expressions)

### Arrays
- `let [a, b, c] =` array destructuring

### Functions
- tuples (eg: `return (1, 2)`)
- named `function` hoisting
- call functions with or without parens
- `:` passes left-hand as first argument to right-hand function
- `...args` named param spreads and rest args
- `() =>` for one-line functions (implicit return)
- `() =>` has `@` bound to parent scope `@`

### Maps
- `let m = {a, b, c}` map key to variable of same name
- `let {a, b, c} =` map destructuring
- `{ [x]: 1 }` any value as map key

### Loops
- `for x in arr` array loops (value only)
- `for x of map` map loops (value only)
- `for i, v in arr` array loops (index and value)
- `for k, v of map` map loops (key and value)
- `for x in [1..2]` range loops

### Comments
- `//` for single line
- `/* */` for multi line

### Undecided
- template strings?
- `setmetatable` keyword?
- `instanceof` keyword?

