# Next.js 15 App Directory: Unexpected Behavior with Dynamic Routes and `fallback: true`

This repository demonstrates an unexpected behavior in Next.js 15's App Directory when using dynamic routes with `fallback: true`.  The issue occurs when navigating to a route that doesn't yet exist, leading to incorrect rendering or behavior.

**Bug Description:**

When `fallback: true` is used in a dynamic route within the app directory, and a request is made for a route that doesn't exist, the `getStaticProps` or `getServerSideProps` function may not be called, resulting in an unexpected empty page or 404 error. This behavior deviates from the expected behavior of `fallback: true` in the pages directory, which gracefully handles these cases.

**Steps to Reproduce:**

1. Clone this repository.
2. Run `npm install`.
3. Run `npm run dev`.
4. Navigate to `/post/nonexistent`. You will see unexpected behavior

**Expected Behavior:**

The `getStaticProps` or `getServerSideProps` function should be called (or at least the fallback page should be rendered), allowing for graceful handling of non-existent routes.

**Actual Behavior:**

The `getStaticProps` or `getServerSideProps` function is not called, resulting in an empty page or 404 error.

**Workaround:**

This issue may be related to the internal implementation of the App Directory in Next.js 15.  Alternative ways of achieving the desired functionality such as using data fetching mechanisms within the component or other approaches are likely workarounds.