# Values

A value is a terminal token representing a concrete element. This can be:
* an integer
* a floating point number
* a date time
* a boolean
* a string
* a function
* a parameter

## Integers

They are represented using numbers. 

{{
123456
}}
They are evaluated as **Int32**.

## Floating point numbers

Use the dot to define the decimal part. 

{{
123.456
.123
}}
They are evaluated as **Decimal**.

## Scientific notation

You can use the **e** to define power of ten (10^).
{{
1.22e1
1e2
1e+2
1e-2
.1e-2
1e10
}}
They are evaluated as Double

## Dates and Times

Must be enclosed between sharps. 

{{
#2008/01/31# // for en-US culture
}}
The are evaluated as **DateTime**. NCalc uses the current Culture to evaluate them.

## Booleans

Booleans can be either **true** or **false**.

{{
true
}}
## Strings

Any character between single quotes "**'**" are evaluated as **String**. 

{{
'hello'
}}
You can escape special characters using **\\**, **\'**, **\n**, **\r**, **\t**.

## Function

A function is made of a name followed by braces, containing optionally any value as arguments.

{{
  Abs(1), doSomehting(1, 'dummy')
}}
Please read the [functions](functions) page for details.

## Parameters

A parameter as a name, and can be optionnaly contained inside brakets.

{{
  2 + x, 2 + [x](x)
}}
Please read the [parameters](parameters) page for details