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
- `typeof` transpiles to `type()`
- `echo` transpiles to `print()`

### Operators
- `==` operator for strict equals
- `!=` operator for not strict equals
- `?=` operator sets variable if nil
- `?.` operator for nil-safe accessors
- `?` operator shorthand for `~= nil`
- `!` operator to convert value to boolean
- `#` operator for string/table length
- `|` operator for piping function results

### Class
- `extends` keyword
- `constructor` keyword
- `get` and `set` keywords
- `foo() {}` method declaration
- `@foo() {}` static methods

### Expressions
- `a = 1` returns `1`
- `a = if true then 1 else 0`

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
- `push`, `unshift`, and `concat` methods
- `map`, `filter`, `reduce`, `forEach` methods
- `slice` and `splice` methods

### Maps
- `let m = {a, b, c}` map key to variable of same name
- `let {a, b, c} =` map destructuring
- `{ [x]: 1 }` any value as map key

### Functions
- named `function` hoisting
- function call no args: `foo()`
- function call no parens: `foo 1, 2`
- function call w/ parens: `foo(1, 2)` or `foo (1, 2)` or `(foo 1, 2)`
- method calls: `a:b()` sets `a` as `@` of `b`
- `@foo()` is a method call, do `@.foo()` for function calls
- `...args` named rest arguments (and array unpacking)
- `function(a = 1) {}` default argument values

### Tuples
- return a tuple: `return (1, 2, 3)`
- assign a tuple: `let (a, b) = (1, 2)`

### Lambdas (function w/ implicit return)
- `() =>` one-liner
- `() => {}` multi-line
- `@` is bound to parent scope `@`
- `(foo => {})` optional syntax if only one arg

### Conditionals
- parens not required
- no braces (except `if true do {}`)
- trailing `if` statement (eg: `return 1 if true`)

### Loops
- parens not required
- no braces (except `while true do {}`)
- `while true` loop
- `until true` loop
- `do {} while true` loop
- `for x in arr` array loops (value only)
- `for x of map` map loops (value only)
- `for i, v in arr` array loops (index and value)
- `for k, v of map` map loops (key and value)
- `for x in [1..2]` range loops
- `continue` keyword
- `break` keyword

### Comments
- `//` for single line
- `/* */` for multi line

### Undecided
- template strings?
- `setmetatable` keyword?
- `instanceof` keyword?
- allow semicolons?

