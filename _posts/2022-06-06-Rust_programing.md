---
layout: post
title: "実践Rustプログラミング入門1"
date: 2022-06-06 22:00:00 +0900
auther: 5hunsat0
categories: Learning 
---


### 第一章

Rustという言語の魅力・特徴

- 実行速度の速さ。C,C++に匹敵する速さ。ちなみにpythonは比較表にも入っていない。
  - 直接機械語にコンパイルされる言語(C,C++,Rust等) vs 仮想マシンを使う言語(java,python等)
  - ガベージコレクションを持つ(Go) vs 持たない (Rust)
    - ガベージコレクションは自動的に不要なメモリ領域を解放する。ない場合は手動で解放している(C, C++)。Rustは別の仕組みで実現。
- ゼロコスト抽象化？の追求。
  - > What you don't use, you don't pay for (in time or space). And futher: What you do use, you couldn't hand code any better.
  - 追加コストなく抽象化の機能を使えることを重視。
- モダンな言語機能
  - 変数が標準で不変(!) : 再代入できない変数。
  - filter, mapの操作？ [この辺り](https://www.unitrust.co.jp/8367)が説明良さそう。
    - > Stream APIとはCollectionを細かい単位に区切って処理させて何かしらの結果を出力させるためのAPI
  - Rustの場合はイテレータ(要素を一つ一つ辿っていく操作を抽象化した機構)文法機能でできる。
- 代数的データ型とパターンマッチング？ むずい。
  - 代数的データ型として使える型が用意されている。あらかじめ型で表現できることを使うので、余計な処理がいらない(値のあるなしなど)、可読性が高くなる書き方。保守性やバグの軽減にも効果あり。
- 型推論
  - 型を明記することはほとんどない -> コンパイル時に型を補完してくれる。
- トレイト？
  - java の interface のような機能。
  - よくわからないが、同様の振る舞いをする処理を共通化して手間を減らす。
  - 関数型プログラミング言語？
    - 命令型計算モデル(java,python) - 関数型計算モデル(Haskell) - 論理型計算モデル(Prolog)
    - 計算能力は全部同じだけど、実現プロセスが違う。上から順に読んでいくか、関数の組み合わせで実現できるものを探して、関数同士を合成しながら実装するか。論理型は知らない。
- OS から Web アプリケーションまで使える
  - OSも書ける。Webアプリケーションのバックエンドも書ける。
- ツールが充実
  - Cargo : パッケージマネージャ兼ビルドツール。が便利。
- 安全性
  - メモリ安全でない操作やスレッド安全でない操作を未然に防ぐ設計
  - メモリ安全でない : 解放したメモリ領域を参照する (use-after-free)
    - セキュリティーホールにもなる
  - スレッド安全ではない : 複数スレッドで共有する変数に同時読み書きした際に一貫性が保てない
- エディションの考え方
  - 互換性の担保。

<br>

次回は環境構築。
