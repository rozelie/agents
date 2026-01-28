# Python

Python programming language guidelines.

## Packages

### `__init__.py`

*TODO:* Add instructions on what to do/not to do within `__init__.py` modules

## Modules

Python constructs should always be defined in this order within a module:

1. imports
2. logger instantiation
3. constants
4. classes
5. public functions
6. private functions

## Functions

Always prefer using functions over classes.

Functions should always:

- start with a verb
- have a single, clear responsibility
- be idompotent and produce no side effects whenever possible
- be private (be prefixed with a leading underscore) if the function is only used within the module it is defined in

Functions should never:

- return tuples with more than two values
    - instead wrap the return value in a `dataclass`
- be nested within each other
    - the only exception is `fun

## Classes

Always prefer using a `dataclass` over a normal class.

## Typing

All Python constructs must be fully typed and narrowly typed as possible.

If `typing.Any` is used, it must include either a:

1. `NOTE` comment describing why `Any` must be used
2. `TODO` comment to replace `Any` with a concrete type

*TODO:* Add instructions on when to use future annotations and built-in types vs. importing

## Docstrings

Always follow existing code patterns for docstrings. 

Examples:

- The code generally does not use docstrings -> do not write new docstrings
- The code only writes a summary in docstrings -> write only a summary in new docstrings
- The code includes descriptions of parameters, documents exceptions that can be raised, and is overall very verbose -> write verbose docstrings matching that style
- The code does not include module-level docstrings -> do not write module-level docstrings
- The code includes module-level docstrings -> write module-level docstrings

## Testing

- Always use the `mocker` fixture from the `pytest-mock` package in favor of `unittest.mock`

*TODO:* Add more testing guidelines

## Other

- *TODO:* Encourage functools.wraps
- *TODO:* SCREAMING_SNAKE_CASE for constants
- *TODO:* In `except` blocks, always either re-raise or log it, NEVER swallow an exception without some logging event that it occurred
- *TODO:* Always add a newline after a dedent, except for try/except blocks that try only a single line of code
