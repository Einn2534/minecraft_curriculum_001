# エージェントで四角を作ろう

### @explicitHints true

## Introduction @unplugged

このチュートリアルでは、Minecraft のチャット命令でエージェントを動かし、砂岩で四角形を作ります。

使うチャット命令は4つです。

- `tp`: エージェントを自分の場所へ呼ぶ
- `rl`: エージェントに砂岩を入れる
- `pd`: 歩くたびにブロックを置く
- `square`: 四角形を作る

## Step 1: エージェントを呼ぶ

チャットで `tp` と入力したら、エージェントが自分の場所に来るようにします。

```blocks
player.onChat("tp", function () {
    agent.teleportToPlayer()
})
```

## Step 2: ブロックを入れる

チャットで `rl` と入力したら、エージェントの1番スロットに砂岩を64個入れます。

```blocks
player.onChat("tp", function () {
    agent.teleportToPlayer()
})
player.onChat("rl", function () {
    agent.setItem(SANDSTONE, 64, 1)
    agent.setSlot(1)
})
```

## Step 3: 置きながら歩く準備をする

チャットで `pd` と入力したら、エージェントが歩くたびにブロックを置く設定にします。

```blocks
player.onChat("tp", function () {
    agent.teleportToPlayer()
})
player.onChat("rl", function () {
    agent.setItem(SANDSTONE, 64, 1)
    agent.setSlot(1)
})
player.onChat("pd", function () {
    agent.setAssist(PLACE_ON_MOVE, true)
})
```

## Step 4: 四角を作る命令を作る

チャットで `square` と入力したら、エージェントが前へ5ブロック進んで左へ曲がる動きを4回くり返すようにします。

```blocks
player.onChat("tp", function () {
    agent.teleportToPlayer()
})
player.onChat("rl", function () {
    agent.setItem(SANDSTONE, 64, 1)
    agent.setSlot(1)
})
player.onChat("pd", function () {
    agent.setAssist(PLACE_ON_MOVE, true)
})
player.onChat("square", function () {
    for (let i = 0; i < 4; i++) {
        agent.move(FORWARD, 5)
        agent.turn(LEFT_TURN)
    }
})
```

## Step 5: Minecraftで実行する

緑の実行ボタンを押してから、Minecraftのチャットで順番に命令を入力します。

1. `tp`
2. `rl`
3. `pd`
4. `square`

エージェントが砂岩で四角形を作れば完成です。
