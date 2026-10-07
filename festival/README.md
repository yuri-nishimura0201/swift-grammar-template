# 日専祭アプリ：MEETI

> **チーム名：**　MEETI
> **チーム：** 西村優里、河野結奈（リーダー）、中島多笑
> **AI利用レベル：** 2（生成コード可）
> **最終更新：** 2026-10-08

> 💡 制作の進め方は担任の先生から案内があります。このファイルの項目は、担任の先生の指示で増えることがあります。

---

## 何ができるアプリか（3行）
文化祭の来場者が、簡易MBTI診断と自己紹介から自分だけのデジタル名刺を作成できるアプリです。
その日の参加者データをもとに、MBTIや趣味などから相性の良い人を見つけることができます。
作成した名刺はQRコードを使って自分のスマートフォンに持ち帰ることができます。

## 画面

（スクリーンショットを貼る。GitHub の編集画面に画像をドラッグ＆ドロップすると貼れます。）

## 使った文法・技術

**CompatibilityCalculator.swift**

```swift
static func calculate(
        first: Participant,
        second: Participant
    ) -> CompatibilityResult? 
```
⇧calculateを実行したら、最後にCompatibilityResult または nil を返すコード。
？をつけてoptional(値が入ってるか空のどちらかを示す)にしている


```swift
return CompatibilityResult(
            totalScore: totalScore,
            mbtiScore: mbtiScore,
            interestScore: interestScore,
            sharedInterests: sharedInterests
        )
```
⇧相性結果をまとめて返すためのコード。


```swift
var sharedInterests: [String] = []
```
⇧共通する部分を追加する配列。複数保持。


```swift
if firstMBTI[0] == secondMBTI[0] {
            mbtiScore += 18
        }
```
⇧もしスコア（０の配列の中身）が一緒なら得点追加。

```swift
for interest in first.interests {
```
⇧一人目が選んだ配列から一個ずつ確認する

```swift
var interestScore = sharedInterests.count * 10

if interestScore > 30 {
    interestScore = 30
}
```
⇧カウントで配列の要素数を取得。一個✖️１０点。


**MBTICalculator.swift**

```swift
if answers.count != questions.count {
    return nil
}
```
⇧全問解答しているかの確認のためのコード。
カウントで数確認。!=で同じか否かの確認ー＞違かったらnil

```swift
for answer in answers {
    // 回答を1つずつ処理
}
```
⇧フォーインで解答を一つずつ取り出し、順番に確認。

```swift
if answer == "A" {
    // A側に加点
} else if answer == "B" {
    // B側に加点
}
```
⇧条件分岐。AならAにBならBに。

```swift
return mbti
```
⇧４文字の英語（mbti）を返す。


（```swift```

## 生成AIの使い方（どの場面で、どう使ったか）

**MBTIの配点について**
```swift
if firstMBTI[0] == secondMBTI[0] { mbtiScore += 18 }
if firstMBTI[1] == secondMBTI[1] { mbtiScore += 18 }
if firstMBTI[2] == secondMBTI[2] { mbtiScore += 17 }
if firstMBTI[3] == secondMBTI[3] { mbtiScore += 17 }
```
好きなことからの配点を加味してMBTIでは70点を出したかった。
　　->18 + 18 + 17 + 17 = 70点にして同じ英語の部分にそれぞれ加算

**結果をまとめる部分**
```swift
return CompatibilityResult(
    totalScore: totalScore,
    mbtiScore: mbtiScore,
    interestScore: interestScore,
    sharedInterests: sharedInterests
)
```
どのように結果を返したらいいのか
　　->CompatibilityResultという箱に結果を入れている。リターンによってcalculate()を呼び出した側に返す。リザルトによって欲しい情報をそれぞれ取り出す。

なぜ総合点だけ返さないのか
　　->MEETIではなぜ80点だったのかも表示したい。相性計算で得られた4つの情報をまとめて返すようにした。

  

（例：画面の骨組みは ChatGPT に書いてもらった。削除ボタンが効かなかったので、原因を質問して直した。）

## 展示で工夫した点

（例：文字を大きくして、来場者が操作しやすいようにした。）
