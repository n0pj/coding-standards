- [命名規則](#命名規則)
  - [ユーザー](#ユーザー)
  - [Rust x Diesel](#rust-x-diesel)
  - [TypeScript x Prisma](#typescript-x-prisma)
  - [PHP x Laravel](#php-x-laravel)
  - [フレームワーク未使用](#フレームワーク未使用)
- [ID](#id)
  - [メリット](#メリット)
  - [デメリット](#デメリット)

サーバーサイドのフレームワークに則る。

データベース名は "-" が使用できない場合があるため、基本的には "\_" を使用する。
しかし、AWS の RDB インスタンス等では、 "\_" が許可されていない場合があるため、"-" を使用し、対応する。

# 命名規則

## ユーザー

ユーザーは、データベース名に則り、同じ規則で命名する。また、環境ごとの区別をつけるため、環境名を付与する。
| Variable | Description |
| ---- | ----- |
| {env} | 環境名 [dev, stg, prod] |

ルートユーザーは
| DB name | Env | Example name |
| -------- | ---- | ----------------- |
| database_yellow | dev | database_yellow_dev |
| database-2 | dev |database-2-dev |

## Rust x Diesel

https://diesel.rs/guides/getting-started
| Kind | Example name |
| -------- | ----------------- |
| database | database |
| database | database_database |
| database | database-database |
| table | some_tables |
| column | some_column |

## TypeScript x Prisma

公式がチュートリアルで使用していたものを使用。
https://www.prisma.io/docs/concepts/components/prisma-migrate/migration-histories
| Kind | Example name |
| -------- | ----------------- |
| database | database |
| database | database_database |
| database | database-database |
| table | SomeTable |
| column | someColumn |

## PHP x Laravel

https://readouble.com/laravel/8.x/ja/migrations.html
| Kind | Example name |
| -------- | ----------------- |
| database | database |
| database | database_database |
| database | database-database |
| table | some_tables |
| column | some_column |

## フレームワーク未使用

一般的なデータベース命名規則を見たうえで判断。

| Kind     | Example name      |
| -------- | ----------------- |
| database | database          |
| database | database_database |
| database | database-database |
| table    | some_tables       |
| column   | some_column       |

# ID

ID, Identification は、昨今までは Int, BigInt の Increments の型で指定されることがほとんどだった。

最近になり、データ量の増加やパフォーマンス、セキュリティの観点から UUID v4 の採用が増えた気がしている。

そのため、ID に関して今後は UUID v4 を使用する。

ただし、システムの整合性を考える必要があるため、担当者との相談が必要。

マックデリバリーでは採用されていた。
https://gyazo.com/9065e757b3ce9c0223c328c804580db3

## メリット

1. 生涯衝突しない ( 唯一性 )

   別システムと合併した際も衝突しない唯一性を持つ。

1. 連番ではないため、推測が不可能 ( セキュリティ )
1.

## デメリット

1. デフォルトでインデックスが最適化されていない

   以下のように空きがあった場合、

   □□□□□□□□□□

   BigInt, Increments であれば以下のようになる。

   ■■■□□□□□□□

   しかし、UUID v4 の場合は連番ではないため、以下のようになる。

   □■□■□□□■□□

2. 長い

   1670ae7f-aad0-403a-9d25-30c33b49ab87

   のような ID が生成されるため、ユーザー向けとは言えない。
   しかし、これはコピーを可能にする UX の導入を行えば対策可能といえる。
   唯一性やセキュリティ等を考えたとき、導入したほうがよいと思われる。
