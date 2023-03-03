# TypeScript

- [TypeScript](#typescript)
- [命名規則](#命名規則)
- [README やコメントを書く習慣を](#readme-やコメントを書く習慣を)
- [フォーマッター](#フォーマッター)
  - [settings.json](#settingsjson)
  - [コメントの記述](#コメントの記述)
  - [コメントの記述例](#コメントの記述例)
- [プログラムをより美しく書くためには](#プログラムをより美しく書くためには)
  - [役割が同じ変数や関数などはまとめる](#役割が同じ変数や関数などはまとめる)
    - [OK](#ok)
    - [NG](#ng)
  - [間隔を意識する](#間隔を意識する)
    - [OK](#ok-1)
    - [NG](#ng-1)
  - [コメントを書く際は 1 行空ける](#コメントを書く際は-1-行空ける)
    - [OK](#ok-2)
    - [NG](#ng-2)
  - [関数を使用する際の渡す引数名を関数の引数名と合わせる](#関数を使用する際の渡す引数名を関数の引数名と合わせる)
- [順番](#順番)
  - [例 1: 関数](#例-1-関数)
    - [OK](#ok-3)
    - [NG](#ng-3)
- [早期リターン](#早期リターン)
- [ネストの削減](#ネストの削減)
  - [OK](#ok-4)
  - [NG](#ng-4)
- [ディレクトリーの基本構成](#ディレクトリーの基本構成)
- [構造体](#構造体)
  - [構造体への実装](#構造体への実装)
- [関数や変数の型](#関数や変数の型)
  - [変数の型](#変数の型)
  - [型エイリアス](#型エイリアス)
  - [ジェネリクス](#ジェネリクス)
- [テスト](#テスト)
- [エラーハンドリング](#エラーハンドリング)

# 命名規則

基本は以下を参考とする。
一部規約変更に関しては、フォーマッターの章を参照すること。

https://www.typescriptlang.org/docs/handbook/namespaces-and-modules.html#naming-conventions

ESLint で TypeScript のコードをフォーマットする際に、以下の設定を使用する。
https://amateur-engineer.com/code-formatter-prettier-eslint/

# README やコメントを書く習慣を

README やコメントが無ければ、どういった動作をするプログラムなのかを判断できない。それ故に、プログラムをトレースしなければどういった動作をするのか判断できない。

また、環境の移行や担当者の不在等により、README やコメント等が無いプロジェクトでは調査を行わなければならなくなる。

これらを回避するために、README やコメントを書き残す習慣を付ける。

# フォーマッター

フォーマッターを用いて、コードを整形する。

- Prettier - Code formatter

  Web 開発における基本のフォーマッター
  https://marketplace.visualstudio.com/items?itemName=esbenp.prettier-vscode

## settings.json

以下の設定で使用する。
特にセミコロンを使用しない設定は、コードの見た目がスッキリするために使用する。

また、文字列を記述する際、基本はシングルクォーテーションを使用する。変数を埋め込む場合は、バッククォートを使用する。

シングルクォーテーションを常用する理由は、US 配列でシングルクォーテーションを入力する際に、シフトキーを押さなくて済むためである。

これ以外は Prettier のデフォルト設定を使用する。

```json
{
  "editor.formatOnSave": true,
  "editor.inlineSuggest.enabled": true,
  "files.trimTrailingWhitespace": true,
  "files.insertFinalNewline": true,
  "editor.defaultFormatter": "esbenp.prettier-vscode",
  "typescript.updateImportsOnFileMove.enabled": "always",
  "prettier.semi": false,
  "prettier.singleQuote": true
}
```

## コメントの記述

簡単でかしこまらずに書く。その関数や変数ではどういった動作をしているのかを完結に書く。

関数や変数を書く前に、コメントで何をするかを定義し、その後に関数や変数を書き始めるのも良いかもしれない。

ただし、コメントを書くのは複雑なものに限り、書きすぎると可読性が損なわれるため、ほどほどに書くことが重要。

## コメントの記述例

# プログラムをより美しく書くためには

## 役割が同じ変数や関数などはまとめる

### OK

```ts
const [user, setUser] = useState()
const [oldUser, setOldUser] = useState()

const now = new Date()
const updatedAt = user.updatedAt
const createdAt = user.createdAt

useEffect(() => {}, [])
useEffect(() => {}, [])
```

### NG

```ts
const [user, setUser] = useState()

const [oldUser, setOldUser] = useState()

const now = new Date()
const updatedAt = user.updatedAt

const createdAt = user.createdAt

useEffect(() => {}, [])

useEffect(() => {}, [])
```

※ これらが複雑な式で成り立っている場合、コメントを記述し、## コメントを書く際は 1 行空ける を参考にする。

## 間隔を意識する

### OK

```ts
const now = new Date()
const updatedAt = user.updatedAt
const createdAt = user.createdAt

useEffect(() => {}, [])
useEffect(() => {}, [])
```

### NG

```ts
const now = new Date()
const updatedAt = user.updatedAt

const createdAt = user.createdAt

useEffect(() => {}, [])

useEffect(() => {}, [])
```

## コメントを書く際は 1 行空ける

### OK

```ts
const now = new Date()
const before = new Date('2023-03-01T00:00:00Z')

// 現在時刻より過去の時間をマイナスし、特定の時間を求める
const diff = now.getTime() - before.getTime()
const diffInMinutes = Math.floor(diff / (1000 * 60))

console.log(`The difference is ${diffInMinutes} minutes`)
```

### NG

```ts
const now = new Date()
const before = new Date('2023-03-01T00:00:00Z')
// 現在時刻より過去の時間をマイナスし、特定の時間を求める
const diff = now.getTime() - before.getTime()
const diffInMinutes = Math.floor(diff / (1000 * 60))

console.log(`The difference is ${diffInMinutes} minutes`)
```

## 関数を使用する際の渡す引数名を関数の引数名と合わせる

# 順番

変数や関数等の記述に関して、書く順番を意識すれば、より可読性が高いプログラムができると思われる。

## 例 1: 関数

以下の関数は立方体・直方体の体積を求める関数である。

以下の関数の場合、引数は 3 つである。

また、一般的に求める式は、縦 x 横 x 高さとなっている。

### OK

一般的な順番を意識している。

※ ここでは変数名を省略せずに書いているが、省略しても意味が伝わるのであれば省略してもよい。

```ts
const calcCubeArea = (depth, width, height) => {
  return depth * width * height
}
```

### NG

同じ答えになるが、順番を意識していない。

```ts
const calcCubeArea = (width, depth, height) => {
  return width * depth * height
}
```

# 早期リターン

早期リターンは、関数内で余分な処理を実行することなく、コードの効率性を向上させることが可能となる。

TypeScript において早期リターンを適用する場合、次のような点に留意する必要がある。

1. 関数の返り値の型が一意であることを確認する。
2. 条件式の比較演算子が正しいことを確認する。
3. 複数の早期リターンがある場合、それらが機能的に同等であることを確認する。

```typescript
const calculateTax = (price: number, taxRate: number): number => {
  if (price <= 0 || taxRate <= 0) {
    return 0
  }

  const tax = price * taxRate

  if (tax > 100) {
    return 100
  }

  return tax
}
```

# ネストの削減

ネストの削減は、可読性の向上やコードの保守性を高めるために重要な要素となる。

## OK

```typescript
const getDisplayName = (user: User) => {
  const fullName = `${user.firstName} ${user.lastName}`

  return user.nickname ? `${fullName} (${user.nickname})` : fullName
}
```

## NG

```typescript
const getDisplayName = (user: User) => {
  if (user.firstName && user.lastName) {
    if (user.nickname) {
      return `${user.firstName} ${user.lastName} (${user.nickname})`
    } else {
      return `${user.firstName} ${user.lastName}`
    }
  } else {
    return 'Anonymous'
  }
}
```

# ディレクトリーの基本構成

posts があれば、

- posts/
- posts/index.tsx
- posts/post.tsx

と作成する。

また post.tsx が肥大化、あるいは更にコンポーネントを分けたい場合は、

- posts/post/
- posts/post/index.tsx
- posts/post/SomeComponent.tsx

とする。

# 構造体

TypeScript において、オブジェクトを作成する場合、interface で定義をしておく。

```typescript
// 構造体の定義
interface Person {
  firstName: string
  lastName: string
  age: number
}

// インスタンスの作成
const person: Person = {
  firstName: 'John',
  lastName: 'Doe',
  age: 30,
}
```

## 構造体への実装

```typescript
interface Person {
  firstName: string
  lastName: string
  age: number
}

class PersonClass implements Person {
  constructor(
    public firstName: string,
    public lastName: string,
    public age: number
  ) {}

  getFullName() {
    return `${this.firstName} ${this.lastName}`
  }
}

const person = new PersonClass('John', 'Doe', 30)
console.log(person.firstName) // "John"
console.log(person.lastName) // "Doe"
console.log(person.age) // 30
console.log(person.getFullName()) // "John Doe"
```

# 関数や変数の型

関数や変数の型を定義する場合、以下のようにする。

```typescript
// 関数の型定義
type Add = (a: number, b: number) => number

const add: Add = (a, b) => a + b

// 変数の型定義
const number: number = 1
```

## 変数の型

基本的に右辺で型が推論されている。その場合、左辺の型は省略する。

推論されているのであれば、あえて左辺の型を定義する必要はない。

```typescript
// 以下は右辺で型が推論されているので、左辺の型は省略する
const number = 1

// 以下は右辺で型が推論されていないので、左辺の型を定義する必要がある
const person = {
  firstName: 'John',
  lastName: 'Doe',
  age: 30,
}

interface Person {
  firstName: string
  lastName: string
  age: number
}

const person: Person = {
  firstName: 'John',
  lastName: 'Doe',
  age: 30,
}
```

## 型エイリアス

型エイリアスは、型を別名で定義することができる。

以下のような場合に使用することが多い。

```typescript
type Persons = Person[]
```

## ジェネリクス

ジェネリクスは、型を引数として受け取ることができる。

これも頻繁に使用するため、覚えておく。

```typescript
const add = <T>(a: T, b: T): T => {
  return a + b
}

add<number>(1, 2) // 3
```

# テスト

# エラーハンドリング
