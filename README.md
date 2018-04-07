# soma v0.1.0

When you mix Javascript with Lua, you get Soma!

Check out [DESIGN.md](./DESIGN.md) for a general idea of the syntax.

Check out the [rules](./rules) to learn about syntax restrictions.

Check out the [guide](./guide) for example code!

The following sections explore the behavior of Soma,
as well as where it differs from Javascript or Lua (or both)!

### Variable hoisting

All function and variable declarations are hoisted,
and named `function` definitions are moved above
all other code.

```
let x = 1
let y = foo()

function foo() {
  return x + bar()
}

function bar() {
  return 2
}
```

The above script becomes:

```lua
local x, y, foo, bar

function foo()
  return x + bar()
end

function bar()
  return 2
end

local x = 1
local y = foo()
```
