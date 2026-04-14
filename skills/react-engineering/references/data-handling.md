# Data Handling

## Terminology

- Data query component: a React component whose sole purpose is to fetch data and pass them to its children
- Data mutation component: a React component whose sole purpose is to build data mutation functions and pass them to its children

## Queries

Use TanStack Query ([Docs](https://tanstack.com/query/latest/docs/framework/react/overview)).

Rules:
- Keep in the same file: data query function(s), data query component.

Example:
```tsx
/* @/data/queries/chat.tsx */
// ...
const ChatQuery = ({ chatId, children }) => {
  const chat = getChat(chatId)
  return children(chat)
}

/* @/routes/chats/$chatId.tsx */
// ...
const ChatView = () => {
  const { chatId } = Route.useParams()
  return (
    <ChatQuery chatId={chatId}>
      {(chat) => (
        <MessageList>
          {(chat.message.map((message) => (
            <MessageItem>
              {message}
            </MessageItem>
          )))}
        </MessageList>
      )}
    </ChatQuery>
  )
}
```

## Mutations

Use TanStack Query's Mutations ([Docs](https://tanstack.com/query/latest/docs/framework/react/guides/mutations)).

Rules:
- Keep in the same file: data mutation function(s), data mutation component.

Example:
```tsx
/* @/data/mutations/create-message.tsx */
// ...
const CreateMessageMutation = ({ chatId, children }) => {
  const createMessage = (formData: FormData) => {}
  return children(createMessage)
}

/* @/routes/chats/$chatId.tsx */
// ...
const ChatView = () => {
  const { chatId } = Route.useParams()

  return (
    <CreateMessageMutation chatId={chatId}>
      {(createMessage) => (
        <form action={createMessage} />
      )}
    </CreateMessageMutation>
  )
}
```

### Form Handling

Rules:
- Use React API for form handling ([Docs](https://react.dev/reference/react-dom/components/form)).
- Delegate form validation to the backend upon submission.
