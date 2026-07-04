# はねるブタ

## はじめに @unplugged

このチュートリアルでは、スライムブロックの上ではねるたびに、空からブタが出てくるプログラムを作ります。

主に使うものは4つです。

- `slime`: ||player:チャットされたとき|| に使う命令
- ||blocks:スライムで満たす||: スライムブロックの場所を作る命令
- ||player:プレイヤーがはねたとき||: はねた瞬間にコードを動かすイベント
- ||mobs:ブタを出す||: プレイヤーの上にブタを出す命令

最後は、||positions:ランダムな場所を選ぶ|| を使って、ブタが出てくる場所をランダムにします。

![空を飛ぶブタ](https://raw.githubusercontent.com/Einn2534/minecraft_curriculum_001/master/assets/agent-square-preview.png)

## スライムの場所

||player:チャットされたとき|| イベントの中にコードを入れて、||blocks:スライムで満たす|| を使って池を作ります。

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

||player:プレイヤーがはねたとき|| にコードを実行するイベントを追加します。

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

はねたとき、プレイヤーの上に ||mobs:ブタを出す|| 命令を追加します。

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

もっと楽しくするために、||mobs:ブタ|| が出てくる場所を ||positions:ランダムな場所|| にします。

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
