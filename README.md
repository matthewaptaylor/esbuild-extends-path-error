# esbuild-extends-path-error

## Quick Start

To get it running, follow the steps below:

### Setup dependencies

```bash
# Install dependencies
pnpm install
```

### Reproduce the error

Attempt to build `apps/client`:

```bash
cd apps/client
pnpm build
```

You will notice that it does not build, because `packages/shared/src/index.ts` uses an import alias when importing from `~shared/foo` which it cannot resolve. However, if you modify the extends field in `apps/client/tsconfig.json` and replace `@repo/tsconfig/base` with `../../tooling/typescript/base.json`, it will resolve `~shared/foo` and build successfully.
