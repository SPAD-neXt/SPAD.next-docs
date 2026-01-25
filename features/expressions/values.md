# Expressions: Values

## Values

A value is a token representing a concrete element. This can be:

* an integer
* a floating point number
* a date time
* a boolean
* a string
* a function
* a parameter

### Integers

They are represented using numbers.

```
123456
```

They are evaluated as **Int32**.

### Floating point numbers

Use the dot to define the decimal part.

```
123.456
.123
```

They are evaluated as **Decimal**.

### Scientific notation

You can use the **e** to define power of ten (10^).

```
1.22e1
1e2
1e+2
1e-2
.1e-2
1e10
```

They are evaluated as Double

### Dates and Times

Must be enclosed between sharps.

```
#2008/01/31# // Note it's US format!
```

The are evaluated as **DateTime**. Expression always use invariant culture (en-us)

### Booleans

Booleans can be either **true** or **false**.

```
true
```

### Strings

Any character between single quotes "**'**" are evaluated as **String**.

```
'hello'
```

You can escape special characters using **\\**, **\\'**, **\n**, **\r**, **\t**.

To enter special characters (e.g. a degree symbol) you can either hold the Alt-Key and enter the asciicode ([https://theasciicode.com.ar/extended-ascii-code/degree-symbol-ascii-code-248.html](https://theasciicode.com.ar/extended-ascii-code/degree-symbol-ascii-code-248.html)) via the numpad (degree = Alt 248) or add the unicode representation \u00B0 (unicode for degree symbol)

### Function

A function is made of a name followed by braces `()` , containing optionally any value as arguments.

```
  Abs(1), doSomehting(1, 'dummy')
```

Please read the [functions](functions.md) page for details.

### Simulation Data

You can reference any data available by enclosing teh datareference in `[]`

```
  2 + [x]
```

Please read the [Referencing-Simulation-Data](referencing-simulation-data.md) page for details
