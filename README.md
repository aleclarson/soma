# soma v0.0.2

Javascript-like language that transpiles to Lua.

**NOTE:** None of this is implemented.

### Keywords
- `class {}` declaration
- `function() {}` declaration
- `@` instead of `this`
- `is` instead of `instanceof`
- `or` instead of `||`
- `and` instead of `&&`
- `let` for variable declaration (block-scoped)
- `global` transpiles to `_G`
- `export` for module exports
- `import` for module imports
- `import()` for require-like syntax
- `typeof` transpiles to `type()`
- `echo` transpiles to `print()`
- `new Foo` transpiles to `Foo.new()`

### Comparison
- `a == b` for strict equals
- `a != b` for *not* strict equals
- `x in [1..10]` range comparison
- `a?` shorthand for `a != nil`
- `!a` shorthand for `a == nil or a == false`

### Operators
- `?=` operator sets variable if nil
- `?.` operator for nil-safe accessors
- `#` operator for string/table length
- `|` operator for piping function results

### Class
- `extends` keyword
- `constructor` keyword
- `get` and `set` keywords
- `foo() {}` method declaration
- `@foo() {}` static methods
- `@foo =` static properties

### Variables
- `let a, b = 1` sets `b` to `1`
- `let (a, b) = (1, 2)` sets `a` to `1` and `b` to `2`
- `let (a, b) =` works with function call on right-hand side too
- assignment of an undeclared variable is a compile-time error

### Literals
- `[]` built-in array structure
- `{}` map literals require braces
- `/.+/g` regex literals
- `do { }` blocks

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
- `(function() {})()` self-calling functions

### Tuples
- return a tuple: `return (1, 2, 3)`
- assign a tuple: `let (a, b) = (1, 2)`
- without let: `(a, b) = (1, 2)` for existing vars
- set properties: `(a[b], a.c) = (1, 2)`
- tuple to array: `let arr[] = (1, 2)`

### Lambdas (function w/ implicit return)
- `() =>` one-liner
- `() => {}` multi-line
- `@` is bound to parent scope `@`
- `(foo => {})` optional syntax if only one arg

### Conditionals
- no braces: `if true`
- with braces: `if (true) {}`
- function calls must use parens: `if foo()` or `if (foo 1, 2)`
- trailing `if` statement (eg: `return 1 if true`)
- `else if` instead of Lua's `elseif`
- `if a = opts.a` set variable and test it

### Switch blocks
- no braces: `switch x`
- with braces: `switch (x) {}`
- `when` keyword for each match
- `when 1:` for one-line match block
- empty `when` blocks use next `when` block
- `else` keyword for default block
- no implicit fallthrough

### Loops
- no braces: `while true`
- with braces: `while (true) {}`
- trailing loop declaration (eg: `a += 1 while true`)
- `while true` loop
- `until true` loop
- `do {} while true` loop
- `do {} until true` loop
- `for x in map` array/map loops (value only)
- `for k, x in map` array/map loops (index/key, value)
- `for a, b, c of iter` iterator loops
- `for x in [1..2]` range loops
- `continue` keyword
- `break` keyword

### Strings
- single or double quotes
- literal concat: `"a\b/c"` => `"a" .. b .. "c"`
- `"a\(b + 1)/c"` for expressions
- variable concat: `a\b\c` => `a .. b .. c`
- multi-line strings (`"` only)
- `a \= b` => `a = a .. b`

### Expressions
- `a = 1` returns `1`
- `a = if true then 1 else 0`
- `a = do {}`

### Comments
- `//` for single line
- `/* */` for multi line

### Modules
- `import` supports relative paths
- `export function` export only a function
- `export foo =` set a property export (accessible in scope too)
- `export {}` export only a map
- `export []` export only an array

### Undecided
- `enum` structs?
- `setmetatable` keyword?
- allow semicolons?

