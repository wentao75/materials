# SWR

下面是去年底开始出现的一个 React Hook 组件 SWR，基于 Hook 方式，非常有用和好用的组件，Vue 也有 Composition API 移植，可以参考[swrv](https://github.com/Kong/swrv)

SWR is a React Hooks library for remote data fetching.

The name “SWR” is derived from stale-while-revalidate, a cache invalidation strategy popularized by HTTP RFC 5861.
SWR first returns the data from cache (stale), then sends the fetch request (revalidate), and finally comes with the up-to-date data again.

It features:

-   Transport and protocol agnostic data fetching
-   Fast page navigation
-   Revalidation on focus
-   Interval polling
-   Request deduplication
-   Local mutation
-   Pagination
-   TypeScript ready
-   SSR support
-   Suspense mode
-   React Native support
-   Minimal API

...and a lot more.

With SWR, components will get a stream of data updates constantly and automatically. Thus, the UI will be always fast and reactive.
