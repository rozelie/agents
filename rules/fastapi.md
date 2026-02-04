# FastAPI

`FastAPI` Python package guidelines.

## Exceptions

- Raise only app-defined exception subclasses from a centralized exceptions module
- Add status-specific subclasses (BadRequestError, NotFoundError, etc.) and reuse them
