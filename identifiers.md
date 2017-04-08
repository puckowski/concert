# Identifiers

Identifiers are any sequence of uninterrupted characters separated by space characters.

## const identifiers

Concert stores const identifiers in a location separate from all other identifiers. By default, Concert does not verify that an identifier is unique upon declaration. Therefore, it is possible to have duplicate identifiers in the same scope. For example, the same identifier could reference a value and reference a const value.
