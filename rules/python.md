# Python

Python programming language guidelines.

## Packages

### `__init__.py`

*TODO:* Add instructions on what to do/not to do within `__init__.py` modules

## Modules

- Keep declarations ordered:
    1. imports
    2. logger instantiation
    3. constants
    4. classes
    5. public functions
    6. private functions
- Prefer splitting modules once they exceed one major responsibility
- Prefer modules to be named a single word
- Prefer a `utils.py` module for catch-all, reusable utilities that have no other clear module to be in

1. imports
2. logger instantiation
3. constants
4. classes
5. public functions
6. private functions

## Functions

- Always prefer using functions over classes
- Prefer small orchestration functions that delegate to focused private function
- Keep private functions module-private (`_name`) unless shared across modules

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

- Prefer `dataclass` for pure data containers
- Prefer `pydantic` models for validation/serialization boundaries

## Typing
- Fully type all functions, including private one
- Avoid `Any`. If unavoidable, require either a:
    - `NOTE` comment describing why `Any` must be used
    - `TODO` comment to replace `Any` with a concrete type
- When a function always raises, annotate as `NoReturn`
- For parsed/untrusted data, validate into typed models early (do not pass raw dicts deep into logic).

*TODO:* Add instructions on when to use future annotations and built-in types vs. importing

## Errors and Exceptions

- In `except` blocks, always re-raise with context or log and raise; never silently swallow

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
