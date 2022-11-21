# Sass

## id セレクタを使用しない

運用面に置いて、id セレクタは使用するべきでない。
id に style を割り当てた場合、class による上書きが不可能となる。

## 初期要素に対しては Reset CSS 以外の style を割り当てない

Reset CSS はメジャーなものを使用する。Reset CSS による初期要素に対してのスタイリングは良いが、それ以外はオリジナルの class を作成すること。
以下のように破壊的なスタイルが生まれる。
https://gyazo.com/23bd40985f22f411f121dfae48389ac6

## Reset CSS を使用する

Reset CSS を用いることで、要素の余分な余白等を消すことができる。
