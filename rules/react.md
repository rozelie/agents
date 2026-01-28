# React

React frontend framework guidelines.

## Naming Conventions

- Use kebab-case for test IDs
    - Be descriptive and specific: `navbar-link-home` vs `link`
    - Include component context: `error-boundary-retry-button`

## Testing Attributes

All interactive elements should include `data-testid` attributes for testing:
```typescript
<button data-testid="submit-button">Submit</button>
```

*TODO:* Add more React guidelines