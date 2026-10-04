# はじめてのプログラムとAgent

### @flyoutOnly true
### @hideDone true

## T01 最初のプログラム

まず「チャットコマンド」の run を hello に変えてみよう。中に「メッセージを送信する」をつないで、文を「王都へようこそ！」にしよう！

緑の実行ボタンを押したら、Tキーでチャットを開いて hello と入力しよう。メッセージが出たら、工房NPCの「表示できた」を押してね。「T01 クリア！」が出るよ！

次はNPCの「入門の続き」→「開始位置へ」。Cキーを押して、上の「次へ」でT02へ進もう。

ヒントは電球を押してみよう。

```blocks
player.onChat("hello", function () {
    player.say("王都へようこそ！")
})
```

## T02 Agentを動かす

NPCの「開始位置へ」は押したかな？ 今は自分が歩いたりジャンプしたりできなくなっているよ。Agentがゴールすると、また歩けるよ！

新しい「チャットコマンド」を置いて run を agent に変えよう。中に「Agentをテレポート」をつなぎ、位置を (0,0,0)、向きを東にしよう。続けて「Agentを前に3ブロック移動」→「Agentを左に回転」→「Agentを前に2ブロック移動」をつなごう。

緑の実行ボタンを押して、Tキーでチャットを開き agent と入力！ 金の床に着くと、自動で「T02 クリア！」が出るよ。困ったら電球を押してみよう。

```blocks
player.onChat("agent", function () {
    agent.teleport(pos(0, 0, 0), EAST)
    agent.move(FORWARD, 3)
    agent.turn(LEFT_TURN)
    agent.move(FORWARD, 2)
})
```
