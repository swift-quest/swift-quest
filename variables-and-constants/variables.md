# 変数

RPG のキャラクターは HP を持っています。これまでは HP を数字として書いてきましたが、 HP を表す入れ物を作ることもできます。

```swift
var hp = 153
print(hp)
```

```
153
```

この _コード_ では、一度 `153` という値を `hp` という入れ物に入れてから、その `hp` を `print` で表示しています。 `print(hp)` とすると <code class="sq-output">hp</code> と表示されるわけではなく、 <code class="sq-output">153</code> と `hp` の中身が表示されます。

この `hp` のような入れ物のことを **_変数_** と言います。また _変数_ には名前を付けることができ、 `hp` というのがその名前です。 _変数_ の名前のことを（そのままですが） **_変数名_** と言います。

今は `hp` という _変数名_ にしていますが、 `a` でも `b` でも自由に名前を付けることができます。たとえば、次のコードは先程のコードとまったく同じ意味になります。

```swift
var a = 153
print(a)
```

しかし、 _変数_ に `a` や `b` などの名前を付けてしまうと、後で見たときにその _変数_ が何を表しているのかわからなくなってしまいます。わかりやすい _変数名_ を付けるようにしましょう。ちなみに、 `HP` ではなく `hp` と小文字になっているのは、 _Swift_ では _変数名_ を小文字にするのが一般的だからです。

まだ、よくわからないものがもう一つありますね。 `var hp = 153` の `var` とは何でしょう？この `var` は新しい _変数_ を作ることを表します。少し難しい言葉ですが、 _変数_ を作ることを _変数_ を **_宣言_** すると言います。 _コード_ の中でこれまでに `hp` という _変数_ は使われていません。新しい _変数_ を _宣言_ したい（ = 作りたい）ときには次のように書きます。

```swift
var 変数名 = 初期値
```

**_初期値_** とは _変数_ を _宣言_ したときに入れられる初期の値です。そのままですね。

また、「値を入れる」と言っていますが、`=` で _変数_ に値を入れることを **_代入_** と言います。この `=` は数学のように等しいという意味というより、 `=` の右に書いた値を左の変数に入れるという意味になります。 `hp = 153` は `hp ← 153` のように考えるとわかりやすいかもしれません。

このようにして _宣言_ された _変数_ は、 `print` するだけでなく後から計算に使うこともできます。たとえば、5 のダメージを受けた後の HP は `hp - 5` として計算することができます。

```swift
var hp = 153
print(hp - 5)
```

```
148
```

また、 `print("HP \(hp)")` のように、 _文字列補間_ で _変数_ を使うこともできます。

```swift
var hp = 153
print("HP \(hp)")
```

```
HP 153
```

さらに、 _変数_ には後から別の値を _代入_ して変更することもできます。

たとえば、相手を即死させる魔法 _デススペル_ で勇者が死んでしまったとしましょう。 HP を 0 に変更しないといけません。そんなときは `hp = 0` として _変数_ `hp` に `0` を _代入_ して変更することができます。

```swift
var hp = 153
print("HP \(hp)")
hp = 0
print("HP \(hp)")
```

```
HP 153
HP 0
```

`var hp = 153` では `var` が必要なのに、 `hp = 0` では `var` が必要 **でない** ことに注意して下さい。 `var` は新しい _変数_ を作るときに必要なものなので、一度 _変数_ `hp` を作った後は `var` を書く必要はありません。

_変数_ には計算結果を _代入_ することもできます。

勇者が死んでしまったので僧侶は _レイズデッド_ の魔法を使って勇者を生き返らせました。 _レイズデッド_ で生き返ったキャラクターは最大 HP の半分の HP で復活します。勇者の最大 HP は 153 なので、 `153 / 2` で復活時の HP を計算することができます。この計算結果を `hp = 153 / 2` として _代入_ することができます。

```swift
var hp = 153
print("HP \(hp)")
hp = 0
print("HP \(hp)")
hp = 153 / 2
print("HP \(hp)")
```

```
HP 153
HP 0
HP 76
```

## 練習問題

### 問 1

魔法使いの HP は 77 です。 _変数_ `hp` を _宣言_ して _初期値_ `77` を代入し、その後 `hp` の値を `print` で表示する _プログラム_ を作成して下さい。

### 問 2

魔法使いの MP は 58 、 _ファイアボール_ の消費 MP は 5 です。 _変数_ `mp` を _宣言_ して _初期値_ `58` を代入し、 _ファイアボール_ を使った後の MP を表示する _プログラム_ を作成して下さい。

### 問 3

問 1 のプログラムを変更して、次のように表示する _プログラム_ に作り変えて下さい。

```
HP 77
```

### 問 4

先程、勇者が死んでしまう↓の _プログラム_ を作りました。

```swift
var hp = 153
print("HP \(hp)")
hp = 0
print("HP \(hp)")
```

その後、僧侶が _リザレクション_ の魔法を使って勇者を生き返らせました。 _リザレクション_ は _レイズデット_ と違い、 HP が完全に回復した状態でキャラクターが復活します。この _コード_ の続きを書いて、 HP を 153 にして勇者を生き返らせ、次のように表示されるようにして下さい。

```
HP 153
HP 0
HP 153
```

## 答え

### 問 1

```swift
var hp = 77
print(hp)
```

### 問 2

```swift
var mp = 58
print(mp - 5)
```

### 問 3

```swift
var hp = 77
print("HP \(hp)")
```

### 問 4

```swift
var hp = 153
print("HP \(hp)")
hp = 0
print("HP \(hp)")
hp = 153
print("HP \(hp)")
```