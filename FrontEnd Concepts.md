<!-- Bare Minimum Front end Concepts -->

Data types refers to the different kind of values that can be store and manipulated on demand . In Js we have several data types .

## Number : Represent numeric value , including integers and floating point numbers .

```bash
   255; // two-hundred and fifty-five
   255.0; // same number
   255 === 255.0; // true
   255 === 0xff; // true (hexadecimal notation)
   255 === 0b11111111; // true (binary notation)
   255 === 0.255e3; // true (decimal exponential notation)
```

A number literal like 37 in JavaScript code is a floating-point value, not an integer. There is no separate integer type in common everyday use. (JavaScript also has a BigInt type, but it's not designed to replace Number for everyday uses. 37 is still a number, not a BigInt.)

When used as a function, Number(value) converts a string or other value to the Number type. If the value can't be converted, it returns NaN.

## Number coercion

Many built-in operations that expect numbers first coerce their arguments to numbers (which is largely why Number objects behave similarly to number primitives). The operation can be summarized as follows:

- Numbers are returned as-is.
- undefined turns into NaN.
- null turns into 0.
- true turns into 1; false turns into 0.
- Strings are converted by parsing them as if they contain a number literal. Parsing failure results in NaN. There are some minor differences compared to an actual number literal:
- Leading and trailing whitespace/line terminators are ignored.
- leading 0 digit does not cause the number to become an octal literal (or get rejected in strict mode).
- "+" and - are allowed at the start of the string to indicate its sign. (In actual code, they "look like" part of the literal, but -are actually separate unary operators.) However, the sign can only appear once, and must not be followed by whitespace.
- nfinity and -Infinity are recognized as literals. In actual code, they are global variables.
- Empty or whitespace-only strings are converted to 0.
- Numeric separators are not allowed.
- BigInts throw a TypeError to prevent unintended implicit coercion causing loss of precision.
  Symbols throw a TypeError.
- Objects are first converted to a primitive by calling their [@@toPrimitive]() (with "number" as hint), valueOf(), and toString() methods, in that order. The resulting primitive is then converted to a number.

---

## String

- The String object is used to represent and manipulate a sequence of characters.

---

## Immutable

    An immutable value is one whose content cannot be changed without creating an entirely new value.

    In JavaScript, primitive values are immutable — once a primitive value is created, it cannot be changed, although the variable that holds it may be reassigned another value. By contrast, objects and arrays are mutable by default — their properties and elements can be changed without reassigning a new value.

    It can be beneficial to use immutable objects for several reasons:

    To improve performance (no planning for the object's future changes)
    To reduce memory use (make object references instead of cloning the whole object)
    Thread-safety (multiple threads can reference the same object without interfering with one other)
    Lower developer mental burden (the object's state won't change and its behavior is always consistent)
    Note that you can easily prove mutability: an object is mutable as long as it offers one way to change its properties. On the other hand, immutability is hard to prove if there are no language semantics to secure it — it is a matter of developer contract. For example, Object.freeze() is a language-level method to make an object immutable in JavaScript.
