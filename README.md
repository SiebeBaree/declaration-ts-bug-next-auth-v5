# Declaration TypeScript Bug in NextAuth v5

When turning on `declararation` and `declarationMap` in the tsconfig.json NextAuth v5 beta 16 will give the following error:

```
The inferred type of 'auth' cannot be named without a reference to '../node_modules/next-auth/lib'. This is likely not portable. A type annotation is necessary.
```

The code works perfectly fine in dev mode but will cause build errors during deployment.

> The error happens in `src/auth.ts`

## Steps to reproduce:

1. `npx create-next-app@latest` (enable TypeScript)
2. `npm install next-auth@beta`
3. Create the `auth.ts` file like the installation guide recommends
4. Set the `declaration` and `declarationMap` to true in the `compilerOptions` of your tsconfig.json

This repository uses Bun but this error is the same on npm, pnpm with node.js runtime.
