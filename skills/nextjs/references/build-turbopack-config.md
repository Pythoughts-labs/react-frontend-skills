---
title: Enable Turbopack File System Caching
impact: CRITICAL
impactDescription: significantly faster cold starts and restarts on large apps
tags: build, turbopack, caching, development
---

## Enable Turbopack File System Caching

Next.js 16 makes Turbopack the default bundler. Its filesystem cache for development is a **beta opt-in** that persists compiler artifacts on disk between runs, significantly speeding up compile times across restarts on large projects. Enable it explicitly — it is not on by default.

**Incorrect (removed config key / non-existent option):**

```typescript
// next.config.ts
const nextConfig = {
  experimental: {
    // `experimental.turbo` was renamed to top-level `turbopack` in 15.3
    // and is removed in Next.js 16. `persistentCaching` is not a real option.
    turbo: {
      persistentCaching: false,
    },
  },
}
```

**Correct (opt into FS caching; configure loaders under top-level `turbopack`):**

```typescript
// next.config.ts
const nextConfig = {
  experimental: {
    // Beta opt-in: persist Turbopack artifacts across dev restarts
    turbopackFileSystemCacheForDev: true,
  },
  // Custom loaders live under the top-level `turbopack` key (not `experimental.turbo`)
  turbopack: {
    rules: {
      '*.svg': {
        loaders: ['@svgr/webpack'],
        as: '*.js',
      },
    },
  },
}
```

**Development command:**

```bash
# Turbopack is the default bundler in Next.js 16
next dev

# Opt out to webpack only if you rely on a custom webpack setup
next dev --webpack
```

**Note:** Filesystem caching is still beta. Turbopack writes its cache under `.next/cache`, which is already gitignored — keep it that way so the cache stays local.

Reference: [Next.js 16 Release Notes](https://nextjs.org/blog/next-16)
