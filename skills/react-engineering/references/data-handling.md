# Data Handling

## Terminology

- Data loader (`@/data-loaders`): a React component whose sole purpose is to fetch data and pass it to its children

## Queries

Use TanStack Query ([Docs](https://tanstack.com/query/latest/docs/framework/react/overview)).

## Mutations

Use TanStack Query's Mutations ([Docs](https://tanstack.com/query/latest/docs/framework/react/guides/mutations)).

### Form Handling

Rules:
- Use React API for form handling ([Docs](https://react.dev/reference/react-dom/components/form)).
- Delegate form validation to the backend upon submission.

## Data Loader

Example:
```tsx
import { MessageList } from "@/components"

const ChatDataLoader = ({ chatId, children }) => {
  const chat = getChat(chatId)
  return children(chat)
}

const ChatView = () => (
  <ChatDataLoader>
    {(chat) => (
      <MessageList>
        {(chat.message.map((message) => (
          <MessageItem>
            {message}
          </MessageItem>
        )))}
      </MessageList>
    )}
  </ChatDataLoader>
)
```