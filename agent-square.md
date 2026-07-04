# エージェントで四角形を作ろう

### @explicitHints true

## はじめに @unplugged

このチュートリアルでは、Minecraft のチャット命令でエージェントを動かして、砂岩の四角形を作ります。

![完成イメージ](https://raw.githubusercontent.com/Einn2534/minecraft_curriculum_001/master/assets/agent-square-preview.png)

作る命令は4つです。

- `tp`: エージェントを自分の場所へ呼ぶ
- `load`: エージェントに砂岩を入れる
- `pen`: 歩くたびにブロックを置く設定にする
- `square`: 四角形を作る

最後に、同じ動きを4回くり返すプログラムを作ります。

## Step 1: エージェントを呼ぼう

まず、チャットで `tp` と入力したら、エージェントが自分の場所に来るようにします。

```blocks
player.onChat("tp", function () {
    agent.teleportToPlayer()
})
```

## Step 2: 砂岩を入れよう

次に、チャットで `load` と入力したら、エージェントの1番スロットに砂岩を64個入れます。

`setSlot(1)` は、エージェントが1番スロットのブロックを使うための命令です。

```blocks
player.onChat("tp", function () {
    agent.teleportToPlayer()
})
player.onChat("load", function () {
    agent.setItem(SANDSTONE, 64, 1)
    agent.setSlot(1)
})
```

## Step 3: 置きながら歩く設定にしよう

チャットで `pen` と入力したら、エージェントが移動するたびにブロックを置く設定にします。

この設定をオンにしてからエージェントを歩かせると、線を引くようにブロックが置かれます。

```blocks
player.onChat("tp", function () {
    agent.teleportToPlayer()
})
player.onChat("load", function () {
    agent.setItem(SANDSTONE, 64, 1)
    agent.setSlot(1)
})
player.onChat("pen", function () {
    agent.setAssist(PLACE_ON_MOVE, true)
})
```

## Step 4: 1辺を作ろう

四角形の1辺を作るには、エージェントを前へ5ブロック進ませます。

ここでは、チャットで `square` と入力したら、まず1辺だけ作るようにします。

```blocks
player.onChat("tp", function () {
    agent.teleportToPlayer()
})
player.onChat("load", function () {
    agent.setItem(SANDSTONE, 64, 1)
    agent.setSlot(1)
})
player.onChat("pen", function () {
    agent.setAssist(PLACE_ON_MOVE, true)
})
player.onChat("square", function () {
    agent.move(FORWARD, 5)
})
```

## Step 5: 角を曲がろう

四角形にするには、1辺を作ったあとに左へ曲がります。

前へ進む命令のあとに、左へ曲がる命令を追加します。

```blocks
player.onChat("tp", function () {
    agent.teleportToPlayer()
})
player.onChat("load", function () {
    agent.setItem(SANDSTONE, 64, 1)
    agent.setSlot(1)
})
player.onChat("pen", function () {
    agent.setAssist(PLACE_ON_MOVE, true)
})
player.onChat("square", function () {
    agent.move(FORWARD, 5)
    agent.turn(LEFT_TURN)
})
```

## Step 6: 4回くり返そう

四角形には辺が4つあります。

「前へ5ブロック進む」と「左へ曲がる」を4回くり返すと、四角形になります。

```blocks
player.onChat("tp", function () {
    agent.teleportToPlayer()
})
player.onChat("load", function () {
    agent.setItem(SANDSTONE, 64, 1)
    agent.setSlot(1)
})
player.onChat("pen", function () {
    agent.setAssist(PLACE_ON_MOVE, true)
})
player.onChat("square", function () {
    for (let i = 0; i < 4; i++) {
        agent.move(FORWARD, 5)
        agent.turn(LEFT_TURN)
    }
})
```

## Step 7: Minecraftで試そう

緑の実行ボタンを押してから、Minecraft のチャットで次の順番に入力します。

1. `tp`
2. `load`
3. `pen`
4. `square`

エージェントが砂岩で四角形を作れば完成です。

## Step 8: 変えてみよう

できた人は、数字やブロックを変えて試してみましょう。

- `5` を `8` に変えると、大きい四角形になります。
- `SANDSTONE` を別のブロックに変えると、材料が変わります。
- `LEFT_TURN` を `RIGHT_TURN` に変えると、右回りになります。
