# 西脇.rb&東灘.rb 合同もくもく会 4th
[もくもく会](http://nishiwaki-higashinadarb.doorkeeper.jp/events/4042)の題材でJekyllを使ってサイトを作ってみた。

## 環境
- Debian Linux 7.0.0
- ruby 2.0.0p195 (2013-05-14 revision 40734) [i686-linux]
- jekyll (1.0.2)

## サイト作成
`jekyll new` で作成。

```
> jekyll new jekyll-sample
```
https://github.com/hilohiro/jekyll-sample/tree/e114013524001c92a4ad76e1260a1e7acb662896

特に問題もなく。
- 指定したディレクトリが存在しているとエラー

`jekyll serve` で4000番ポートでサーバを起動。`jekyll serve -w`でファイルの更新を監視して自動的にビルド実行。

## ページを追加
another.mdを作成して追加。  
https://github.com/hilohiro/jekyll-sample/commit/7b8b862121c19e26df96dbf2b587ae88baa3ecb5

## 投稿を追加
_postに新しいファイルを追加。  
https://github.com/hilohiro/jekyll-sample/commit/1be59cec1898099acc983de16cf47b9c84568696

## 投稿のPermalinkの形式を変更
Permalinkに日付が入らないようにしたい。  
[Permalink](http://jekyllrb.com/docs/permalinks/)によると設定かYAML Front-Matterで変更可能らしいので修正してみる ⇒ 入らなくなった。  
https://github.com/hilohiro/jekyll-sample/commit/635a2d1f1b478851483426c0c642e24765fe999b

## ファイル名に投稿日を持たない投稿を作ってみる
1. 単純に日付を持たないファイルを_postに追加 ⇒ 投稿として認識されない。  
    https://github.com/hilohiro/jekyll-sample/tree/817951b3e132749f4ec6102dc14230bc3f85a63d
1. Front-matterに`date`を追加して指定 ⇒ 投稿として認識されない。  
    https://github.com/hilohiro/jekyll-sample/commit/7696a1a35da1c5087ae569d09a3f4e975589d9ee

あきらめた。

## 投稿の目次の順番をいじってみる
Liquidの`for`文の最後に`reversed`と付けると逆順になるらしい。  
https://github.com/hilohiro/jekyll-sample/commit/df096f87f5192b130606961bdd4b7897c91d4161

もう少し変更したい。

- Pluginで用意された拡張点やLiquidの修正では実現出来なさそう?
    - Liquidに渡す変数を増やす必要がある??
