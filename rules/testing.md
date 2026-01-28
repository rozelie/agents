# Testing

Language-agnostic testing guidelines.

## Test Hierarchy

Always write tests with the following precedent:

1. End-to-end tests (tests across the stack with minimal mocking)
2. Integration tests (tests across multiple functions within a single service)
    - e.g. testing an API endpoint from request all the way to the response
3. Unit tests (tests an individual function)

**NEVER** write a unit test that verifies behavior already validated by an integration test.

Integration tests may duplicate behaviour already tested in an end-to-end test. This is to allow for quicker test feedback within services.

## Guidelines

- Tests should verify a single behaviour
- Tests should be named in the form of: "action + expected result'
    - Good example: `test_incorrect_password_shows_error_message`
    - Bad example: `test_password_fails`
