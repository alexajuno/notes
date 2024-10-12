# Server and Client Composition Patterns

## When to use

Description [here](https://nextjs.org/docs/app/building-your-application/rendering/composition-patterns)

## Server Component Patterns

- Sharing data between components
  - using `fetch` or `cache` since data is automatically memoized
- Keeping server-only code out of Client Environment
  - `server-only` and `client-only`
- Using third-party packages and Providers
  - some packages is only available in client components
  - workaround by wrapping it within a file start with `use client`
- Using Context Providers

## Client Components

- Moving Client Components down the tree
- Passing props from Server to Client Components

## Interleaving Server and Client Components
