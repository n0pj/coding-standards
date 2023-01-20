# coding-standards

筆者が使用する各種規約をまとめたものである。

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

# プログラムを記述する際はフォーマッターを
