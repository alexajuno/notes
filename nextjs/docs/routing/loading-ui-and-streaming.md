# Loading UI and Streaming

## Instant Loading States

- Using `loading.js`
- `loading.js` will be nested inside `layout.js`, automatically wraps the `page.js` and all of its children in a &lt;Suspense&gt; boundary
- Navigation is interruptible, meaning changing routes does not need to wait for the content of the route to fully load before navigating to another route.
- Navigation is immediate, even with server-centric routing.

## Streaming with Suspense

- SSR renders all elements before sending it to the client
- Streaming with &lt;Suspense&gt; help delivering some elements earlier
- I still need more example to understand this

## SEO

- Something about Streaming not affecting SEO, but I don't understand much.

## Status Codes

