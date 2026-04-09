# View Composition

Adopt the mindset of a cinematographer:
- Size: The bigger something appears, the more important it is perceived to the viewer.
- Focus: What is the focal point of the scene?

Also, adopt the mindset of a product designer:
- Habits: Most apps are similar because users don't have to learn to use another app.

Rules:
- A `<h1>` is required to determine what the main topic of the view is.
- Headings must stand out from other elements.
- There is at max one CTA, the rest are secondary.
- Use existing popular layouts and view compositions.

## Developer Happiness

Rules:
- Extend the "Prefer Short Functions" limit to 100 lines for components.
- When many views (at least 3) share a similar structure, it's time to create a reusable layout.
- Prefer contexts for prop drilling, especially when the props make sense on the view-level.
    ```tsx
      const ChatLayout = () => (
        <ChatDataLoader>
          {(chat) => (
            <ChatContext value={{ chat }}>
              {/* ... */}
            </ChatContext>
          )}
        </ChatDataLoader>
      )
    ```