This is where syntax ideas are organized.

### Keywords
- `class {}` declaration
- `function() {}` declaration
- `isa` instead of `instanceof` and `typeof`
- `or` instead of `||`
- `and` instead of `&&`
- `let` for variable declaration (block-scoped)
- `export` for module exports
- `import` for module imports
- `import()` for require-like syntax
- `echo` transpiles to `print()`
- `new Foo` transpiles to `Foo.new()`
- `throw` transpiles to `error()`
- `try..catch` transpiles to `pcall()`
- `void` transpiles to empty userdata

### Comparison
- `a == b` for strict equals
- `a != b` for *not* strict equals
- `x in [1..10]` range comparison
- `a?` shorthand for `a != nil`
- `!a` shorthand for `a == nil or a == false`

### Operators
- `a ?= b` sets `a` to `b` if `a == nil`
- `a ?? b` returns `a` if `a != nil` else `b`
- `a?.b` returns `a.b` if `a != nil` else `nil`
- `a?:b()` will call the `b` method if `a != nil`
- `a:b?()` will call the `b` method if `a.b != nil`
- `#` for string/table length
- `|` for piping function results

### Variables
- `let a, b = 1` sets `a` to `nil` and `b` to `1`
- `let (a, b) = (1, 2)` sets `a` to `1` and `b` to `2`
- `let (a, b) =` works with function call on right-hand side too
- assignment of an undeclared variable is a compile-time error

### Literals
- `[]` built-in array structure
- `{}` map literals require braces
- `$[]` read-only array
- `${}` read-only map
- `!{}` Lua table (must use `x = 1` for string keys)
- `/.+/g` regex literals
- `do { }` blocks

### Arrays
- `let [a, b, c] =` array destructuring
- `push`, `unshift`, `shift`, `pop`, and `concat` methods
- `map`, `filter`, `reduce`, `forEach` methods
- `join`, `slice`, and `splice` methods
- `arr[2..3]` slice from 2 to 3
- `arr[5..]` slice from 5 to end
- `arr[..3]` slice first 3 items
- `arr[-2..]` slice last 2 items
- `arr[..]` clone the array
- `let arr = [2..3]` range literal

### Maps
- `let m = {a, b, c}` map key to variable of same name
- `let {a, b, c} =` map destructuring
- `{ [x]: 1 }` any value as map key
- `m.{a: 1, b: 2}` shorthand property assignment
- `foo(a: 1, b: 2)` optional braces for one-line tables wrapped with function call parens

### Functions
- no parens: `foo 1, 2` (not allowed if 0 args)
- with parens: `foo(1, 2)` or `foo (1, 2)` or `(foo 1, 2)`
- method calls: `a:b()` sets `a` as `@` of `b`
- context: `@` or `this`
- context property: `@x` or `this.x`
- context methods: `@foo()` or `this:foo()`
- context functions: `@.foo()` or `this.foo()`
- functions using `@` or `this` are called as methods
- `...args` named rest arguments (and array unpacking)
- `function(a = 1) {}` default argument values
- `(function() {})()` self-calling functions
- named functions are hoisted: `function foo() {}`
- Unnamed `...` within a function to spread all arguments

### Macros
- aka inlined "functions"
- `macro foo() {}`
- the expansion is always wrapped with parens
- arguments are always wrapped with parens
- `%arg%` is used for embedded identifiers

### Tuples
- return a tuple: `return (1, 2, 3)`
- assign a tuple: `let (a, b) = (1, 2)`
- without let: `(a, b) = (1, 2)` for existing vars
- set properties: `(a[b], a.c) = (1, 2)`

### Lambdas (function w/ implicit return)
- `() =>` one-liner
- `() => {}` multi-line
- `@` is bound to parent scope `@`
- `(foo => {})` optional syntax if only one arg

### Class
- `extends` keyword
- `constructor` keyword
- `get` and `set` keywords
- `foo() {}` method declaration
- `@foo() {}` static methods
- `@foo =` static properties
- named classes are hoisted: `class Foo {}`
- anonymous classes are not: `let x = class {}`
- mutate a metatable: `Foo:bar = function() {}`

### Super
- `super` returns the metatable of the superclass
- `super()` within a method to call the overrided method
- `super.foo()` to call some other method of the superclass

### Conditionals
- no braces: `if true`
- with braces: `if (true) {}`
- function calls must use parens: `if foo()` or `if (foo 1, 2)`
- trailing `if` statement (eg: `return 1 if true`)
- `else if` instead of Lua's `elseif`
- `else while` and `else for` are allowed
- `if a = opts.a` set variable and test it
- `unless a and b` is equivalent to `if !(a and b)`

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
- `for x in [1..10]` range loops
- `continue` keyword
- `break` keyword

### Strings
- single or double quotes
- `"a \(b) c"` => `"a " .. b .. " c"`
- `"a \(b + 1) c"` => `" a" .. (b + 1) .. " c"`
- `a \ b \ c` => `a .. b .. c`
- `a \= b` => `a = a .. b`
- interpolation in `"` only
- literal line breaks in `"` only

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
- rename to `nug` with `.nug` extension
- `enum` structs?
- `setmetatable` keyword?
- `struct` keyword (FFI in LuaJIT)
- `effect` keyword ("did set" handler in `class` body)
- `weak` keyword (weak property declaration in `class` body)
- allow semicolons?

