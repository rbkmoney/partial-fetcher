# Partial-fetcher

**The library for fetching data from endpoints that uses continuationToken.**

---

API answers something like this?

```typecript
Response {
	result: any[];
	continuationToken?: string;
}
```

Use a `partial-fetcher`!

---

Why `partial-fetcher` so great? Because supports things like `doAction`, `hasMore`, `fetchMore`.

---

### Installation

-   Add `.npmrc` file into your root directory in your project with this line

```
@rbkmoney:registry=https://npm.pkg.github.com/
```

-   Login into github npm registry ([Guide](https://help.github.com/en/github/managing-packages-with-github-packages/configuring-npm-for-use-with-github-packages#authenticating-to-github-packages 'Guide'))

-   Install `partial-fetcher` via

```sh
npm i --save @rbkmoney/partial-fetcher
```

---

### Usage

-   Extend your service class with `PartialFetcher` like this where `R` is result type and `P` search params type

```typescript
Service extends PartialFetcher<R, P>
```

-   Declare protected fetch method

```typescript
fetch(params: P, continuationToken: string): Observable<FetchResult<R>>
```

-   Search your items with `search` method, update items with `refresh`, load more with `fetchMore`.

-   Get your items from `searchResult$`, check if it has more with `hasMore$`, get loading state from `doAction$` and subscribe to errors with `errors$`.

-   **You're awesome!**
