# TypeScript

# README やコメントを書く習慣を

README やコメントが無ければ、どういった動作をするプログラムなのかを判断できない。それ故に、プログラムをトレースしなければどういった動作をするのか判断できない。

また、環境の移行や担当者の不在等により、README やコメント等が無いプロジェクトでは調査を行わなければならなくなる。

これらを回避するために、README やコメントを書き残す習慣を付ける。

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

// 現在時刻より過去の時間をマイナスし、特定の時間を求める
const result = now -
```

### NG

```ts
const now = new Date()
// 現在時刻より過去の時間をマイナスし、特定の時間を求める
const result = now -
```

## 関数を使用する際の渡す引数名を関数の引数名と合わせる

# 順番

変数や関数等の記述に関して、書く順番を意識すれば、より可読性が高いプログラムができると思われる。

## 例 1: 関数

以下の関数は立方体・直方体の体積を求める関数である。
以下の関数の場合、引数は 3 つである。
また、一般的に求める式は、
縦 _ 横 _ 高さとなっている。

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

# ネストの削減

if のやつ

```ts
if ()
```

# ディレクトリーの基本構成

posts があれば、
posts/
posts/index.tsx
posts/post.tsx

と作成する。

また post.tsx が肥大化、あるいは更にコンポーネントを分けたい場合は、
posts/post/
posts/post/index.tsx
posts/post/SomeComponent.tsx

とする。

# オブジェクト

{ uuid }
{ uuid: uuid }
