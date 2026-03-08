Xerox Language version 0.0.1
This is a programming language created in sri lanka based on C# and that language uses near English style scripting system.

## Language Guide

### Variables & Types

```xerox
create number age   with value 25
create text   name  with value "Alice"
create bool   flag  with value true
create list   items with value [1, 2, 3]
create any    x                          // declared, unset (nothing)

set age  to 26
let name = "Bob"                         // shorthand assignment
```

**Types:** `number`, `text`, `bool`, `list`, `object`, `any`

---

### Arithmetic

```xerox
create number a with value 10
create number b with value 3

display a plus b                  // 13
display a minus b                 // 7
display a multiplied by b         // 30
display a divided by b            // 3.333…
display a modulo b                // 1
display squareroot of 16          // 4
display absolute of -7            // 7
display floor of 3.9              // 3
display ceiling of 3.1            // 4
display round of 2.5              // 3
display pow(2, 8)                 // 256

// Symbolic operators work too
display 10 + 3
display 10 * 3
```

---

### String Operations

```xerox
create text s with value "Hello"

display s joined with " World"        // Hello World
display length of s                   // 5
display upper(s)                      // HELLO
display lower(s)                      // hello
display trim("  hi  ")                // hi
display s contains "ell"              // true
display s starts with "He"            // true
display s ends with "lo"              // true
display split("a,b,c", ",")           // [a, b, c]
display join("-", ["x","y","z"])      // x-y-z
display replace("foo bar", "bar", "baz") // foo baz
display substring("hello", 1, 3)     // ell
```

---

### Control Flow

```xerox
// if / otherwise if / otherwise
if score is greater than 90 then
    display "A"
otherwise if score is greater than 80 then
    display "B"
otherwise
    display "C"
end if

// while loop
while x is less than 10
    set x to x plus 1
end while

// repeat N times
repeat 5 times
    display "hello"
end repeat

// for each
for each item in myList
    display item
end for

// break / skip(continue)
while true
    if done then
        break
    end if
    skip   // continue to next iteration
end while
```

---

### Functions

```xerox
define function add that takes a and b
    give back a plus b
end function

// Call with 'call … with …'
create number result with value call add with 3, 4

// Default parameters
define function greet that takes name and greeting with value "Hello"
    display greeting joined with ", " joined with name
end function
call greet with "Alice"              // Hello, Alice
call greet with "Bob" and "Hi"       // Hi, Bob

// Recursion
define function factorial that takes n
    if n is less than 2 then
        give back 1
    end if
    give back n multiplied by call factorial with n minus 1
end function
```

---

### Lists

```xerox
create list nums with value [1, 2, 3]

add 4 to nums                         // append
remove 2 from nums                    // remove by value
remove at index 0 from nums           // remove by index

display nums at index 1               // access by index
display count of nums                 // size
display first(nums)
display last(nums)
display sort(nums)
display reverse(nums)
display slice(nums, 0, 2)
display flatten([[1,[2]],[3]])

for each item in nums
    display item
end for
```

---

### Blueprints (Classes)

```xerox
blueprint Animal
    has name  with value "unknown"
    has sound with value "..."

    build with n
        set itself.name to n
    end build

    knows how to speak
        display itself.name joined with " says " joined with itself.sound
    end function
end blueprint

// Inheritance
blueprint Dog extends Animal
    build with n
        set itself.name  to n
        set itself.sound to "Woof!"
    end build

    knows how to fetch that takes item
        display itself.name joined with " fetches the " joined with item
    end function
end blueprint

create object dog with value new Dog with "Rex"
call dog.speak            // Rex says Woof!
call dog.fetch with "ball"
display dog.name          // Rex
```

---

### Comparison & Logic

```xerox
x is greater than y
x is less than y
x is equal to y
x is not equal to y
x is not greater than y

// Logical
true and false        // false
true or false         // true
not true              // false
both a and b          // both a and b must be truthy

// Symbolic
x > y   x < y   x >= y   x <= y   x == y   x != y
x && y  x || y  !x
```

---

### Standard Library

| Category  | Functions |
|-----------|-----------|
| **IO**    | `display`, `print`, `ask`, `readLine`, `readNumber` |
| **Math**  | `abs`, `round`, `floor`, `ceiling`, `sqrt`, `pow`, `sin`, `cos`, `tan`, `log`, `exp`, `max`, `min`, `clamp`, `random`, `randomInt` |
| **String**| `upper`, `lower`, `trim`, `split`, `join`, `replace`, `contains`, `startsWith`, `endsWith`, `indexOf`, `substring`, `charAt`, `repeat`, `padLeft`, `padRight`, `format`, `isBlank` |
| **List**  | `count`, `isEmpty`, `append`, `prepend`, `removeAt`, `removeValue`, `get`, `set`, `sort`, `reverse`, `slice`, `concat`, `first`, `last`, `flatten`, `contains`, `indexOf` |
| **Convert**| `toNumber`, `toText`, `toBool`, `isNumber`, `isText`, `isBool`, `isList`, `isObject`, `isNothing`, `typeOf` |
| **System**| `now`, `today`, `timestamp`, `wait`, `exit`, `error`, `assert`, `version` |

**Constants:** `PI`, `E`, `INFINITY`, `NAN`

---

### Comments

```xerox
// Single line comment

/* Multi-line
   block comment */
```

---

## File Extension

Xerox source files use `.xe` or `.xerox`.

## CLI Usage

```
xerox                        Start REPL
xerox hello.xe               Run a file
xerox hello.xe arg1 arg2     Run with arguments (available as 'args' list)
xerox -e "display 1 + 1"     Evaluate expression
xerox --version              Show version
xerox --help                 Show usage
```

## REPL Commands

```
>>> help          Show help
>>> env           Show current variables


>>> history       Show input history
>>> :load file.xe Load a file
>>> exit          Quit
```


Download (Windows) :  https://drive.google.com/file/d/111W4MoiG1Xx6UZucwo-YU0a7cL3SufMn/view?usp=drive_link

Other builds will release in future
