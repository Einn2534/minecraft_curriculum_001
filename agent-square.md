# はねるブタ

### @explicitHints true

## はじめに @unplugged

このチュートリアルでは、スライムブロックの上ではねるたびに、空からブタが出てくるプログラムを作ります。

使うものは3つです。

- `slime`: スライムブロックの場所を作るチャット命令
- `プレイヤーがはねたとき`: はねた瞬間にコードを動かすイベント
- `ブタを出す`: プレイヤーの上にブタを出す命令

最後は、ブタが出てくる場所をランダムにします。

## スライムの場所

`チャットされたとき` イベントの中にコードを入れて、スライムブロックで満たされた池を作ります。

池の範囲は `~-20 ~0 ~-20` から `~20 ~0 ~20` までにします。

```blocks
player.onChat("slime", function () {
    blocks.fill(
    SLIME_BLOCK,
    pos(-20, 0, -20),
    pos(20, 0, 20),
    FillOperation.Replace
    )
})
```

## はねたとき

プレイヤーがはねたときにコードを実行するイベントを追加します。

```blocks
player.onChat("slime", function () {
    blocks.fill(
    SLIME_BLOCK,
    pos(-20, 0, -20),
    pos(20, 0, 20),
    FillOperation.Replace
    )
})
player.onTravelled(TravelMethod.Bounce, function () {
})
```

## ブタを出そう

はねたとき、プレイヤーの上にブタを出すコードを追加します。

```blocks
player.onChat("slime", function () {
    blocks.fill(
    SLIME_BLOCK,
    pos(-20, 0, -20),
    pos(20, 0, 20),
    FillOperation.Replace
    )
})
player.onTravelled(TravelMethod.Bounce, function () {
    mobs.spawn(PIG, pos(0, 20, 0))
})
```

## ランダムなブタ

もっと楽しくするために、ブタが出てくる場所をランダムに選びます。

```blocks
player.onChat("slime", function () {
    blocks.fill(
    SLIME_BLOCK,
    pos(-20, 0, -20),
    pos(20, 0, 20),
    FillOperation.Replace
    )
})
player.onTravelled(TravelMethod.Bounce, function () {
    mobs.spawn(PIG, randpos(
    pos(-10, 20, -10),
    pos(10, 20, 10)
    ))
})
```

## 試してみよう

緑の実行ボタンを押してから、Minecraft に戻ります。

チャットを開いて `slime` と入力します。

スライムブロックの上ではねると、ブタが空から出てきます。
