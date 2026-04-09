# Tailwindcss

## Developer Happiness

Rules:
- Avoid creating custom classes.
- Put all utility classes inside `className` without encapsulating them in component classes.

## Common Patterns

### Centering an element

```tsx
  <div className="size-full flex justify-center items-center">
    {/* Element */}
  </div>
```

### Growing a child element

```tsx
  // Horizontally
  <div className="flex flex-row"> {/* Parent */}
    <div className="shrink-0">{/* Fixed-size child element*/}</div>
    <div className="min-w-0 grow">{/* Growing child element */}</div>
  </div>

  // Vertically
  <div className="flex flex-col"> {/* Parent */}
    <div className="shrink-0">{/* Fixed-size child element*/}</div>
    <div className="min-h-0 grow">{/* Growing child element */}</div>
  </div>
```

## Dark Mode

Dark mode is enabled using the `dark` class.