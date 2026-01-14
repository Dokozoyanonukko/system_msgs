# system_msgs : メッセージ型定義パッケージ
服薬支援システムmypkgにおいて服薬イベント、ユーザ応答、判定結果を表現するためのメッセージ型定義パッケージです。本パッケージはmypkgの動作に必要です。

![CMake](https://img.shields.io/badge/CMake-3.8%2B-blue?logo=cmake)

## 概要
本パッケージでは、4種類のメッセージ型を定義しています。それぞれの型が表す状態や値の意味は以下の通りです。

|型|値や意味|
|:---:|:---:|
|`system_msgs/msg/RmEvent`|0: イベントなし, 1: 服薬の時間|
|`system_msgs/msg/Response`|0: 無反応, 1: 服薬済み|
|`system_msgs/msg/RmNotioncmd`|0: 待機, 1: 通常, 2: 緊急（服薬忘れ）|
|`system_msgs/msg/RmStatus`|0: 待機, 1: 通常, 2: 緊急（服薬忘れ）|

* なお、`system_msgs/msg/RmEvent`には、イベント発生時刻を表すために、`builtin_interfaces/msg/Time`型のフィールドを含んでいます。

## 目的と責務
本パッケージはノード間でやり取りされる服薬イベント、ユーザ応答、判定結果について、各値が何を表すかを明示したメッセージ型を定義します。本パッケージの役割はメッセージ型の定義のみであり、イベント発行や服薬状況の判定などの処理は含みません。

## 使い方
mypkgと同じ階層に本パッケージをクローンしてください。
```bash
$ git clone git@github.com:Dokozoyanonukko/system_msgs.git
```

さらに具体的な使い方は以下のパッケージに記載しています。
* https://github.com/Dokozoyanonukko/mypkg

## ライセンス
* このソフトウェアパッケージは，3条項BSDライセンスの下，再頒布および使用が許可されます．
* © 2025 Dokozoyanonukko
