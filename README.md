# coding-standards

筆者が使用する各種規約をまとめたものである。

- [coding-standards](#coding-standards)
- [コーディング規約に関して](#コーディング規約に関して)
- [コーディング環境](#コーディング環境)
  - [Visual Studio Code](#visual-studio-code)
  - [WSL](#wsl)
- [プログラムを記述する際はフォーマッターを](#プログラムを記述する際はフォーマッターを)
- [VS Code でよく使用する拡張機能](#vs-code-でよく使用する拡張機能)

# コーディング規約に関して

筆者もソースコードの可読性や、今後のメンテナンスを考えないコード等を書いてしまい、酷いことになったこともあった。また、エンジニアそれぞれで書き方が違い、ソースコードを読むのに苦労したりもした。
それらを繰り返さないためにも、コーディング規約、命名規則等の取り決めなどを導入するようにした。

TypeScript や Rust などの言語を別の表現に変えると、日本語や英語などの言語だろう。日本語や英語には、文章の書き方や文法、書き順や語彙力があるように、プログラムにも存在する。

人によって文章が変わるように、プログラムの階層構造、コンポーネントやモジュールの依存関係などが変わる。

人によって字や書き順が変わるように、プログラムのインデントや処理の順番などの書き方も変わる。

語彙力があるように、プログラムでは三項演算子やクロージャー、フレームワーク等が使用できるかに関わってくるであろう。
このように、考えると色々共通点がある。

字が汚い人の文章は見たいと思うだろうか。間違っていた場合、訂正して返したくなるだろうか。もちろん、モノ好きな人ではない限り、見たくはないし、赤ペンでレ点を書くだけだろう。プログラミング言語にあるコーディング規約や命名規則はこのためにあると言える。

秩序のないプログラムはいずれ破綻する。

# コーディング環境

## Visual Studio Code

プラグインが豊富で、これ 1 つでなんでも解決。
他の環境を使用しても良いが、プラグイン関係が同じ設定とならない場合は、Visual Studio Code を使用すること。
https://azure.microsoft.com/ja-jp/products/visual-studio-code/

## WSL

基本的にリリース先は Linux 環境となるため、開発環境も Linux で行うべきである。

推奨の Linux ディストリビューションは Ubuntu 最新版。

https://docs.microsoft.com/ja-jp/windows/wsl/install

※ Mac では bash が使用できるため、その環境でもよい

# プログラムを記述する際はフォーマッターを

フォーマッターは、コードの見た目や書き方に一定のルールを持たせることができる。これにより、コードの可読性が向上し、コードレビューの際にも読みやすくなる。

また、フォーマッターを使用することで、コードの品質を維持することができる。フォーマッターが設定されたルールに沿ってコードを整形することで、タブやスペースの使い方、改行の位置などが一貫していることが保証される。これにより、コードの品質が一定水準以上であることを確認することができる。

また、フォーマッターを使用することで、コードを手動で整形する手間やミスを省くことができる。フォーマッターは、ルールに沿った形でコードを自動的に整形するため、コーディングに集中できるようになる。そのため、効率的な開発を行うことが可能となる。

# VS Code でよく使用する拡張機能

- Prettier - Code formatter

  Web 開発における基本のフォーマッター
  
  https://marketplace.visualstudio.com/items?itemName=esbenp.prettier-vscode

- Apollo GraphQL

  https://marketplace.visualstudio.com/items?itemName=apollographql.vscode-apollo

- indent-rainbow

  インデントの深さによって色付けをしてくれる
  
  https://marketplace.visualstudio.com/items?itemName=oderwat.indent-rainbow

- Live Share

  ペアプログラミングに最適
  
  https://marketplace.visualstudio.com/items?itemName=MS-vsliveshare.vsliveshare

- Markdown Preview Mermaid Support

  マークダウンでマーメイド記法がプレビューできる
  
  https://marketplace.visualstudio.com/items?itemName=bierner.markdown-mermaid

- Prisma

  https://marketplace.visualstudio.com/items?itemName=Prisma.prisma

- Rainbow CSV

  CSV のカラムごとに色付けをしてくれる
  
  https://marketplace.visualstudio.com/items?itemName=mechatroner.rainbow-csv

- rust-analyzer

  https://marketplace.visualstudio.com/items?itemName=rust-lang.rust-analyzer

- Markdown All in One

  マークダウンでドキュメントを書く際、長くなる場合はこの拡張機能の目次機能を使用する
  
  https://marketplace.visualstudio.com/items?itemName=yzhang.markdown-all-in-one
