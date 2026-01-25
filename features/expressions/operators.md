# Expressions: Operators

Expressions can be combined using operators. Each operator as a precedence priority. Here is the list of those expression's priority.

### Logical

These operators can do some logical comparison between other expressions:

* or, ||
* and, &&

{% hint style="info" %}
The **and** operator has more priority than the **or**, thus in the example above, **false and true** is evaluated first.
{% endhint %}

### Relational

* \=, ==, !=, <, >
* <, <=, >, >=

### Additive

* +, -

### Multiplicative

* \*, /, %

### Bitwise

*   & (bitwise and), | (bitwise or), ^(bitwise xor), << (left shift), >>(right shift)

    > 2 >> 3

    **Unary**
* !, not, -, \~ (bitwise not)

### Primary

* (, )

$$2 * ( 3 +2)$$
