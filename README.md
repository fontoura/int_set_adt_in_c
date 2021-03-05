# Minimal integer set in C
This is an implementation of the 'set' Abstract Data Type (ADT) in plain C.

This code is meant to be friendly for unexperienced programmers - it may perform minimal safety checks when handling pointers.

In order to enable safety checks, please keep the `SAFETY_CHECKS_ON` definition on the header file. In order to disable them, please remove this definition.

## Usage

In order to create an integer set, create a variable of type `int_set` and initialize it with `EMPTY_INT_SET`.

```C
int_set myset = EMPTY_INT_SET;
```

In order to add an element, use the `int_set__add` function. Since the structure is a set, it does not allow duplicates. Adding a duplicate value does not issue an error, and is merely a 'no-op'.

```
int_set__add(&myset, 1);
```

In order to remove an element, use the `int_set__remove` function. Removing a value which is not within the set does not issue an error, and is merely a 'no-op'.

```
int_set__remove(&myset, 2);
```

In order to check whether the set contains a given element, use the  `int_set__contains` function.

```
if (int_set__contains(&myset, 3))
{
    // do something
}
else
{
    // do something else
}
```

In order to check the length (or 'size') of the set (that is, the number of elements), use the `int_set__lenght` function.

```
int l = int_set__lenght(&myset);
```

In order to read an element from the set, use the `int_set__get` function. This function takes an index as input.

```
int v = int_set__get(&myset, 0);
```

In order to clear the set (remove all elements), use the `int_set__clear` function. This function should be used when the set will no longer be used, as it frees all dyamically alocated memory used by the set.

```
int_set__clear(&myset);
```

## License
This library was released under the MIT license.
