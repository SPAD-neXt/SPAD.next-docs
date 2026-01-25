# Expressions

SPAD.neXt contains a powerful expression evaluation system, which can be used throughout all events and actions.

If not stated differently in the event/action the result of the expression is expected to be a number.

By default all data references will be interpreted as numbers. You might need to apply conversion (see [Functions](functions.md)) or preface your expression with `''+` (two single quotes) to enforce the expression system to interpret (and automatically convert) everything as a string.

The underlying expression system (ncalc) is Open-Source and can be found [here](https://github.com/ncalc/ncalc)

