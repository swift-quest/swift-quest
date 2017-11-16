# 実践: 1 ターンの戦闘

これまでに学んだことを使って 1 ターンの戦闘を作ってみましょう。勇者と魔王がお互いに攻撃をし、ターンの始めと終わりに勇者と魔王の HP を表示します。

勇者と魔王のステータスは次の通りです。

| | 勇者 | 魔王 |
|:---|---:|---:|
| HP | 153 | 999 |
| 攻撃力 | 162 | 185 |
| 防御力 | 97 | 58 |

まずはこれを _変数_ と _定数_ で表します。名前は `name` 、 HP は `hp` 、攻撃力は `attack` 、防御力は `defense` とします。勇者と魔王の 2 人がいるので、勇者は `hp1` 、魔王は `hp2` というように、勇者のステータスの _変数名_ には `1` を、魔王には `2` を付けます。

```swift
let name1 = "ゆうしゃ"
var hp1 = 153
let attack1 = 162
let defense1 = 97

let name2 = "まおう"
var hp2 = 999
let attack2 = 185
let defense2 = 58
```

5 行目に空行（何も書いていない行）があります。これは勇者と魔王のステータスを分けて _コード_ を見やすくするためのものです。 _Swift_ の _コード_ では好きなところに空行を入れることができます。

この続きで勇者と魔王の HP を表示しましょう。

```swift
print(name1)
print("HP \(hp1)")
print()

print(name2)
print("HP \(hp2)")
print()
```

`print()` は空行を表示するためのものです。これがないと勇者と魔王のステータスがつながって表示されてしまいます。 _コード_ 上でも 4 行目に空行がありますが、これはあくまで _コード_ を見やすくするためのものです。 _コード_ で空行を入れても表示結果には一切影響がないことに注意して下さい。

ここまでで _プログラム_ を実行すると結果は次のようになります。

```
ゆうしゃ
HP 153

まおう
HP 999

```

次に勇者が魔王を攻撃します。ダメージは攻撃力から防御力を引いて 2 で割ることで計算できました。今、勇者の攻撃力は `attack1` 、魔王のっ防御力は `defense2` なので、ダメージは `(attack1 - defense2) / 2` で計算できます。

```swift
print("\(name1)のこうげき。\(name2)に\((attack1 - defense2) / 2)のダメージ！")
```

```
ゆうしゃのこうげき。まおうに52のダメージ！
```

おお！ステータスからちゃんとダメージが計算されて RPG っぽく表示できました。

魔王にダメージを与えたということは魔王の HP を減らさなければなりません。前にやったように `-=` を使って魔王の HP を減らします。ダメージは今計算したように `(attack1 - defense2) / 2` なので、これを魔王の HP を表す `hp2` から引きましょう。

```swift
hp2 -= (attack1 - defense2) / 2
```

これでもいいのですが、 `(attack1 - defense2) / 2` という計算を 2 箇所に書いてしまっていて無駄です。次のように、計算結果を _変数_ や _定数_ にとっておけば、その計算結果を後から使うことができます。

```swift
let damage1 = (attack1 - defense2) / 2
print("\(name1)のこうげき。\(name2)に\(damage1)のダメージ！")
hp2 -= damage1
```

同じ計算を無駄に 2 回も書く必要がなくなりました。 `damage1` は勇者の攻撃のダメージを表す _定数_ です。

さて、次は魔王の攻撃です。勇者の攻撃と同じように書いてみましょう。

```swift
let damage2 = (attack2 - defense1) / 2
print("\(name2)のこうげき。\(name1)に\(damage2)のダメージ！")
hp1 -= damage2
```

```
まおうのこうげき。ゆうしゃに44のダメージ！
```

さて、これで 1 ターンの行動が終わりました。最初と同じように勇者と魔王の HP を表示してやれば終わりです。

完成した _プログラム_ は次のようになります。

