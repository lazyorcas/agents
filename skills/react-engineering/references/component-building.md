# Component Building

## Developer Happiness

Rules:
- Prefer function definitions before rendering, unless it is an obvious one-liner e.g. `onChange={(event) => update(event.target.data)}`.
- Extend the "Prefer Short Functions" limit to 100 lines for components.

### File Naming

Each component's filename must have a suffix that contains the component type.
- `Message.tsx` -> `MessageItem.tsx` or `MessageCard.tsx`
- `Messages.tsx` -> `MessageList.tsx` or `MessageCardList.tsx`

## Terminology

- UI component (`@/components/ui`): a reusable component
    - Base UI component: a shadcn component
    - Custom UI component: a component that stitch together other UI components
- View component (`@/components/view`): a view-specific component

### Examples

```tsx
// Base UI components
import { Input, Label } from "@/components/ui"

// Custom UI component - @/components/ui/chat-input.tsx
const ChatInput = () => (
  <div>
    <Label>Message: </Label>
    <Input />
  </div>
)

// View component - @/components/view/chat/chat-header.tsx
const ChatHeader = () => {
  const { chat } = useContext(ChatContext)
  return (
    <header>
      <h2>{chat.title}</h2>
      <p>{chat.lastUpdatedAt}</p>
    </header>
  )
}
```

## Before creating a component

Ask yourself:
- What is the purpose of this component?
- What type of component is this?

## Core Workflows

### Creating a new UI component

1. Search for existing components in [the shadcn component library](https://ui.shadcn.com/docs/components).
2. Ask yourself: Is there a single shadcn component that can fulfill the purpose of this component?
3. Build a base or custom UI component.
