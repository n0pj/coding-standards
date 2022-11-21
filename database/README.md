# 命名規則

サーバーサイドのフレームワークに則る。

データベース名は "-" が使用できない場合があるため、基本的には "\_" を使用する。
しかし、AWS の RDB インスタンス等では、 "\_" が許可されていない場合があるため、"-" を使用し、対応する。

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
