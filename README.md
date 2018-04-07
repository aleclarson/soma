# soma v0.1.0

When you mix Javascript with Lua, you get Soma!

Check out [DESIGN.md](./DESIGN.md) for a general idea of the syntax.

Check out the [rules](./rules) to learn about syntax restrictions.

Check out the [guide](./guide) for example code!

The following sections explore the behavior of Soma,
as well as where it differs from Javascript or Lua (or both)!

### Function hoisting

Named functions are hoisted above all other code in the
nearest block.

Just like in Javascript, this lets you call named functions before
they appear in the script. For example, one of your named functions
may decide to call another named function that's defined further
down in the script!

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
function foo()
  return x + bar()
end

function bar()
  return 2
end

local x = 1
local y = foo()
```
