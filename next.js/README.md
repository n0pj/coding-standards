# Next.js

- [Next.js](#nextjs)
- [基本的に React.js x TypeScript を用いる](#基本的に-reactjs-x-typescript-を用いる)
  - [規約は TypeScript の規約に則る](#規約は-typescript-の規約に則る)
  - [React.js の規約に則る](#reactjs-の規約に則る)
- [ディレクトリー構成](#ディレクトリー構成)

# 基本的に React.js x TypeScript を用いる

## 規約は TypeScript の規約に則る

規約は、TypeScript の規約に則る。

typescript/README.md に記載されている規約を参照する。

## React.js の規約に則る

React.js の規約に則る。

react/README.md に記載されている規約を参照する。

# ディレクトリー構成

以下のような構成が好ましい。

```typescript
.
├── public
│   ├── favicon.ico
│   ├── images
│   │   └── logo.svg
│   └── robots.txt
├── src
│   ├── components
│   │   ├── atoms
│   │   │   ├── Button
│   │   │   │   ├── index.tsx
│   │   │   │   └── styles.module.scss
│   │   │   └── Input
│   │   │       ├── index.tsx
│   │   │       └── styles.module.scss
│   │   ├── molecules
│   │   │   └── Form
│   │   │       ├── index.tsx
│   │   │       └── styles.module.scss
│   │   └── organisms
│   │       └── Header
│   │           ├── index.tsx
│   │           └── styles.module.scss
│   ├── pages
│   │   ├── _app.tsx
│   │   ├── _document.tsx
│   │   ├── _error.tsx
│   │   ├── index.tsx
│   │   └── styles.module.scss
│   ├── styles
│   │   ├── global.scss
│   │   └── variables.scss
│   └── utils
│       └── api.ts
├── .eslintrc.js
├── .gitignore
├── .prettierrc.js
├── next-env.d.ts
├── next.config.js
├── package.json
├── README.md
├── tsconfig.json
└── yarn.lock
```
