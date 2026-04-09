---
name: rails-style-backend-engineering
description: Backend engineering in Rails/37signals style. Use this skill when the author asks to work with the backend in a 
---

# Backend Engineering

## Setup

You are required to help the author find a skill for this particular backend framework.

## Developer Happiness

The author is an advocate of Ruby on Rails and 37signals dev philosophy.

Rules:
- Prefer validations, rules, and logic in models.
    - Don't use service objects.
    - Don't use repositories.
- Prefer CRUD operations. Otherwise, create an application-layer model (not tied 1:1 to a DB entity).
  ```rb
    # Bad
    class Message < ApplicationRecord
      def create_multiple_messages
        # ...
      end
    end

    # Good
    class Message < ApplicationRecord; end
    class BatchMessageTask
      def create
        # ...
      end
    end
  ```
- Prefer separation of concerns to maintain the "Prefer Short Files" rule.
  ```rb
    class Message
      include Deleteable
      include Referenceable
    end
  ```
- Adopt Rails's naming convention:
    - Tables in Plural Form e.g. `messages`, `users`
    - Models in Singular Form e.g. `Message`, `User`
    - Concerns often named with adjectives ending in `-able` or `-ible` e.g. `Deletable`

## Security

- Do not trust the frontend.
- Do not print paths, tokens, or secrets in errors/logs.
- Do not store secrets from config or keychain in source.

Take extra care around actions you can't undo (e.g., auth, deletes).

## Risk Appetite

Always mention risks.

- Low → small change.
- Medium → handle edge cases explicitly.
- High (deletes, auth, unrecoverable changes) → spell out assumptions and failure paths.

## Out of Scope

The following topics are out of scope unless explicitly requested.

- Database indexing & constraints
- Caching
- Background jobs
- Performance optimization
- Writing tests

## References

You are not required to read these webpages.
- https://dev.37signals.com/active-record-nice-and-blended/
- https://dev.37signals.com/good-concerns/
- https://dev.37signals.com/vanilla-rails-is-plenty/