```swift
let name1 = "ゆうしゃ"
var hp1 = 153
let attack1 = 162
let defense1 = 97

let name2 = "まおう"
var hp2 = 999
let attack2 = 185
let defense2 = 58

print(name1)
print("HP \(hp1)")
print()

print(name2)
print("HP \(hp2)")
print()

let damage1 = (attack1 - defense2) / 2
print("\(name1)のこうげき。\(name2)に\(damage1)のダメージ！")
hp2 -= damage1

let damage2 = (attack2 - defense1) / 2
print("\(name2)のこうげき。\(name1)に\(damage2)のダメージ！")
hp1 -= damage2

print()

print(name1)
print("HP \(hp1)")
print()

print(name2)
print("HP \(hp2)")
```

実行結果は次の通りです。

```
ゆうしゃ
HP 153

まおう
HP 999

ゆうしゃのこうげき。まおうに52のダメージ！
まおうのこうげき。ゆうしゃに44のダメージ！

ゆうしゃ
HP 109

まおう
HP 947
```

おおお！ RPG の戦闘 1 ターン分ができました！ステータスを色々いじったり、 2 ターン目を作ってみたり、色々と遊んでみて下さい。

## 練習問題

### 問 1

↑で作った _プログラム_ を修正し、次のように表示する _プログラム_ を作成して下さい。ただし、 <code class="sq-output">XX</code> の部分には計算結果が入るものとします。

```
ゆうしゃ
HP 153

せんし
HP 198

まおう
HP 999

ゆうしゃのこうげき。まおうにXXのダメージ！
せんしのこうげき。まおうにXXのダメージ！
まおうのこうげき。ゆうしゃにXXのダメージ！

ゆうしゃ
HP XX

せんし
HP XX

まおう
HP XX
```

なお、戦士のステータスは次の通りです。

| | 戦士 |
|:---|---:|
| HP | 198 |
| 攻撃力 | 178 |
| 防御力 | 111 |

ステータスを表す _変数名_ は、勇者は `hp1` 、戦士は `hp2` 、魔王は `hp3` のように、末尾にそれぞれ `1`, `2`, `3` を付けて下さい。

### 問 2

問 1 の _プログラム_ を修正し、魔王が勇者ではなく戦士を攻撃する _プログラム_ を作成して下さい。

## 答え

### 問 1

```swift
let name1 = "ゆうしゃ"
var hp1 = 153
let attack1 = 162
let defense1 = 97

let name2 = "せんし"
var hp2 = 198
let attack2 = 178
let defense2 = 111

let name3 = "まおう"
var hp3 = 999
let attack3 = 185
let defense3 = 58

print(name1)
print("HP \(hp1)")
print()

print(name2)
print("HP \(hp2)")
print()

print(name3)
print("HP \(hp3)")
print()

let damage1 = (attack1 - defense3) / 2
print("\(name1)のこうげき。\(name3)に\(damage1)のダメージ！")
hp3 -= damage1

let damage2 = (attack2 - defense3) / 2
print("\(name2)のこうげき。\(name3)に\(damage2)のダメージ！")
hp3 -= damage2

let damage3 = (attack3 - defense1) / 2
print("\(name3)のこうげき。\(name1)に\(damage3)のダメージ！")
hp1 -= damage3

print()

print(name1)
print("HP \(hp1)")
print()

print(name2)
print("HP \(hp2)")
print()

print(name3)
print("HP \(hp3)")
```

### 問 2

```swift
let name1 = "ゆうしゃ"
var hp1 = 153
let attack1 = 162
let defense1 = 97

let name2 = "せんし"
var hp2 = 198
let attack2 = 178
let defense2 = 111

let name3 = "まおう"
var hp3 = 999
let attack3 = 185
let defense3 = 58

print(name1)
print("HP \(hp1)")
print()

print(name2)
print("HP \(hp2)")
print()

print(name3)
print("HP \(hp3)")
print()

let damage1 = (attack1 - defense3) / 2
print("\(name1)のこうげき。\(name3)に\(damage1)のダメージ！")
hp3 -= damage1

let damage2 = (attack2 - defense3) / 2
print("\(name2)のこうげき。\(name3)に\(damage2)のダメージ！")
hp3 -= damage2

let damage3 = (attack3 - defense2) / 2
print("\(name3)のこうげき。\(name2)に\(damage3)のダメージ！")
hp2 -= damage3

print()

print(name1)
print("HP \(hp1)")
print()

print(name2)
print("HP \(hp2)")
print()

print(name3)
print("HP \(hp3)")
```
