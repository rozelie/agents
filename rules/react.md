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

## Routing & Navigation

- For internal app navigation, always use react-router-dom Link/NavLink, never raw <a href="/...">
- Reserve <a> for external URLs only, and include target="_blank" + rel="noopener noreferrer" when opening a new tab
- Do not create React.lazy(...) inside render paths; define lazy components at module scope or memoize once to keep component identity stable

## State & Data Source Consistency

- Persist selection state by stable IDs, not display labels/names

## List Rendering

- Never use array index as React key for dynamic lists (add/remove/reorder/filtered lists)
- Prefer stable keys from backend IDs; if unavailable, use a deterministic composite key from stable fields

## Hooks & Effects

- Never call hooks conditionally or after early returns
- Any setTimeout/setInterval created in components must be cleaned up on unmount
- Zustand selectors: subscribe to only needed slices instead of whole-store objects to reduce rerenders

## DRY & Component Reuse

- Before creating a component in a feature folder, check for an existing shared equivalent in src/components or another feature
- If UI/logic is repeated in 2+ places, extract a shared component or utility
- Use “compatibility re-export” files when moving shared components to avoid churny imports

## Page Layout Consistency

- Use shared page-shell/layout primitives for container spacing and title patterns
- Use shared primitives for repeated UI patterns (error alerts, external links, section headers) rather than copy-pasting class strings

## Large Component Guardrails

- Aim to split components once they grow past a practical size threshold (for example: >300-400 lines or >3 distinct responsibilities)
- Keep page components focused on orchestration; move dense UI blocks and formatting utilities into dedicated subcomponents/modules