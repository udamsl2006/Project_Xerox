Xerox Language version 0.0.2
This is a programming language created in sri lanka based on C# and that language uses near English style scripting system.

An English-prose-style interpreted programming language that reads like plain English.

## Quick Start

```bash
# Run a file
xerox hello.xe

# Start interactive REPL
xerox

# Create a project
mkdir myapp && cd myapp
xm init

# Install packages
xm install math
xm install testing
xm install scientific
xm install networking
xm install advancedmath

# Run
xm run run
xm run test
```

---

## Language Sample

```
// Variables
create number age  with value 25
create text   name with value "Alice"

// Template strings
display f"Hello {name}, you are {age} years old!"

// Lambdas & higher-order functions
create list numbers with value [1, 2, 3, 4, 5, 6, 7, 8, 9, 10]
create list evens   with value filter(numbers, lambda that takes x => x modulo 2 is equal to 0)
create number sum   with value reduce(evens, lambda that takes a and b => a plus b, 0)
display f"Sum of evens: {sum}"

// Try / Catch
try
    throw "Something failed"
catch err
    display f"Caught: {err}"
end try

// Match
match age
    when age is greater than 17: display "Adult"
    otherwise:                   display "Minor"
end match

// OOP
blueprint Animal
    has name with value "unknown"
    build with n
        set itself.name to n
    end build
    knows how to speak
        display f"{itself.name} speaks!"
    end function
end blueprint

create object dog with value new Animal with "Rex"
call dog.speak
```

---

## Packages (via xm)

| Package | Install | Functions |
|---------|---------|-----------|
| `math` | `xm install math` | `factorial`, `fibonacci`, `isPrime`, `gcd`, `lcm`, `lerp` |
| `strings` | `xm install strings` | `capitalize`, `titleCase`, `isPalindrome`, `toWords` |
| `collections` | `xm install collections` | `groupBy`, `chunk`, `intersection`, `countBy` |
| `json` | `xm install json` | `stringify`, `prettyPrint` |
| `testing` | `xm install testing` | `test`, `expect`, `toBe`, `summary` |
| `networking` | `xm install networking` | `parseUrl`, `buildQueryString`, `makeClient`, `isPrivateIP`, `mimeType` |
| `scientific` | `xm install scientific` | `mean`, `stdDev`, `linearRegression`, `matMultiply`, `celsiusToFahrenheit` |
| `advancedmath` | `xm install advancedmath` | `isPrime`, `modPow`, `complex`, `fibonacci`, `collatz`, `toBinary` |

---

you must add xerox and xm as environmet variables

