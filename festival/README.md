# 日専祭アプリ：（アプリ名をここに書く）

> **チーム名：**　MEETI
> **チーム：** 西村優里、河野結奈（リーダー）、中島多笑
> **AI利用レベル：** 2（生成コード可）
> **最終更新：** 2026-09-28

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

｀｀｀static func calculate(
        first: Participant,
        second: Participant
    ) -> CompatibilityResult? {
    ｀｀｀
    calculateを実行したら、最後にCompatibilityResult または nil を返すコード。

｀｀｀return CompatibilityResult(
            totalScore: totalScore,
            mbtiScore: mbtiScore,
            interestScore: interestScore,
            sharedInterests: sharedInterests
        )
        ｀｀｀
４つのスコアをまとめて返すためのコード。

（例：`@State`、`List`、`ForEach`、構造体、配列の `append` と `remove`）

## 生成AIの使い方（どの場面で、どう使ったか）

（例：画面の骨組みは ChatGPT に書いてもらった。削除ボタンが効かなかったので、原因を質問して直した。）

## 展示で工夫した点

（例：文字を大きくして、来場者が操作しやすいようにした。）
