
Keywords: `if`, `then`, `else`, `when`, `switch`

## if-then expression
- `then` and `else` blocks must be one-liners

## and-or expression
- `let a = b and c or d` uses `c` if `b` is truthy otherwise `d`

## braced if statement
- cannot be used as expression (like the name implies)
- `else if` must also use braces
- `else foo()` is legal

## trailing if statement
- `let a = b if c` declares the variable outside the if statement
- two ways to negate a function result
  - `a if !(b c)` or `a if !b(c)`
  - `a if !b c` is illegal

## when expression
- `when {}` braces are required
- `then` and `else` blocks must be one-liners

## switch statement
- `switch(x) {}` parens and braces are required
- `when (a, b)` when 2+ values are valid matches
- `when a then b` for one-liners
- `when (a) {}` otherwise
- `else` can omit braces if a one-liner

