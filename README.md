# Idioms, types and constructions in programming languages

Of course, everything can be interpreted via a Turing machine or lambda calculus. Point is to list idiomatic constructions used in programming langauges.

Being type theoretically correct is not a goal.

This is not about dynamic and static languages. This is not about compilation, interpretation or preprocessing.

This is a record of my understanding of this as of March of 2023.

## Unit

This type exists because its value and type is unique.

Haskell example (`()` is the unit): `putStrLn :: String -> IO ()`.

## Nil

This type exists because its value is different. Sometimes putting it somewhere causes an error.

## Blank

This special identifier exists because anything can be assigned to it without actual assignment happening.

## Boolean

Sometimes known as a bit.

This type exists to represent extremes on a spectum (0 and 1, truth and false).

Boolean logic can be done upon booleans: xor, and, or, not, ...

Related: pair, tag.

## Tag

Given some names, makes them nominal to differentiate between them.

Related: enums, iota, preprocessor macros.

## Range

Given a and b, exists to represent a possible value from a to b.

Endless debate could be had on whether a and b should be included or excluded from the range and whether idiomatic ranges should start at zero, one or some other number.

Related: iterators.

## Natural number

Exists to number things and perform arithmetics.

Example: a pointer.

## Integer

Imply specific representation in bits.

## Other numbers

Floating point numbers, rational number, complex numbers, irrational numbers, etc.

Many real computers operate on numbers of limited size. Sometimes this limits the programmer.

## Array of bits

Imply size of an array.

Many computers use this. Many assembler use this. Many assemblers are untyped. Code is data, data is code.

## Directed array of bits

https://en.wikipedia.org/wiki/Endianness

## Name

Array of bits. Sometimes with other strings attached (pun indented).

Implies an isomorphism between names and bits. Example: UTF-8. Another example: some internal or external representation, enforced by a text editor, a language run time, and/or by an operating system.

Tcl exists there, everything is a name (a string). Other data structures are built upon this. Interpreter optimizes as it can. Code is data, data is code.

## Stack

Parameterized by type of its elements. Allows pushing on top and popping from top.

## Queue

Parameterized by type of its elements. Allows pushing on top and popping from the bottom.

## Linked list

Parameterized by type of its elements.

Usually built upon pointers.

Scheme and some other LISPs exists there. “LISP” means “list processor”. Other data structures are present in Scheme (atoms). Code is data, data is code.

Interestingly enough, often lambdas can’t be looked into.

## Graphs, trees, hash trees, etc.

They exist too, yes.

Many immutable data structures use trees under the hood.

Merkle trees are awesome, too.

## Tuple

Parameterized by array of types x, contains values of each of the types in x.

## Array

Sometimes known as an array of one dimension.

Sometimes terminated with a zero element.

Parameterized by type of its elements.

Arrays is a dictionary from numbers to elements of the array.

## Slice

Array and its length.

## Structure

Can’t be expanded after definition.

Maps offsets (in the language: names) to structure elements.

In C: `struct`.

## Name space

Map names to values.

## Pair

Given types a and b, allows accessing both of them (commonly known as “left” and “right”).

## Bijective dictionary

Given types k and v, maps k to v, such that all mappings point to a different element.

Bijections are trivially invertible.

Example in Python: {0: "red", 1: "green", 2: "blue"}

Counterexample: {0: "red", 1: "red"}.

## Dictionary

Given k and v, maps k to v.

Example: tables in Lua. Keys can be anything except nil and nan.

## Log

Given v, maps some time value to v.

Useful for robustness (write ahead logs) and error detection.

## Bijective function

## Function

Given types k and v, maps k to v.

From perspective of a mathematician, dictionaries and functions are the same.

## Check sum

Given type k, maps k to some check sum (hash).

## Intersection

Given n types, contains intersection of them. Constrains.

## Union

Given n types, contains one of them at one point in time.

## Tagged union

Union and tag, allows to dispatch on actual type in run time.

Tags may be nominal, as in Haskell: `data StringOrInt = StringOrIntString String | StringOrIntInt Int`...

Or structural, as in TypeScript: `string | number`.

## Set

Given type t, is an unordered collection of t.

Can be emulated as a dictionary from t to unit, which tells that element is contained in a set.

## Relation

Parameterized by array of types x, contains a set of tuples of x.

Known as facts in Prolog.

SQL tables are not true relations, because they allow duplicates. They are more like bags.

## Bag

Given type t, contain bunch of t. Can push something and take something out.

## Tensors

Sometimes known as multidimensional arrays.

Parameterized by its size (a tuple of n numbers) and element’s type.

Present in array languages: NumPy (?), APL, BQN, J, TensorFlow (?).

Related: array.

## Type

In dependently typed languages, types can be values and values can be types. In langauges with union and intersection types, values can appear in types.

## Neural network

No idea what’s inside, sorry. Probably related to tensors.

# Questions

How would this work in a langauge with union types, how to determine if some type is worth having, given that many types can be emulated by other types?

What should happen in a language when illegal operations are performed?

Do arrays make C dependently typed? Does sizeof make C dependently typed?

What is the best way to represent functions as data?

## To-do

- Cryptography
- Discrete mathematics
- Type theory
- Symbolic computation
- Logic programming
