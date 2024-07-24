# Data Fetching, Caching, and Revalidating

- Using fetch with async/await in server components, server actions and route handlers

## Caching data

- fetch data is automatically cached
- fetch ain't cached on Server Actions and Route Handlers with POST method

## Revalidating data

- about revalidation
- two ways of revalidate
  - time-based revalidation:  
    - in a page: fetch('https://...', { next: { revalidate: 3600 } })
    - route segment config
  - on-demand
    - 