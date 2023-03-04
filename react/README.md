# React.js

# 基本的に TypeScript を用いる

言わずもがな、TypeScript を用いる。

ただし、プロジェクトにより導入が難しい場合は、担当者との相談を行う。

## 規約は TypeScript の規約に則る

規約は、TypeScript の規約に則る。

typescript/README.md に記載されている規約を参照する。

# コンポーネントにコメント

TypeScript の規約にも記載されているが、コンポーネントにはコメントを記入する。

```typescript
/**
 * コンポーネントの説明
 */
const Component = () => {
  return <div>コンポーネント</div>
}
```

# コンポーネントの命名

コンポーネントの命名は、以下の規約に従う。

- コンポーネントは、大文字から始まるキャメルケースで命名する
- コンポーネントのファイル名は、コンポーネント名と同じにする
- コンポーネントのフォルダ名は、コンポーネント名と同じにする

```typescript
// コンポーネントの定義
const HelloComponent = () => {
  return <div>Hello コンポーネント</div>
}
```

コンポーネントのファイル名

HelloComponent.tsx

コンポーネントのフォルダ名

HelloComponent/

# コンポーネントのフォルダ構成

コンポーネントのフォルダ構成は、以下の規約に従う。

- コンポーネントのフォルダは、pages/ または components/ に配置する
- コンポーネントのフォルダ名は、コンポーネント名と同じにする
- コンポーネントのファイル名は、index.tsx または、コンポーネント名.tsx にする

原則、上記に従うが、コンポーネントが多くなり、フォルダが増えてしまう場合は、フォルダを分割する。

例: リスト系のコンポーネントを components/ に配置する場合

- components/
- components/List/
- components/List/index.tsx ( List.tsx として扱われる、親コンポーネント )
- components/List/Item.tsx ( List の子コンポーネント )

例: 単体のコンポーネントを components/ に配置する場合

- components/
- components/HelloComponent.tsx
