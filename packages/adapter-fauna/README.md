<p align="center">
   <br/>
   <a href="https://authjs.dev" target="_blank">
   <img height="64px" src="https://authjs.dev/img/logo/logo-sm.png" /></a>&nbsp;&nbsp;&nbsp;&nbsp;<img height="64px" src="https://raw.githubusercontent.com/nextauthjs/adapters/main/packages/fauna/logo.svg" />
   <h3 align="center"><b>Fauna Adapter</b> - NextAuth.js</h3>
   <p align="center">
   Open Source. Full Stack. Own Your Data.
   </p>
   <p align="center" style="align: center;">
      <img src="https://github.com/nextauthjs/next-auth/actions/workflows/release.yml/badge.svg?branch=main" alt="Build Test" />
      <a href="https://www.npmjs.com/package/@next-auth/faunadb-adapter" target="_blank"><img src="https://img.shields.io/bundlephobia/minzip/@next-auth/fauna-adapter/next" alt="Bundle Size"/></a>
      <a href="https://www.npmjs.com/package/@next-auth/faunadb-adapter" target="_blank"><img src="https://img.shields.io/npm/v/@next-auth/fauna-adapter/next" alt="@next-auth/fauna-adapter Version" /></a>
   </p>
</p>

## Overview

This is the Fauna Adapter for [`auth.js`](https://authjs.dev). This package can only be used in conjunction with the primary `auth.js` package. It is not a standalone package.

You can find the Fauna schema and seed information in the docs at [authjs.dev/reference/adapters/fauna](https://authjs.dev/reference/adapters/fauna).

## Getting Started

1. Install `faunadb`, `next-auth` and `@next-auth/fauna-adapter`

```js
npm install faunadb next-auth @next-auth/fauna-adapter@next
```

2. Add this adapter to your `pages/api/[...nextauth].js` next-auth configuration object.

```js
import NextAuth from "next-auth"
import { Client as FaunaClient } from "faunadb"
import { FaunaAdapter } from "@next-auth/fauna-adapter"

const client = new FaunaClient({
  secret: "secret",
  scheme: "http",
  domain: "localhost",
  port: 8443,
})

// For more information on each option (and a full list of options) go to
// https://authjs.dev/reference/configuration/auth-options
export default NextAuth({
  // https://authjs.dev/reference/providers/oauth-builtin
  providers: [],
  adapter: FaunaAdapter(client)
  ...
})
```

## Contributing

We're open to all community contributions! If you'd like to contribute in any way, please read our [Contributing Guide](https://github.com/nextauthjs/next-auth/blob/main/CONTRIBUTING.md).

## License

ISC
