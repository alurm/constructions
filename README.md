# Idioms, types and constructions in programming languages

Of course, everything can be interpreted via a Turing machine or lambda calculus. Point is to list idiomatic constructions used in programming langauges.

Being type theoretically correct is not a goal.

This is not about dynamic and static languages. This is not about compilation, interpretation or preprocessing.

This is a record of my understanding of this as of March of 2023.

## Unit

This type exists because it’s value and type is unique.

Haskell example (`()` is the unit): `putStrLn :: String -> IO ()`.

## Nil

This type exists because it's value is different. Sometimes putting it somewhere causes a error.

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

## Other numbers

Floating point numbers, rational number, complex numbers, irrational numbers, etc.

Many real computers operate on numbers of limited size. Sometimes this limits the programmer.

## Array of bits

Imply size of an array.

Many computers use this. Many assembler use this. Many assemblers are untyped. Code is data, data is code.

## Directed array of bits

https://en.wikipedia.org/wiki/Endianness

## Name

Tcl exists there, it’s the only type there. Other data structures are built upon this. Interpreter optimizes as it can. Code is data, data is code.

## Linked list

Parameterized by type of it’s elements.

Usually built upon pointers.

Scheme and some other LISPs exists there. “LISP” means “list processor”. Other data structures are present in Scheme (atoms). Code is data, data is code.

Interestingly enough, often lambdas can’t be looked into.

## Graphs, trees, hash trees, etc.

They exist too, yes.

Many immutable data structures use trees under the hood.

## Tuple

Parameterized by array of types x, contains values of each of the types in x.

## Array

Sometimes known as an array of one dimension.

Parameterized by type of it’s elements.

Arrays is a dictionary from numbers to elements of the array.

## Slice

Array and its length.

## Structure

Can't be expanded after definition.

Maps offsets (in the language: names) to structure elements.

In C: `struct`.

## Name space

Map names to values.

## Pair

Given types a and b, allows accessing both of them (commonly known as “left” and “right”).

## Dictionary

Given k and v, maps k to v.

Example: tables in Lua. Keys can be anything except nil and nan.

## Function

Given types k and v, maps k to v.

From perspective of a mathematician, dictionaries and functions are the same.

## Intersection

Given n types, contains intersection of them. Contrains.

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

Parameterized by it’s size (a tuple of n numbers) and element’s type.

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
