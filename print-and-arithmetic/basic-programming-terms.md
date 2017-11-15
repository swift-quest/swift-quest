# プログラミングの基本用語

新しいことを学ぶ前に、プログラミングに関する基本的な用語を説明します。

まず、最も基本的なこととして、 **_プログラミング_** とは何でしょうか？ _プログラミング_ とは、 **_プログラム_** を作ることです。では、 _プログラム_ とは何でしょう？ _プログラム_ とは、コンピューターに対する命令の集まりです。

コンピューターは _プログラム_ に書かれた命令に忠実に従って動きます。逆に言えば、 **コンピューターは _プログラム_ に書かれている通りにしか動きません**。コンピューターに何かをさせたければ、そのような _プログラム_ を作らなければなりません。

では、 _プログラム_ はどのように作ればいいのでしょうか？前回、 `print(153 - 5)` のような _プログラム_ を作りました。

```swift
print(153 - 5)
```

コンピューターはこれを直接理解して動いているように見えますが、実はそうではありません。 `print(153 - 5)` などは、 **_ソースコード_** 、または単に **_コード_** と呼ばれるものです。本書では、以降は _コード_ と呼びます。

コンピューターは、 _コード_ をそのまま理解することはできません。コンピューターが理解できるのは **_機械語_** と呼ばれる言葉だけです。しかし、 **_機械語_** は 0 と 1 だけで書かれた言葉で、人間がそのまま書くのは大変です。かといって、人間の言葉（日本語や英語など）はあいまいなので、人間の言葉で書かれた命令をそのまま _機械語_ に翻訳するのも難しいです。

人間に理解しやすく、 _機械語_ に翻訳しやすい言葉が必要です。そうして作られたのが **_プログラミング言語_** です。人間は _プログラミング言語_ を使って _コード_ を書きます（ _コード_ を書くことを **_コーディング_** と言います）。そして、 _コード_ を _機械語_ に翻訳し（ _コード_ を _機械語_ に翻訳することを **_コンパイル_** と言います）、できあがった _プログラム_ をコンピューターが実行するのです。　_プログラミング_ とは、この一連の作業すべてを指す言葉です。

_プログラム_ はいつも思い通りに動くとは限りません。 _コード_ が間違えていたら、コンピューターはその間違いに忠実に動きます。あなたの作った _プログラム_ が思っていたのと違う動きをしたら、それはあなたが間違えているということです。もしくは _コンパイル_ に失敗して動かすことすらできないかもしれません。ごまかしは利きません。原因を調査し、 _コード_ を修正し、再度 _プログラム_ を実行して確認をしなければなりません。

これは魔法によく似ています。物語の中の魔法使いは、魔法を発動するのに呪文を唱えたり印を切ったりします。これは _コーディング_ に当たります。呪文は正確に唱えなければなりません。少しでも間違えてしまうと魔法が発動しなかったり、変な発動のしかたをしたりします。同じように、 _コード_ も正確に書く必要があります。魔法使いの唱える呪文は、古代語だったり魔法の言葉だったりします。これが _プログラミング言語_ です。そして、呪文を正確に唱えるとそれが魔法の力に変換（ _コンパイル_ ）されます。そうしてようやく魔法が発動（ _プログラム_ を実行）できるわけです。

| 魔法 | _プログラム_ |
|:---|:---|
| 呪文 | _コード_ |
| 呪文詠唱（呪文を唱えること） | _コーディング_ |
| 呪文の言語（古代語など） | _プログラミング言語_ |
| 正しく呪文を唱えるとそれが魔法の力に変換されること | _コンパイル_ |
| 魔法を使うこと | _プログラミング_ |

SWIFT QUEST では **_Swift_** という _プログラミング言語_ を使って _プログラミング_ を学びます。これは、次のような理由からです。

- シンプルで初心者が学びやすい
- 2014 年に生まれた新しい言語なので最新の考え方を学びやすい
- 幅広い機能を持っていて _プログラミング_ における様々な考え方を学ぶことができる
- 人気があり、プロも使っていて実際に役に立つ（ iPhone 用のアプリを作ったりするのに使える）