# 入門から本編へ・コードの作り方

### @flyoutOnly true
### @hideDone true

## T001 チャットコマンドを使ってみよう！

**T001 チャットコマンドを使ってみよう！**

工房NPCの「開始する」を押したら、このページで作ってみよう！

1. 「チャットコマンド」の run を hello に変えよう。

2. 中に「メッセージを送信する」をつないで、文を「王都へようこそ！」にしよう。

3. さいごに「コマンドを実行する」をつなぎ、function t001 と入れよう。これはクリアをゲームに知らせる合図だよ。

4. 緑の実行ボタンを押して、Tキーのチャットで hello と入力しよう。メッセージと「T001 クリア！」が出るよ！

次は緑の道をたどって、工房NPCの「入門の続き」→「開始位置へ」。この説明の右矢印でT002へ進もう。

ヒントは電球を押してみよう。

```blocks
player.onChat("hello", function () {
    player.say("王都へようこそ！")
    player.execute("function t001")
})
```

## T002 Agentを動かしてみよう！

**T002 Agentを動かしてみよう！**

工房NPCの「開始位置へ」は押したかな？ 今は歩いたりジャンプしたりできないよ。Agentがゴールすると、また歩けるよ！

1. 新しい「チャットコマンド」を置いて、run を agent に変えよう。

2. 中にAgentを呼ぶブロックをつなごう。位置は (0,0,0)、向きは東だよ。

3. 「前に3ブロックすすむ」→「ひだりまわり」→「前に2ブロックすすむ」をつなごう。ひだりまわりは、Agentの向きを左に変えることだよ。

4. 緑の実行ボタンを押して、Tキーのチャットで agent と入力しよう。金の床に着くと「T002 クリア！」！

次は工房NPCの「次の本編」でQ01をはじめよう。この説明の右矢印で「Q01」のページに進めるよ。

ヒントは電球を押してみよう。

```blocks
player.onChat("agent", function () {
    agent.teleport(pos(0, 0, 0), EAST)
    agent.move(FORWARD, 3)
    agent.turn(LEFT_TURN)
    agent.move(FORWARD, 2)
})
```

## Q01 王旗を掲げよ

**Q01 王旗を掲げよ**

Agentに同じ間隔で旗柱の土台を建てさせる

1. 新しい「チャットコマンド」を置いて、run を q01 に変えよう。

2. 中に「エージェントのスロットを1にする」をつなごう。工房で用意されたブロックを使うよ。

3. Agentを位置 (-3.0,1,10)・東向きへ呼ぼう。

4. 「6回くり返す」の中に「下にブロックを置く」→「前に1ブロックすすむ」をつなごう。

5. 入口の金の床に立とう。緑の実行ボタンを押して、Tキーのチャットで q01 と入力しよう。

6. できたら工房NPCの「完成した・判定」を押そう。床の印はこわさないでね。

ヒントは電球を押してみよう。

```blocks
player.onChat("q01", function () {
    agent.setSlot(1)
    agent.teleport(pos(-3.0, 1, 10), EAST)
    for (let i = 0; i < 6; i++) {
        agent.place(DOWN)
        agent.move(FORWARD, 1)
    }
})
```

## Q06 砕けた彩色窓

**Q06 砕けた彩色窓**

窓面を走査し、空いている場所へ指定色のガラスを補う

1. 新しい「チャットコマンド」を置いて、run を q06 に変えよう。

2. 中に「エージェントのスロットを1にする」をつなごう。工房で用意されたブロックを使うよ。

3. Agentを位置 (-4,1,8)・東向きへ呼んで、「下にブロックを置く」をつなごう。

4. Agentを位置 (-2,1,10)・東向きへ呼んで、「下にブロックを置く」をつなごう。

5. Agentを位置 (0,1,8)・東向きへ呼んで、「下にブロックを置く」をつなごう。

6. Agentを位置 (2,1,10)・東向きへ呼んで、「下にブロックを置く」をつなごう。

7. Agentを位置 (4,1,8)・東向きへ呼んで、「下にブロックを置く」をつなごう。

8. 入口の金の床に立とう。緑の実行ボタンを押して、Tキーのチャットで q06 と入力しよう。

9. できたら工房NPCの「完成した・判定」を押そう。床の印はこわさないでね。

ヒントは電球を押してみよう。

```blocks
player.onChat("q06", function () {
    agent.setSlot(1)
    agent.teleport(pos(-4, 1, 8), EAST)
    agent.place(DOWN)
    agent.teleport(pos(-2, 1, 10), EAST)
    agent.place(DOWN)
    agent.teleport(pos(0, 1, 8), EAST)
    agent.place(DOWN)
    agent.teleport(pos(2, 1, 10), EAST)
    agent.place(DOWN)
    agent.teleport(pos(4, 1, 8), EAST)
    agent.place(DOWN)
})
```

## Q11 座標術の試験

**Q11 座標術の試験**

相対座標と絶対座標を使い分けて複数の印を置く

1. 新しい「チャットコマンド」を置いて、run を q11 に変えよう。

2. 中に「エージェントのスロットを1にする」をつなごう。工房で用意されたブロックを使うよ。

3. Agentを位置 (-5,1,12)・東向きへ呼んで、「下にブロックを置く」をつなごう。

4. Agentを位置 (0,1,14)・東向きへ呼んで、「下にブロックを置く」をつなごう。

5. Agentを位置 (5,1,12)・東向きへ呼んで、「下にブロックを置く」をつなごう。

6. 入口の金の床に立とう。緑の実行ボタンを押して、Tキーのチャットで q11 と入力しよう。

7. できたら工房NPCの「完成した・判定」を押そう。床の印はこわさないでね。

ヒントは電球を押してみよう。

```blocks
player.onChat("q11", function () {
    agent.setSlot(1)
    agent.teleport(pos(-5, 1, 12), EAST)
    agent.place(DOWN)
    agent.teleport(pos(0, 1, 14), EAST)
    agent.place(DOWN)
    agent.teleport(pos(5, 1, 12), EAST)
    agent.place(DOWN)
})
```

## Q16 消えた街灯

**Q16 消えた街灯**

街灯列を検査し、欠けた光源だけを置き直す

1. 新しい「チャットコマンド」を置いて、run を q16 に変えよう。

2. 中に「エージェントのスロットを1にする」をつなごう。工房で用意されたブロックを使うよ。

3. Agentを位置 (-4,1,12)・南向きへ呼んで、「前にブロックを置く」をつなごう。

4. Agentを位置 (-2,3,12)・南向きへ呼んで、「前にブロックを置く」をつなごう。

5. Agentを位置 (0,2,12)・南向きへ呼んで、「前にブロックを置く」をつなごう。

6. Agentを位置 (2,0,12)・南向きへ呼んで、「前にブロックを置く」をつなごう。

7. Agentを位置 (4,4,12)・南向きへ呼んで、「前にブロックを置く」をつなごう。

8. 入口の金の床に立とう。緑の実行ボタンを押して、Tキーのチャットで q16 と入力しよう。

9. できたら工房NPCの「完成した・判定」を押そう。床の印はこわさないでね。

ヒントは電球を押してみよう。

```blocks
player.onChat("q16", function () {
    agent.setSlot(1)
    agent.teleport(pos(-4, 1, 12), SOUTH)
    agent.place(FORWARD)
    agent.teleport(pos(-2, 3, 12), SOUTH)
    agent.place(FORWARD)
    agent.teleport(pos(0, 2, 12), SOUTH)
    agent.place(FORWARD)
    agent.teleport(pos(2, 0, 12), SOUTH)
    agent.place(FORWARD)
    agent.teleport(pos(4, 4, 12), SOUTH)
    agent.place(FORWARD)
})
```

## Q21 運河の漂流物

**Q21 運河の漂流物**

水路脇を進み、障害物だけを壊して回収する

1. 新しい「チャットコマンド」を置いて、run を q21 に変えよう。

2. 中に「エージェントのスロットを1にする」をつなごう。工房で用意されたブロックを使うよ。

3. Agentを位置 (-8,0,1)・南向きへ呼ぼう。

4. 「前に12ブロックすすむ」→「ひだりまわり」→「前に7ブロックすすむ」をつなごう。

5. 入口の金の床に立とう。緑の実行ボタンを押して、Tキーのチャットで q21 と入力しよう。

6. できたら工房NPCの「完成した・判定」を押そう。床の印はこわさないでね。

ヒントは電球を押してみよう。

```blocks
player.onChat("q21", function () {
    agent.setSlot(1)
    agent.teleport(pos(-8, 0, 1), SOUTH)
    agent.move(FORWARD, 12)
    agent.turn(LEFT_TURN)
    agent.move(FORWARD, 7)
})
```

## Q26 城壁破損調査

**Q26 城壁破損調査**

城壁を格子状に走査し、空洞だけを石材で修理する

1. 新しい「チャットコマンド」を置いて、run を q26 に変えよう。

2. 中に「エージェントのスロットを1にする」をつなごう。工房で用意されたブロックを使うよ。

3. Agentを位置 (-6,1,3)・東向きへ呼ぼう。

4. 「4回くり返す」の中に「6回くり返す」を置こう。その中は「下にブロックを置く」→「前に2ブロックすすむ」。

5. 小さいくり返しの外、大きいくり返しの中に「みぎまわり」をつなごう。

6. 入口の金の床に立とう。緑の実行ボタンを押して、Tキーのチャットで q26 と入力しよう。

7. できたら工房NPCの「完成した・判定」を押そう。床の印はこわさないでね。

ヒントは電球を押してみよう。

```blocks
player.onChat("q26", function () {
    agent.setSlot(1)
    agent.teleport(pos(-6, 1, 3), EAST)
    for (let side = 0; side < 4; side++) {
        for (let step = 0; step < 6; step++) {
            agent.place(DOWN)
            agent.move(FORWARD, 2)
        }
        agent.turn(RIGHT_TURN)
    }
})
```

## Q31 露店設営入門

**Q31 露店設営入門**

Agentに四角い屋台骨組みを組ませる

1. 新しい「チャットコマンド」を置いて、run を q31 に変えよう。

2. 中に「エージェントのスロットを1にする」をつなごう。工房で用意されたブロックを使うよ。

3. Agentを位置 (-4.0,1,10)・東向きへ呼ぼう。

4. 「8回くり返す」の中に「下にブロックを置く」→「前に1ブロックすすむ」をつなごう。

5. 入口の金の床に立とう。緑の実行ボタンを押して、Tキーのチャットで q31 と入力しよう。

6. できたら工房NPCの「完成した・判定」を押そう。床の印はこわさないでね。

ヒントは電球を押してみよう。

```blocks
player.onChat("q31", function () {
    agent.setSlot(1)
    agent.teleport(pos(-4.0, 1, 10), EAST)
    for (let i = 0; i < 8; i++) {
        agent.place(DOWN)
        agent.move(FORWARD, 1)
    }
})
```

## Q36 鍛冶炉の品質検査

**Q36 鍛冶炉の品質検査**

炉壁の素材を検査し、間違ったブロックだけを交換する

1. 新しい「チャットコマンド」を置いて、run を q36 に変えよう。

2. 中に「エージェントのスロットを1にする」をつなごう。工房で用意されたブロックを使うよ。

3. Agentを位置 (-4,1,8)・東向きへ呼んで、「下にブロックを置く」をつなごう。

4. Agentを位置 (-2,1,10)・東向きへ呼んで、「下にブロックを置く」をつなごう。

5. Agentを位置 (0,1,8)・東向きへ呼んで、「下にブロックを置く」をつなごう。

6. Agentを位置 (2,1,10)・東向きへ呼んで、「下にブロックを置く」をつなごう。

7. Agentを位置 (4,1,8)・東向きへ呼んで、「下にブロックを置く」をつなごう。

8. 入口の金の床に立とう。緑の実行ボタンを押して、Tキーのチャットで q36 と入力しよう。

9. できたら工房NPCの「完成した・判定」を押そう。床の印はこわさないでね。

ヒントは電球を押してみよう。

```blocks
player.onChat("q36", function () {
    agent.setSlot(1)
    agent.teleport(pos(-4, 1, 8), EAST)
    agent.place(DOWN)
    agent.teleport(pos(-2, 1, 10), EAST)
    agent.place(DOWN)
    agent.teleport(pos(0, 1, 8), EAST)
    agent.place(DOWN)
    agent.teleport(pos(2, 1, 10), EAST)
    agent.place(DOWN)
    agent.teleport(pos(4, 1, 8), EAST)
    agent.place(DOWN)
})
```

## Q41 石畳の穴探し

**Q41 石畳の穴探し**

道路を走査し、穴だけを同じ舗装材で埋める

1. 新しい「チャットコマンド」を置いて、run を q41 に変えよう。

2. 中に「エージェントのスロットを1にする」をつなごう。工房で用意されたブロックを使うよ。

3. Agentを位置 (-5,1,12)・東向きへ呼んで、「下にブロックを置く」をつなごう。

4. Agentを位置 (0,1,14)・東向きへ呼んで、「下にブロックを置く」をつなごう。

5. Agentを位置 (5,1,12)・東向きへ呼んで、「下にブロックを置く」をつなごう。

6. 入口の金の床に立とう。緑の実行ボタンを押して、Tキーのチャットで q41 と入力しよう。

7. できたら工房NPCの「完成した・判定」を押そう。床の印はこわさないでね。

ヒントは電球を押してみよう。

```blocks
player.onChat("q41", function () {
    agent.setSlot(1)
    agent.teleport(pos(-5, 1, 12), EAST)
    agent.place(DOWN)
    agent.teleport(pos(0, 1, 14), EAST)
    agent.place(DOWN)
    agent.teleport(pos(5, 1, 12), EAST)
    agent.place(DOWN)
})
```

## Q46 パン屋の配達路

**Q46 パン屋の配達路**

配達先の座標配列を巡り、各家で荷物を1個ずつ下ろす

1. 新しい「チャットコマンド」を置いて、run を q46 に変えよう。

2. 中に「エージェントのスロットを1にする」をつなごう。工房で用意されたブロックを使うよ。

3. Agentを位置 (-4,1,12)・南向きへ呼んで、「前にブロックを置く」をつなごう。

4. Agentを位置 (-2,3,12)・南向きへ呼んで、「前にブロックを置く」をつなごう。

5. Agentを位置 (0,2,12)・南向きへ呼んで、「前にブロックを置く」をつなごう。

6. Agentを位置 (2,0,12)・南向きへ呼んで、「前にブロックを置く」をつなごう。

7. Agentを位置 (4,4,12)・南向きへ呼んで、「前にブロックを置く」をつなごう。

8. 入口の金の床に立とう。緑の実行ボタンを押して、Tキーのチャットで q46 と入力しよう。

9. できたら工房NPCの「完成した・判定」を押そう。床の印はこわさないでね。

ヒントは電球を押してみよう。

```blocks
player.onChat("q46", function () {
    agent.setSlot(1)
    agent.teleport(pos(-4, 1, 12), SOUTH)
    agent.place(FORWARD)
    agent.teleport(pos(-2, 3, 12), SOUTH)
    agent.place(FORWARD)
    agent.teleport(pos(0, 2, 12), SOUTH)
    agent.place(FORWARD)
    agent.teleport(pos(2, 0, 12), SOUTH)
    agent.place(FORWARD)
    agent.teleport(pos(4, 4, 12), SOUTH)
    agent.place(FORWARD)
})
```

## Q51 畑の区画設計

**Q51 畑の区画設計**

面積と周長から畝の幅・長さを決めて囲いを作る

1. 新しい「チャットコマンド」を置いて、run を q51 に変えよう。

2. 中に「エージェントのスロットを1にする」をつなごう。工房で用意されたブロックを使うよ。

3. Agentを位置 (-8,0,1)・南向きへ呼ぼう。

4. 「前に12ブロックすすむ」→「ひだりまわり」→「前に7ブロックすすむ」をつなごう。

5. 入口の金の床に立とう。緑の実行ボタンを押して、Tキーのチャットで q51 と入力しよう。

6. できたら工房NPCの「完成した・判定」を押そう。床の印はこわさないでね。

ヒントは電球を押してみよう。

```blocks
player.onChat("q51", function () {
    agent.setSlot(1)
    agent.teleport(pos(-8, 0, 1), SOUTH)
    agent.move(FORWARD, 12)
    agent.turn(LEFT_TURN)
    agent.move(FORWARD, 7)
})
```

## Q56 放牧柵の建設

**Q56 放牧柵の建設**

縦横の値から長方形の柵と1か所の門を作る

1. 新しい「チャットコマンド」を置いて、run を q56 に変えよう。

2. 中に「エージェントのスロットを1にする」をつなごう。工房で用意されたブロックを使うよ。

3. Agentを位置 (-6,1,3)・東向きへ呼ぼう。

4. 「4回くり返す」の中に「6回くり返す」を置こう。その中は「下にブロックを置く」→「前に2ブロックすすむ」。

5. 小さいくり返しの外、大きいくり返しの中に「みぎまわり」をつなごう。

6. 入口の金の床に立とう。緑の実行ボタンを押して、Tキーのチャットで q56 と入力しよう。

7. できたら工房NPCの「完成した・判定」を押そう。床の印はこわさないでね。

ヒントは電球を押してみよう。

```blocks
player.onChat("q56", function () {
    agent.setSlot(1)
    agent.teleport(pos(-6, 1, 3), EAST)
    for (let side = 0; side < 4; side++) {
        for (let step = 0; step < 6; step++) {
            agent.place(DOWN)
            agent.move(FORWARD, 2)
        }
        agent.turn(RIGHT_TURN)
    }
})
```

## Q02 玉座の床紋章

**Q02 玉座の床紋章**

2次元配列の色番号から左右対称の床模様を描く

1. 新しい「チャットコマンド」を置いて、run を q02 に変えよう。

2. 中に「エージェントのスロットを1にする」をつなごう。工房で用意されたブロックを使うよ。

3. Agentを位置 (-6,1,3)・東向きへ呼ぼう。

4. 「4回くり返す」の中に「6回くり返す」を置こう。その中は「下にブロックを置く」→「前に2ブロックすすむ」。

5. 小さいくり返しの外、大きいくり返しの中に「みぎまわり」をつなごう。

6. 入口の金の床に立とう。緑の実行ボタンを押して、Tキーのチャットで q02 と入力しよう。

7. できたら工房NPCの「完成した・判定」を押そう。床の印はこわさないでね。

ヒントは電球を押してみよう。

```blocks
player.onChat("q02", function () {
    agent.setSlot(1)
    agent.teleport(pos(-6, 1, 3), EAST)
    for (let side = 0; side < 4; side++) {
        for (let step = 0; step < 6; step++) {
            agent.place(DOWN)
            agent.move(FORWARD, 2)
        }
        agent.turn(RIGHT_TURN)
    }
})
```

## Q03 衛兵巡回試験

**Q03 衛兵巡回試験**

標識ブロックを検知しながら決められた巡回路を一周する

1. 新しい「チャットコマンド」を置いて、run を q03 に変えよう。

2. 中に「エージェントのスロットを1にする」をつなごう。工房で用意されたブロックを使うよ。

3. Agentを位置 (-8,0,1)・南向きへ呼ぼう。

4. 「前に12ブロックすすむ」→「ひだりまわり」→「前に9ブロックすすむ」をつなごう。

5. 入口の金の床に立とう。緑の実行ボタンを押して、Tキーのチャットで q03 と入力しよう。

6. できたら工房NPCの「完成した・判定」を押そう。床の印はこわさないでね。

ヒントは電球を押してみよう。

```blocks
player.onChat("q03", function () {
    agent.setSlot(1)
    agent.teleport(pos(-8, 0, 1), SOUTH)
    agent.move(FORWARD, 12)
    agent.turn(LEFT_TURN)
    agent.move(FORWARD, 9)
})
```

## Q04 嵐の跳ね橋

**Q04 嵐の跳ね橋**

天候と時刻を調べ、条件に応じて橋を上げ下げする

1. 新しい「チャットコマンド」を置いて、run を q04 に変えよう。

2. 中に「エージェントのスロットを1にする」をつなごう。工房で用意されたブロックを使うよ。

3. Agentを位置 (-4,1,12)・南向きへ呼んで、「前にブロックを置く」をつなごう。

4. Agentを位置 (-2,3,12)・南向きへ呼んで、「前にブロックを置く」をつなごう。

5. Agentを位置 (0,2,12)・南向きへ呼んで、「前にブロックを置く」をつなごう。

6. Agentを位置 (2,0,12)・南向きへ呼んで、「前にブロックを置く」をつなごう。

7. Agentを位置 (4,4,12)・南向きへ呼んで、「前にブロックを置く」をつなごう。

8. 入口の金の床に立とう。緑の実行ボタンを押して、Tキーのチャットで q04 と入力しよう。

9. できたら工房NPCの「完成した・判定」を押そう。床の印はこわさないでね。

ヒントは電球を押してみよう。

```blocks
player.onChat("q04", function () {
    agent.setSlot(1)
    agent.teleport(pos(-4, 1, 12), SOUTH)
    agent.place(FORWARD)
    agent.teleport(pos(-2, 3, 12), SOUTH)
    agent.place(FORWARD)
    agent.teleport(pos(0, 2, 12), SOUTH)
    agent.place(FORWARD)
    agent.teleport(pos(2, 0, 12), SOUTH)
    agent.place(FORWARD)
    agent.teleport(pos(4, 4, 12), SOUTH)
    agent.place(FORWARD)
})
```

## Q05 王家の暗号金庫

**Q05 王家の暗号金庫**

数字の手掛かりを配列に保存し、正しい組合せだけを返す

1. 新しい「チャットコマンド」を置いて、run を q05 に変えよう。

2. 中に「エージェントのスロットを1にする」をつなごう。工房で用意されたブロックを使うよ。

3. Agentを位置 (-5,1,12)・東向きへ呼んで、「下にブロックを置く」をつなごう。

4. Agentを位置 (0,1,14)・東向きへ呼んで、「下にブロックを置く」をつなごう。

5. Agentを位置 (5,1,12)・東向きへ呼んで、「下にブロックを置く」をつなごう。

6. 入口の金の床に立とう。緑の実行ボタンを押して、Tキーのチャットで q05 と入力しよう。

7. できたら工房NPCの「完成した・判定」を押そう。床の印はこわさないでね。

ヒントは電球を押してみよう。

```blocks
player.onChat("q05", function () {
    agent.setSlot(1)
    agent.teleport(pos(-5, 1, 12), EAST)
    agent.place(DOWN)
    agent.teleport(pos(0, 1, 14), EAST)
    agent.place(DOWN)
    agent.teleport(pos(5, 1, 12), EAST)
    agent.place(DOWN)
})
```

## Q07 朝鐘の旋律

**Q07 朝鐘の旋律**

Agentが鐘を正しい順番と回数で鳴らす

1. 新しい「チャットコマンド」を置いて、run を q07 に変えよう。

2. 中に「エージェントのスロットを1にする」をつなごう。工房で用意されたブロックを使うよ。

3. Agentを位置 (-4.0,1,10)・東向きへ呼ぼう。

4. 「8回くり返す」の中に「下にブロックを置く」→「前に1ブロックすすむ」をつなごう。

5. 入口の金の床に立とう。緑の実行ボタンを押して、Tキーのチャットで q07 と入力しよう。

6. できたら工房NPCの「完成した・判定」を押そう。床の印はこわさないでね。

ヒントは電球を押してみよう。

```blocks
player.onChat("q07", function () {
    agent.setSlot(1)
    agent.teleport(pos(-4.0, 1, 10), EAST)
    for (let i = 0; i < 8; i++) {
        agent.place(DOWN)
        agent.move(FORWARD, 1)
    }
})
```

## Q08 祈りの灯列

**Q08 祈りの灯列**

左右交互の燭台へ一定間隔で灯りを置く

1. 新しい「チャットコマンド」を置いて、run を q08 に変えよう。

2. 中に「エージェントのスロットを1にする」をつなごう。工房で用意されたブロックを使うよ。

3. Agentを位置 (-6,1,3)・東向きへ呼ぼう。

4. 「4回くり返す」の中に「6回くり返す」を置こう。その中は「下にブロックを置く」→「前に2ブロックすすむ」。

5. 小さいくり返しの外、大きいくり返しの中に「みぎまわり」をつなごう。

6. 入口の金の床に立とう。緑の実行ボタンを押して、Tキーのチャットで q08 と入力しよう。

7. できたら工房NPCの「完成した・判定」を押そう。床の印はこわさないでね。

ヒントは電球を押してみよう。

```blocks
player.onChat("q08", function () {
    agent.setSlot(1)
    agent.teleport(pos(-6, 1, 3), EAST)
    for (let side = 0; side < 4; side++) {
        for (let step = 0; step < 6; step++) {
            agent.place(DOWN)
            agent.move(FORWARD, 2)
        }
        agent.turn(RIGHT_TURN)
    }
})
```

## Q09 巡礼路の修復

**Q09 巡礼路の修復**

長さを引数にして石畳と縁石を同時に敷く

1. 新しい「チャットコマンド」を置いて、run を q09 に変えよう。

2. 中に「エージェントのスロットを1にする」をつなごう。工房で用意されたブロックを使うよ。

3. Agentを位置 (-8,0,1)・南向きへ呼ぼう。

4. 「前に12ブロックすすむ」→「ひだりまわり」→「前に10ブロックすすむ」をつなごう。

5. 入口の金の床に立とう。緑の実行ボタンを押して、Tキーのチャットで q09 と入力しよう。

6. できたら工房NPCの「完成した・判定」を押そう。床の印はこわさないでね。

ヒントは電球を押してみよう。

```blocks
player.onChat("q09", function () {
    agent.setSlot(1)
    agent.teleport(pos(-8, 0, 1), SOUTH)
    agent.move(FORWARD, 12)
    agent.turn(LEFT_TURN)
    agent.move(FORWARD, 10)
})
```

## Q10 地下墓所の迷宮

**Q10 地下墓所の迷宮**

壁を検知し続け、赤石の終点までAgentを自律移動させる

1. 新しい「チャットコマンド」を置いて、run を q10 に変えよう。

2. 中に「エージェントのスロットを1にする」をつなごう。工房で用意されたブロックを使うよ。

3. Agentを位置 (-4,1,12)・南向きへ呼んで、「前にブロックを置く」をつなごう。

4. Agentを位置 (-2,3,12)・南向きへ呼んで、「前にブロックを置く」をつなごう。

5. Agentを位置 (0,2,12)・南向きへ呼んで、「前にブロックを置く」をつなごう。

6. Agentを位置 (2,0,12)・南向きへ呼んで、「前にブロックを置く」をつなごう。

7. Agentを位置 (4,4,12)・南向きへ呼んで、「前にブロックを置く」をつなごう。

8. 入口の金の床に立とう。緑の実行ボタンを押して、Tキーのチャットで q10 と入力しよう。

9. できたら工房NPCの「完成した・判定」を押そう。床の印はこわさないでね。

ヒントは電球を押してみよう。

```blocks
player.onChat("q10", function () {
    agent.setSlot(1)
    agent.teleport(pos(-4, 1, 12), SOUTH)
    agent.place(FORWARD)
    agent.teleport(pos(-2, 3, 12), SOUTH)
    agent.place(FORWARD)
    agent.teleport(pos(0, 2, 12), SOUTH)
    agent.place(FORWARD)
    agent.teleport(pos(2, 0, 12), SOUTH)
    agent.place(FORWARD)
    agent.teleport(pos(4, 4, 12), SOUTH)
    agent.place(FORWARD)
})
```

## Q12 錬金素材の仕分け

**Q12 錬金素材の仕分け**

Agentのスロット内容と個数を調べ、棚ごとに移し替える

1. 新しい「チャットコマンド」を置いて、run を q12 に変えよう。

2. 中に「エージェントのスロットを1にする」をつなごう。工房で用意されたブロックを使うよ。

3. Agentを位置 (-4,1,8)・東向きへ呼んで、「下にブロックを置く」をつなごう。

4. Agentを位置 (-2,1,10)・東向きへ呼んで、「下にブロックを置く」をつなごう。

5. Agentを位置 (0,1,8)・東向きへ呼んで、「下にブロックを置く」をつなごう。

6. Agentを位置 (2,1,10)・東向きへ呼んで、「下にブロックを置く」をつなごう。

7. Agentを位置 (4,1,8)・東向きへ呼んで、「下にブロックを置く」をつなごう。

8. 入口の金の床に立とう。緑の実行ボタンを押して、Tキーのチャットで q12 と入力しよう。

9. できたら工房NPCの「完成した・判定」を押そう。床の印はこわさないでね。

ヒントは電球を押してみよう。

```blocks
player.onChat("q12", function () {
    agent.setSlot(1)
    agent.teleport(pos(-4, 1, 8), EAST)
    agent.place(DOWN)
    agent.teleport(pos(-2, 1, 10), EAST)
    agent.place(DOWN)
    agent.teleport(pos(0, 1, 8), EAST)
    agent.place(DOWN)
    agent.teleport(pos(2, 1, 10), EAST)
    agent.place(DOWN)
    agent.teleport(pos(4, 1, 8), EAST)
    agent.place(DOWN)
})
```

## Q13 魔法文字印刷機

**Q13 魔法文字印刷機**

入力した短い文字を壁へブロックで印刷する

1. 新しい「チャットコマンド」を置いて、run を q13 に変えよう。

2. 中に「エージェントのスロットを1にする」をつなごう。工房で用意されたブロックを使うよ。

3. Agentを位置 (-3.0,1,10)・東向きへ呼ぼう。

4. 「6回くり返す」の中に「下にブロックを置く」→「前に1ブロックすすむ」をつなごう。

5. 入口の金の床に立とう。緑の実行ボタンを押して、Tキーのチャットで q13 と入力しよう。

6. できたら工房NPCの「完成した・判定」を押そう。床の印はこわさないでね。

ヒントは電球を押してみよう。

```blocks
player.onChat("q13", function () {
    agent.setSlot(1)
    agent.teleport(pos(-3.0, 1, 10), EAST)
    for (let i = 0; i < 6; i++) {
        agent.place(DOWN)
        agent.move(FORWARD, 1)
    }
})
```

## Q14 王都気象台

**Q14 王都気象台**

観測値に応じて天候と警告を切り替える

1. 新しい「チャットコマンド」を置いて、run を q14 に変えよう。

2. 中に「エージェントのスロットを1にする」をつなごう。工房で用意されたブロックを使うよ。

3. Agentを位置 (-6,1,3)・東向きへ呼ぼう。

4. 「4回くり返す」の中に「6回くり返す」を置こう。その中は「下にブロックを置く」→「前に2ブロックすすむ」。

5. 小さいくり返しの外、大きいくり返しの中に「みぎまわり」をつなごう。

6. 入口の金の床に立とう。緑の実行ボタンを押して、Tキーのチャットで q14 と入力しよう。

7. できたら工房NPCの「完成した・判定」を押そう。床の印はこわさないでね。

ヒントは電球を押してみよう。

```blocks
player.onChat("q14", function () {
    agent.setSlot(1)
    agent.teleport(pos(-6, 1, 3), EAST)
    for (let side = 0; side < 4; side++) {
        for (let step = 0; step < 6; step++) {
            agent.place(DOWN)
            agent.move(FORWARD, 2)
        }
        agent.turn(RIGHT_TURN)
    }
})
```

## Q15 壊れた魔導書

**Q15 壊れた魔導書**

用意された誤作動コードをテストし、5個のバグを直す

1. 新しい「チャットコマンド」を置いて、run を q15 に変えよう。

2. 中に「エージェントのスロットを1にする」をつなごう。工房で用意されたブロックを使うよ。

3. Agentを位置 (-8,0,1)・南向きへ呼ぼう。

4. 「前に12ブロックすすむ」→「ひだりまわり」→「前に6ブロックすすむ」をつなごう。

5. 入口の金の床に立とう。緑の実行ボタンを押して、Tキーのチャットで q15 と入力しよう。

6. できたら工房NPCの「完成した・判定」を押そう。床の印はこわさないでね。

ヒントは電球を押してみよう。

```blocks
player.onChat("q15", function () {
    agent.setSlot(1)
    agent.teleport(pos(-8, 0, 1), SOUTH)
    agent.move(FORWARD, 12)
    agent.turn(LEFT_TURN)
    agent.move(FORWARD, 6)
})
```

## Q17 広場清掃隊

**Q17 広場清掃隊**

指定範囲を巡回し、汚れブロックだけを除去・回収する

1. 新しい「チャットコマンド」を置いて、run を q17 に変えよう。

2. 中に「エージェントのスロットを1にする」をつなごう。工房で用意されたブロックを使うよ。

3. Agentを位置 (-5,1,12)・東向きへ呼んで、「下にブロックを置く」をつなごう。

4. Agentを位置 (0,1,14)・東向きへ呼んで、「下にブロックを置く」をつなごう。

5. Agentを位置 (5,1,12)・東向きへ呼んで、「下にブロックを置く」をつなごう。

6. 入口の金の床に立とう。緑の実行ボタンを押して、Tキーのチャットで q17 と入力しよう。

7. できたら工房NPCの「完成した・判定」を押そう。床の印はこわさないでね。

ヒントは電球を押してみよう。

```blocks
player.onChat("q17", function () {
    agent.setSlot(1)
    agent.teleport(pos(-5, 1, 12), EAST)
    agent.place(DOWN)
    agent.teleport(pos(0, 1, 14), EAST)
    agent.place(DOWN)
    agent.teleport(pos(5, 1, 12), EAST)
    agent.place(DOWN)
})
```

## Q18 噴水設計競技

**Q18 噴水設計競技**

幅・高さを引数で変えられる左右対称の噴水を作る

1. 新しい「チャットコマンド」を置いて、run を q18 に変えよう。

2. 中に「エージェントのスロットを1にする」をつなごう。工房で用意されたブロックを使うよ。

3. Agentを位置 (-4,1,8)・東向きへ呼んで、「下にブロックを置く」をつなごう。

4. Agentを位置 (-2,1,10)・東向きへ呼んで、「下にブロックを置く」をつなごう。

5. Agentを位置 (0,1,8)・東向きへ呼んで、「下にブロックを置く」をつなごう。

6. Agentを位置 (2,1,10)・東向きへ呼んで、「下にブロックを置く」をつなごう。

7. Agentを位置 (4,1,8)・東向きへ呼んで、「下にブロックを置く」をつなごう。

8. 入口の金の床に立とう。緑の実行ボタンを押して、Tキーのチャットで q18 と入力しよう。

9. できたら工房NPCの「完成した・判定」を押そう。床の印はこわさないでね。

ヒントは電球を押してみよう。

```blocks
player.onChat("q18", function () {
    agent.setSlot(1)
    agent.teleport(pos(-4, 1, 8), EAST)
    agent.place(DOWN)
    agent.teleport(pos(-2, 1, 10), EAST)
    agent.place(DOWN)
    agent.teleport(pos(0, 1, 8), EAST)
    agent.place(DOWN)
    agent.teleport(pos(2, 1, 10), EAST)
    agent.place(DOWN)
    agent.teleport(pos(4, 1, 8), EAST)
    agent.place(DOWN)
})
```

## Q19 市民調査集計

**Q19 市民調査集計**

複数の回答値を保存し、合計・最大・平均相当を表示する

1. 新しい「チャットコマンド」を置いて、run を q19 に変えよう。

2. 中に「エージェントのスロットを1にする」をつなごう。工房で用意されたブロックを使うよ。

3. Agentを位置 (-4.0,1,10)・東向きへ呼ぼう。

4. 「8回くり返す」の中に「下にブロックを置く」→「前に1ブロックすすむ」をつなごう。

5. 入口の金の床に立とう。緑の実行ボタンを押して、Tキーのチャットで q19 と入力しよう。

6. できたら工房NPCの「完成した・判定」を押そう。床の印はこわさないでね。

ヒントは電球を押してみよう。

```blocks
player.onChat("q19", function () {
    agent.setSlot(1)
    agent.teleport(pos(-4.0, 1, 10), EAST)
    for (let i = 0; i < 8; i++) {
        agent.place(DOWN)
        agent.move(FORWARD, 1)
    }
})
```

## Q20 時計塔の同期

**Q20 時計塔の同期**

時刻を取得し、朝・昼・夕・夜で鐘と案内表示を変える

1. 新しい「チャットコマンド」を置いて、run を q20 に変えよう。

2. 中に「エージェントのスロットを1にする」をつなごう。工房で用意されたブロックを使うよ。

3. Agentを位置 (-6,1,3)・東向きへ呼ぼう。

4. 「4回くり返す」の中に「6回くり返す」を置こう。その中は「下にブロックを置く」→「前に2ブロックすすむ」。

5. 小さいくり返しの外、大きいくり返しの中に「みぎまわり」をつなごう。

6. 入口の金の床に立とう。緑の実行ボタンを押して、Tキーのチャットで q20 と入力しよう。

7. できたら工房NPCの「完成した・判定」を押そう。床の印はこわさないでね。

ヒントは電球を押してみよう。

```blocks
player.onChat("q20", function () {
    agent.setSlot(1)
    agent.teleport(pos(-6, 1, 3), EAST)
    for (let side = 0; side < 4; side++) {
        for (let step = 0; step < 6; step++) {
            agent.place(DOWN)
            agent.move(FORWARD, 2)
        }
        agent.turn(RIGHT_TURN)
    }
})
```

## Q22 港湾荷役試験

**Q22 港湾荷役試験**

荷物を指定スロットから倉庫の3区画へ配る

1. 新しい「チャットコマンド」を置いて、run を q22 に変えよう。

2. 中に「エージェントのスロットを1にする」をつなごう。工房で用意されたブロックを使うよ。

3. Agentを位置 (-4,1,12)・南向きへ呼んで、「前にブロックを置く」をつなごう。

4. Agentを位置 (-2,3,12)・南向きへ呼んで、「前にブロックを置く」をつなごう。

5. Agentを位置 (0,2,12)・南向きへ呼んで、「前にブロックを置く」をつなごう。

6. Agentを位置 (2,0,12)・南向きへ呼んで、「前にブロックを置く」をつなごう。

7. Agentを位置 (4,4,12)・南向きへ呼んで、「前にブロックを置く」をつなごう。

8. 入口の金の床に立とう。緑の実行ボタンを押して、Tキーのチャットで q22 と入力しよう。

9. できたら工房NPCの「完成した・判定」を押そう。床の印はこわさないでね。

ヒントは電球を押してみよう。

```blocks
player.onChat("q22", function () {
    agent.setSlot(1)
    agent.teleport(pos(-4, 1, 12), SOUTH)
    agent.place(FORWARD)
    agent.teleport(pos(-2, 3, 12), SOUTH)
    agent.place(FORWARD)
    agent.teleport(pos(0, 2, 12), SOUTH)
    agent.place(FORWARD)
    agent.teleport(pos(2, 0, 12), SOUTH)
    agent.place(FORWARD)
    agent.teleport(pos(4, 4, 12), SOUTH)
    agent.place(FORWARD)
})
```

## Q23 倉庫番の仕分け

**Q23 倉庫番の仕分け**

品物の種類と数を検査し、空きのある棚へ移す

1. 新しい「チャットコマンド」を置いて、run を q23 に変えよう。

2. 中に「エージェントのスロットを1にする」をつなごう。工房で用意されたブロックを使うよ。

3. Agentを位置 (-5,1,12)・東向きへ呼んで、「下にブロックを置く」をつなごう。

4. Agentを位置 (0,1,14)・東向きへ呼んで、「下にブロックを置く」をつなごう。

5. Agentを位置 (5,1,12)・東向きへ呼んで、「下にブロックを置く」をつなごう。

6. 入口の金の床に立とう。緑の実行ボタンを押して、Tキーのチャットで q23 と入力しよう。

7. できたら工房NPCの「完成した・判定」を押そう。床の印はこわさないでね。

ヒントは電球を押してみよう。

```blocks
player.onChat("q23", function () {
    agent.setSlot(1)
    agent.teleport(pos(-5, 1, 12), EAST)
    agent.place(DOWN)
    agent.teleport(pos(0, 1, 14), EAST)
    agent.place(DOWN)
    agent.teleport(pos(5, 1, 12), EAST)
    agent.place(DOWN)
})
```

## Q24 壊れた荷車橋

**Q24 壊れた荷車橋**

入力された長さに応じて床・欄干・灯りを架ける

1. 新しい「チャットコマンド」を置いて、run を q24 に変えよう。

2. 中に「エージェントのスロットを1にする」をつなごう。工房で用意されたブロックを使うよ。

3. Agentを位置 (-4,1,8)・東向きへ呼んで、「下にブロックを置く」をつなごう。

4. Agentを位置 (-2,1,10)・東向きへ呼んで、「下にブロックを置く」をつなごう。

5. Agentを位置 (0,1,8)・東向きへ呼んで、「下にブロックを置く」をつなごう。

6. Agentを位置 (2,1,10)・東向きへ呼んで、「下にブロックを置く」をつなごう。

7. Agentを位置 (4,1,8)・東向きへ呼んで、「下にブロックを置く」をつなごう。

8. 入口の金の床に立とう。緑の実行ボタンを押して、Tキーのチャットで q24 と入力しよう。

9. できたら工房NPCの「完成した・判定」を押そう。床の印はこわさないでね。

ヒントは電球を押してみよう。

```blocks
player.onChat("q24", function () {
    agent.setSlot(1)
    agent.teleport(pos(-4, 1, 8), EAST)
    agent.place(DOWN)
    agent.teleport(pos(-2, 1, 10), EAST)
    agent.place(DOWN)
    agent.teleport(pos(0, 1, 8), EAST)
    agent.place(DOWN)
    agent.teleport(pos(2, 1, 10), EAST)
    agent.place(DOWN)
    agent.teleport(pos(4, 1, 8), EAST)
    agent.place(DOWN)
})
```

## Q25 二連水門の制御

**Q25 二連水門の制御**

上流と下流の印を検査し、正しい順番で水門を開閉する

1. 新しい「チャットコマンド」を置いて、run を q25 に変えよう。

2. 中に「エージェントのスロットを1にする」をつなごう。工房で用意されたブロックを使うよ。

3. Agentを位置 (-3.0,1,10)・東向きへ呼ぼう。

4. 「6回くり返す」の中に「下にブロックを置く」→「前に1ブロックすすむ」をつなごう。

5. 入口の金の床に立とう。緑の実行ボタンを押して、Tキーのチャットで q25 と入力しよう。

6. できたら工房NPCの「完成した・判定」を押そう。床の印はこわさないでね。

ヒントは電球を押してみよう。

```blocks
player.onChat("q25", function () {
    agent.setSlot(1)
    agent.teleport(pos(-3.0, 1, 10), EAST)
    for (let i = 0; i < 6; i++) {
        agent.place(DOWN)
        agent.move(FORWARD, 1)
    }
})
```

## Q27 夜警の巡回路

**Q27 夜警の巡回路**

複数の座標を順番に巡り、各地点で信号を出す

1. 新しい「チャットコマンド」を置いて、run を q27 に変えよう。

2. 中に「エージェントのスロットを1にする」をつなごう。工房で用意されたブロックを使うよ。

3. Agentを位置 (-8,0,1)・南向きへ呼ぼう。

4. 「前に12ブロックすすむ」→「ひだりまわり」→「前に8ブロックすすむ」をつなごう。

5. 入口の金の床に立とう。緑の実行ボタンを押して、Tキーのチャットで q27 と入力しよう。

6. できたら工房NPCの「完成した・判定」を押そう。床の印はこわさないでね。

ヒントは電球を押してみよう。

```blocks
player.onChat("q27", function () {
    agent.setSlot(1)
    agent.teleport(pos(-8, 0, 1), SOUTH)
    agent.move(FORWARD, 12)
    agent.turn(LEFT_TURN)
    agent.move(FORWARD, 8)
})
```

## Q28 王国射撃大会

**Q28 王国射撃大会**

的をランダムに選び、命中回数と連続得点を数える

1. 新しい「チャットコマンド」を置いて、run を q28 に変えよう。

2. 中に「エージェントのスロットを1にする」をつなごう。工房で用意されたブロックを使うよ。

3. Agentを位置 (-4,1,12)・南向きへ呼んで、「前にブロックを置く」をつなごう。

4. Agentを位置 (-2,3,12)・南向きへ呼んで、「前にブロックを置く」をつなごう。

5. Agentを位置 (0,2,12)・南向きへ呼んで、「前にブロックを置く」をつなごう。

6. Agentを位置 (2,0,12)・南向きへ呼んで、「前にブロックを置く」をつなごう。

7. Agentを位置 (4,4,12)・南向きへ呼んで、「前にブロックを置く」をつなごう。

8. 入口の金の床に立とう。緑の実行ボタンを押して、Tキーのチャットで q28 と入力しよう。

9. できたら工房NPCの「完成した・判定」を押そう。床の印はこわさないでね。

ヒントは電球を押してみよう。

```blocks
player.onChat("q28", function () {
    agent.setSlot(1)
    agent.teleport(pos(-4, 1, 12), SOUTH)
    agent.place(FORWARD)
    agent.teleport(pos(-2, 3, 12), SOUTH)
    agent.place(FORWARD)
    agent.teleport(pos(0, 2, 12), SOUTH)
    agent.place(FORWARD)
    agent.teleport(pos(2, 0, 12), SOUTH)
    agent.place(FORWARD)
    agent.teleport(pos(4, 4, 12), SOUTH)
    agent.place(FORWARD)
})
```

## Q29 緊急信号旗

**Q29 緊急信号旗**

入力番号に応じて異なる色の信号模様を生成する

1. 新しい「チャットコマンド」を置いて、run を q29 に変えよう。

2. 中に「エージェントのスロットを1にする」をつなごう。工房で用意されたブロックを使うよ。

3. Agentを位置 (-5,1,12)・東向きへ呼んで、「下にブロックを置く」をつなごう。

4. Agentを位置 (0,1,14)・東向きへ呼んで、「下にブロックを置く」をつなごう。

5. Agentを位置 (5,1,12)・東向きへ呼んで、「下にブロックを置く」をつなごう。

6. 入口の金の床に立とう。緑の実行ボタンを押して、Tキーのチャットで q29 と入力しよう。

7. できたら工房NPCの「完成した・判定」を押そう。床の印はこわさないでね。

ヒントは電球を押してみよう。

```blocks
player.onChat("q29", function () {
    agent.setSlot(1)
    agent.teleport(pos(-5, 1, 12), EAST)
    agent.place(DOWN)
    agent.teleport(pos(0, 1, 14), EAST)
    agent.place(DOWN)
    agent.teleport(pos(5, 1, 12), EAST)
    agent.place(DOWN)
})
```

## Q30 防衛柵の展開

**Q30 防衛柵の展開**

長さと向きを変えて再利用できる柵建築関数を作る

1. 新しい「チャットコマンド」を置いて、run を q30 に変えよう。

2. 中に「エージェントのスロットを1にする」をつなごう。工房で用意されたブロックを使うよ。

3. Agentを位置 (-4,1,8)・東向きへ呼んで、「下にブロックを置く」をつなごう。

4. Agentを位置 (-2,1,10)・東向きへ呼んで、「下にブロックを置く」をつなごう。

5. Agentを位置 (0,1,8)・東向きへ呼んで、「下にブロックを置く」をつなごう。

6. Agentを位置 (2,1,10)・東向きへ呼んで、「下にブロックを置く」をつなごう。

7. Agentを位置 (4,1,8)・東向きへ呼んで、「下にブロックを置く」をつなごう。

8. 入口の金の床に立とう。緑の実行ボタンを押して、Tキーのチャットで q30 と入力しよう。

9. できたら工房NPCの「完成した・判定」を押そう。床の印はこわさないでね。

ヒントは電球を押してみよう。

```blocks
player.onChat("q30", function () {
    agent.setSlot(1)
    agent.teleport(pos(-4, 1, 8), EAST)
    agent.place(DOWN)
    agent.teleport(pos(-2, 1, 10), EAST)
    agent.place(DOWN)
    agent.teleport(pos(0, 1, 8), EAST)
    agent.place(DOWN)
    agent.teleport(pos(2, 1, 10), EAST)
    agent.place(DOWN)
    agent.teleport(pos(4, 1, 8), EAST)
    agent.place(DOWN)
})
```

## Q32 可変式商店

**Q32 可変式商店**

幅・奥行き・屋根色を入力して別寸法の露店を作る

1. 新しい「チャットコマンド」を置いて、run を q32 に変えよう。

2. 中に「エージェントのスロットを1にする」をつなごう。工房で用意されたブロックを使うよ。

3. Agentを位置 (-6,1,3)・東向きへ呼ぼう。

4. 「4回くり返す」の中に「6回くり返す」を置こう。その中は「下にブロックを置く」→「前に2ブロックすすむ」。

5. 小さいくり返しの外、大きいくり返しの中に「みぎまわり」をつなごう。

6. 入口の金の床に立とう。緑の実行ボタンを押して、Tキーのチャットで q32 と入力しよう。

7. できたら工房NPCの「完成した・判定」を押そう。床の印はこわさないでね。

ヒントは電球を押してみよう。

```blocks
player.onChat("q32", function () {
    agent.setSlot(1)
    agent.teleport(pos(-6, 1, 3), EAST)
    for (let side = 0; side < 4; side++) {
        for (let step = 0; step < 6; step++) {
            agent.place(DOWN)
            agent.move(FORWARD, 2)
        }
        agent.turn(RIGHT_TURN)
    }
})
```

## Q33 商人の価格計算

**Q33 商人の価格計算**

個数、単価、割引条件から代金を計算して表示する

1. 新しい「チャットコマンド」を置いて、run を q33 に変えよう。

2. 中に「エージェントのスロットを1にする」をつなごう。工房で用意されたブロックを使うよ。

3. Agentを位置 (-8,0,1)・南向きへ呼ぼう。

4. 「前に12ブロックすすむ」→「ひだりまわり」→「前に9ブロックすすむ」をつなごう。

5. 入口の金の床に立とう。緑の実行ボタンを押して、Tキーのチャットで q33 と入力しよう。

6. できたら工房NPCの「完成した・判定」を押そう。床の印はこわさないでね。

ヒントは電球を押してみよう。

```blocks
player.onChat("q33", function () {
    agent.setSlot(1)
    agent.teleport(pos(-8, 0, 1), SOUTH)
    agent.move(FORWARD, 12)
    agent.turn(LEFT_TURN)
    agent.move(FORWARD, 9)
})
```

## Q34 消えた小包

**Q34 消えた小包**

候補座標を配列に入れ、毎回違う場所へ荷物を隠す

1. 新しい「チャットコマンド」を置いて、run を q34 に変えよう。

2. 中に「エージェントのスロットを1にする」をつなごう。工房で用意されたブロックを使うよ。

3. Agentを位置 (-4,1,12)・南向きへ呼んで、「前にブロックを置く」をつなごう。

4. Agentを位置 (-2,3,12)・南向きへ呼んで、「前にブロックを置く」をつなごう。

5. Agentを位置 (0,2,12)・南向きへ呼んで、「前にブロックを置く」をつなごう。

6. Agentを位置 (2,0,12)・南向きへ呼んで、「前にブロックを置く」をつなごう。

7. Agentを位置 (4,4,12)・南向きへ呼んで、「前にブロックを置く」をつなごう。

8. 入口の金の床に立とう。緑の実行ボタンを押して、Tキーのチャットで q34 と入力しよう。

9. できたら工房NPCの「完成した・判定」を押そう。床の印はこわさないでね。

ヒントは電球を押してみよう。

```blocks
player.onChat("q34", function () {
    agent.setSlot(1)
    agent.teleport(pos(-4, 1, 12), SOUTH)
    agent.place(FORWARD)
    agent.teleport(pos(-2, 3, 12), SOUTH)
    agent.place(FORWARD)
    agent.teleport(pos(0, 2, 12), SOUTH)
    agent.place(FORWARD)
    agent.teleport(pos(2, 0, 12), SOUTH)
    agent.place(FORWARD)
    agent.teleport(pos(4, 4, 12), SOUTH)
    agent.place(FORWARD)
})
```

## Q35 市場の人流整理

**Q35 市場の人流整理**

種類や範囲でMobを選び、安全な待機場所へ移動させる

1. 新しい「チャットコマンド」を置いて、run を q35 に変えよう。

2. 中に「エージェントのスロットを1にする」をつなごう。工房で用意されたブロックを使うよ。

3. Agentを位置 (-5,1,12)・東向きへ呼んで、「下にブロックを置く」をつなごう。

4. Agentを位置 (0,1,14)・東向きへ呼んで、「下にブロックを置く」をつなごう。

5. Agentを位置 (5,1,12)・東向きへ呼んで、「下にブロックを置く」をつなごう。

6. 入口の金の床に立とう。緑の実行ボタンを押して、Tキーのチャットで q35 と入力しよう。

7. できたら工房NPCの「完成した・判定」を押そう。床の印はこわさないでね。

ヒントは電球を押してみよう。

```blocks
player.onChat("q35", function () {
    agent.setSlot(1)
    agent.teleport(pos(-5, 1, 12), EAST)
    agent.place(DOWN)
    agent.teleport(pos(0, 1, 14), EAST)
    agent.place(DOWN)
    agent.teleport(pos(5, 1, 12), EAST)
    agent.place(DOWN)
})
```

## Q37 木材切出し計画

**Q37 木材切出し計画**

指定寸法の範囲だけを伐採し、材料を回収する

1. 新しい「チャットコマンド」を置いて、run を q37 に変えよう。

2. 中に「エージェントのスロットを1にする」をつなごう。工房で用意されたブロックを使うよ。

3. Agentを位置 (-3.0,1,10)・東向きへ呼ぼう。

4. 「6回くり返す」の中に「下にブロックを置く」→「前に1ブロックすすむ」をつなごう。

5. 入口の金の床に立とう。緑の実行ボタンを押して、Tキーのチャットで q37 と入力しよう。

6. できたら工房NPCの「完成した・判定」を押そう。床の印はこわさないでね。

ヒントは電球を押してみよう。

```blocks
player.onChat("q37", function () {
    agent.setSlot(1)
    agent.teleport(pos(-3.0, 1, 10), EAST)
    for (let i = 0; i < 6; i++) {
        agent.place(DOWN)
        agent.move(FORWARD, 1)
    }
})
```

## Q38 厩舎の清掃

**Q38 厩舎の清掃**

床を蛇行走査し、汚れだけを除去して敷料を補充する

1. 新しい「チャットコマンド」を置いて、run を q38 に変えよう。

2. 中に「エージェントのスロットを1にする」をつなごう。工房で用意されたブロックを使うよ。

3. Agentを位置 (-6,1,3)・東向きへ呼ぼう。

4. 「4回くり返す」の中に「6回くり返す」を置こう。その中は「下にブロックを置く」→「前に2ブロックすすむ」。

5. 小さいくり返しの外、大きいくり返しの中に「みぎまわり」をつなごう。

6. 入口の金の床に立とう。緑の実行ボタンを押して、Tキーのチャットで q38 と入力しよう。

7. できたら工房NPCの「完成した・判定」を押そう。床の印はこわさないでね。

ヒントは電球を押してみよう。

```blocks
player.onChat("q38", function () {
    agent.setSlot(1)
    agent.teleport(pos(-6, 1, 3), EAST)
    for (let side = 0; side < 4; side++) {
        for (let step = 0; step < 6; step++) {
            agent.place(DOWN)
            agent.move(FORWARD, 2)
        }
        agent.turn(RIGHT_TURN)
    }
})
```

## Q39 薬棚の在庫整理

**Q39 薬棚の在庫整理**

素材を種類別スロットへ移し、不足数を表示する

1. 新しい「チャットコマンド」を置いて、run を q39 に変えよう。

2. 中に「エージェントのスロットを1にする」をつなごう。工房で用意されたブロックを使うよ。

3. Agentを位置 (-8,0,1)・南向きへ呼ぼう。

4. 「前に12ブロックすすむ」→「ひだりまわり」→「前に10ブロックすすむ」をつなごう。

5. 入口の金の床に立とう。緑の実行ボタンを押して、Tキーのチャットで q39 と入力しよう。

6. できたら工房NPCの「完成した・判定」を押そう。床の印はこわさないでね。

ヒントは電球を押してみよう。

```blocks
player.onChat("q39", function () {
    agent.setSlot(1)
    agent.teleport(pos(-8, 0, 1), SOUTH)
    agent.move(FORWARD, 12)
    agent.turn(LEFT_TURN)
    agent.move(FORWARD, 10)
})
```

## Q40 建築家の設計機

**Q40 建築家の設計機**

幅・階数・屋根型を引数化した小屋ビルダーを作る

1. 新しい「チャットコマンド」を置いて、run を q40 に変えよう。

2. 中に「エージェントのスロットを1にする」をつなごう。工房で用意されたブロックを使うよ。

3. Agentを位置 (-4,1,12)・南向きへ呼んで、「前にブロックを置く」をつなごう。

4. Agentを位置 (-2,3,12)・南向きへ呼んで、「前にブロックを置く」をつなごう。

5. Agentを位置 (0,2,12)・南向きへ呼んで、「前にブロックを置く」をつなごう。

6. Agentを位置 (2,0,12)・南向きへ呼んで、「前にブロックを置く」をつなごう。

7. Agentを位置 (4,4,12)・南向きへ呼んで、「前にブロックを置く」をつなごう。

8. 入口の金の床に立とう。緑の実行ボタンを押して、Tキーのチャットで q40 と入力しよう。

9. できたら工房NPCの「完成した・判定」を押そう。床の印はこわさないでね。

ヒントは電球を押してみよう。

```blocks
player.onChat("q40", function () {
    agent.setSlot(1)
    agent.teleport(pos(-4, 1, 12), SOUTH)
    agent.place(FORWARD)
    agent.teleport(pos(-2, 3, 12), SOUTH)
    agent.place(FORWARD)
    agent.teleport(pos(0, 2, 12), SOUTH)
    agent.place(FORWARD)
    agent.teleport(pos(2, 0, 12), SOUTH)
    agent.place(FORWARD)
    agent.teleport(pos(4, 4, 12), SOUTH)
    agent.place(FORWARD)
})
```

## Q42 生垣剪定機

**Q42 生垣剪定機**

高さ上限を超えた葉だけを切って回収する

1. 新しい「チャットコマンド」を置いて、run を q42 に変えよう。

2. 中に「エージェントのスロットを1にする」をつなごう。工房で用意されたブロックを使うよ。

3. Agentを位置 (-4,1,8)・東向きへ呼んで、「下にブロックを置く」をつなごう。

4. Agentを位置 (-2,1,10)・東向きへ呼んで、「下にブロックを置く」をつなごう。

5. Agentを位置 (0,1,8)・東向きへ呼んで、「下にブロックを置く」をつなごう。

6. Agentを位置 (2,1,10)・東向きへ呼んで、「下にブロックを置く」をつなごう。

7. Agentを位置 (4,1,8)・東向きへ呼んで、「下にブロックを置く」をつなごう。

8. 入口の金の床に立とう。緑の実行ボタンを押して、Tキーのチャットで q42 と入力しよう。

9. できたら工房NPCの「完成した・判定」を押そう。床の印はこわさないでね。

ヒントは電球を押してみよう。

```blocks
player.onChat("q42", function () {
    agent.setSlot(1)
    agent.teleport(pos(-4, 1, 8), EAST)
    agent.place(DOWN)
    agent.teleport(pos(-2, 1, 10), EAST)
    agent.place(DOWN)
    agent.teleport(pos(0, 1, 8), EAST)
    agent.place(DOWN)
    agent.teleport(pos(2, 1, 10), EAST)
    agent.place(DOWN)
    agent.teleport(pos(4, 1, 8), EAST)
    agent.place(DOWN)
})
```

## Q43 井戸の安全柵

**Q43 井戸の安全柵**

井戸の周囲へ角を数えながら柵と入口を作る

1. 新しい「チャットコマンド」を置いて、run を q43 に変えよう。

2. 中に「エージェントのスロットを1にする」をつなごう。工房で用意されたブロックを使うよ。

3. Agentを位置 (-4.0,1,10)・東向きへ呼ぼう。

4. 「8回くり返す」の中に「下にブロックを置く」→「前に1ブロックすすむ」をつなごう。

5. 入口の金の床に立とう。緑の実行ボタンを押して、Tキーのチャットで q43 と入力しよう。

6. できたら工房NPCの「完成した・判定」を押そう。床の印はこわさないでね。

ヒントは電球を押してみよう。

```blocks
player.onChat("q43", function () {
    agent.setSlot(1)
    agent.teleport(pos(-4.0, 1, 10), EAST)
    for (let i = 0; i < 8; i++) {
        agent.place(DOWN)
        agent.move(FORWARD, 1)
    }
})
```

## Q44 住居番号印刷

**Q44 住居番号印刷**

家の座標リストから連番を壁へ表示する

1. 新しい「チャットコマンド」を置いて、run を q44 に変えよう。

2. 中に「エージェントのスロットを1にする」をつなごう。工房で用意されたブロックを使うよ。

3. Agentを位置 (-6,1,3)・東向きへ呼ぼう。

4. 「4回くり返す」の中に「6回くり返す」を置こう。その中は「下にブロックを置く」→「前に2ブロックすすむ」。

5. 小さいくり返しの外、大きいくり返しの中に「みぎまわり」をつなごう。

6. 入口の金の床に立とう。緑の実行ボタンを押して、Tキーのチャットで q44 と入力しよう。

7. できたら工房NPCの「完成した・判定」を押そう。床の印はこわさないでね。

ヒントは電球を押してみよう。

```blocks
player.onChat("q44", function () {
    agent.setSlot(1)
    agent.teleport(pos(-6, 1, 3), EAST)
    for (let side = 0; side < 4; side++) {
        for (let step = 0; step < 6; step++) {
            agent.place(DOWN)
            agent.move(FORWARD, 2)
        }
        agent.turn(RIGHT_TURN)
    }
})
```

## Q45 夜間照明当番

**Q45 夜間照明当番**

夜だけ街灯を点灯し、朝になったら元へ戻す

1. 新しい「チャットコマンド」を置いて、run を q45 に変えよう。

2. 中に「エージェントのスロットを1にする」をつなごう。工房で用意されたブロックを使うよ。

3. Agentを位置 (-8,0,1)・南向きへ呼ぼう。

4. 「前に12ブロックすすむ」→「ひだりまわり」→「前に6ブロックすすむ」をつなごう。

5. 入口の金の床に立とう。緑の実行ボタンを押して、Tキーのチャットで q45 と入力しよう。

6. できたら工房NPCの「完成した・判定」を押そう。床の印はこわさないでね。

ヒントは電球を押してみよう。

```blocks
player.onChat("q45", function () {
    agent.setSlot(1)
    agent.teleport(pos(-8, 0, 1), SOUTH)
    agent.move(FORWARD, 12)
    agent.turn(LEFT_TURN)
    agent.move(FORWARD, 6)
})
```

## Q47 煙突安全検査

**Q47 煙突安全検査**

煙突上部の塞がりを検知し、安全な高さまで除去する

1. 新しい「チャットコマンド」を置いて、run を q47 に変えよう。

2. 中に「エージェントのスロットを1にする」をつなごう。工房で用意されたブロックを使うよ。

3. Agentを位置 (-5,1,12)・東向きへ呼んで、「下にブロックを置く」をつなごう。

4. Agentを位置 (0,1,14)・東向きへ呼んで、「下にブロックを置く」をつなごう。

5. Agentを位置 (5,1,12)・東向きへ呼んで、「下にブロックを置く」をつなごう。

6. 入口の金の床に立とう。緑の実行ボタンを押して、Tキーのチャットで q47 と入力しよう。

7. できたら工房NPCの「完成した・判定」を押そう。床の印はこわさないでね。

ヒントは電球を押してみよう。

```blocks
player.onChat("q47", function () {
    agent.setSlot(1)
    agent.teleport(pos(-5, 1, 12), EAST)
    agent.place(DOWN)
    agent.teleport(pos(0, 1, 14), EAST)
    agent.place(DOWN)
    agent.teleport(pos(5, 1, 12), EAST)
    agent.place(DOWN)
})
```

## Q48 公園の花植え

**Q48 公園の花植え**

区画内へ重複を避けながら花をランダム配置する

1. 新しい「チャットコマンド」を置いて、run を q48 に変えよう。

2. 中に「エージェントのスロットを1にする」をつなごう。工房で用意されたブロックを使うよ。

3. Agentを位置 (-4,1,8)・東向きへ呼んで、「下にブロックを置く」をつなごう。

4. Agentを位置 (-2,1,10)・東向きへ呼んで、「下にブロックを置く」をつなごう。

5. Agentを位置 (0,1,8)・東向きへ呼んで、「下にブロックを置く」をつなごう。

6. Agentを位置 (2,1,10)・東向きへ呼んで、「下にブロックを置く」をつなごう。

7. Agentを位置 (4,1,8)・東向きへ呼んで、「下にブロックを置く」をつなごう。

8. 入口の金の床に立とう。緑の実行ボタンを押して、Tキーのチャットで q48 と入力しよう。

9. できたら工房NPCの「完成した・判定」を押そう。床の印はこわさないでね。

ヒントは電球を押してみよう。

```blocks
player.onChat("q48", function () {
    agent.setSlot(1)
    agent.teleport(pos(-4, 1, 8), EAST)
    agent.place(DOWN)
    agent.teleport(pos(-2, 1, 10), EAST)
    agent.place(DOWN)
    agent.teleport(pos(0, 1, 8), EAST)
    agent.place(DOWN)
    agent.teleport(pos(2, 1, 10), EAST)
    agent.place(DOWN)
    agent.teleport(pos(4, 1, 8), EAST)
    agent.place(DOWN)
})
```

## Q49 王都郵便経路

**Q49 王都郵便経路**

複数候補から短い配達順を比較して実行する

1. 新しい「チャットコマンド」を置いて、run を q49 に変えよう。

2. 中に「エージェントのスロットを1にする」をつなごう。工房で用意されたブロックを使うよ。

3. Agentを位置 (-3.0,1,10)・東向きへ呼ぼう。

4. 「6回くり返す」の中に「下にブロックを置く」→「前に1ブロックすすむ」をつなごう。

5. 入口の金の床に立とう。緑の実行ボタンを押して、Tキーのチャットで q49 と入力しよう。

6. できたら工房NPCの「完成した・判定」を押そう。床の印はこわさないでね。

ヒントは電球を押してみよう。

```blocks
player.onChat("q49", function () {
    agent.setSlot(1)
    agent.teleport(pos(-3.0, 1, 10), EAST)
    for (let i = 0; i < 6; i++) {
        agent.place(DOWN)
        agent.move(FORWARD, 1)
    }
})
```

## Q50 Agentかくれんぼ

**Q50 Agentかくれんぼ**

隠れ場所をランダム選択し、ヒントを段階表示する

1. 新しい「チャットコマンド」を置いて、run を q50 に変えよう。

2. 中に「エージェントのスロットを1にする」をつなごう。工房で用意されたブロックを使うよ。

3. Agentを位置 (-6,1,3)・東向きへ呼ぼう。

4. 「4回くり返す」の中に「6回くり返す」を置こう。その中は「下にブロックを置く」→「前に2ブロックすすむ」。

5. 小さいくり返しの外、大きいくり返しの中に「みぎまわり」をつなごう。

6. 入口の金の床に立とう。緑の実行ボタンを押して、Tキーのチャットで q50 と入力しよう。

7. できたら工房NPCの「完成した・判定」を押そう。床の印はこわさないでね。

ヒントは電球を押してみよう。

```blocks
player.onChat("q50", function () {
    agent.setSlot(1)
    agent.teleport(pos(-6, 1, 3), EAST)
    for (let side = 0; side < 4; side++) {
        for (let step = 0; step < 6; step++) {
            agent.place(DOWN)
            agent.move(FORWARD, 2)
        }
        agent.turn(RIGHT_TURN)
    }
})
```

## Q52 自動耕作Agent

**Q52 自動耕作Agent**

作物列を進み、耕す・植える・補充を繰り返す

1. 新しい「チャットコマンド」を置いて、run を q52 に変えよう。

2. 中に「エージェントのスロットを1にする」をつなごう。工房で用意されたブロックを使うよ。

3. Agentを位置 (-4,1,12)・南向きへ呼んで、「前にブロックを置く」をつなごう。

4. Agentを位置 (-2,3,12)・南向きへ呼んで、「前にブロックを置く」をつなごう。

5. Agentを位置 (0,2,12)・南向きへ呼んで、「前にブロックを置く」をつなごう。

6. Agentを位置 (2,0,12)・南向きへ呼んで、「前にブロックを置く」をつなごう。

7. Agentを位置 (4,4,12)・南向きへ呼んで、「前にブロックを置く」をつなごう。

8. 入口の金の床に立とう。緑の実行ボタンを押して、Tキーのチャットで q52 と入力しよう。

9. できたら工房NPCの「完成した・判定」を押そう。床の印はこわさないでね。

ヒントは電球を押してみよう。

```blocks
player.onChat("q52", function () {
    agent.setSlot(1)
    agent.teleport(pos(-4, 1, 12), SOUTH)
    agent.place(FORWARD)
    agent.teleport(pos(-2, 3, 12), SOUTH)
    agent.place(FORWARD)
    agent.teleport(pos(0, 2, 12), SOUTH)
    agent.place(FORWARD)
    agent.teleport(pos(2, 0, 12), SOUTH)
    agent.place(FORWARD)
    agent.teleport(pos(4, 4, 12), SOUTH)
    agent.place(FORWARD)
})
```

## Q53 灌漑路の掘削

**Q53 灌漑路の掘削**

一定間隔で水路を掘り、端まで来たら次列へ移る

1. 新しい「チャットコマンド」を置いて、run を q53 に変えよう。

2. 中に「エージェントのスロットを1にする」をつなごう。工房で用意されたブロックを使うよ。

3. Agentを位置 (-5,1,12)・東向きへ呼んで、「下にブロックを置く」をつなごう。

4. Agentを位置 (0,1,14)・東向きへ呼んで、「下にブロックを置く」をつなごう。

5. Agentを位置 (5,1,12)・東向きへ呼んで、「下にブロックを置く」をつなごう。

6. 入口の金の床に立とう。緑の実行ボタンを押して、Tキーのチャットで q53 と入力しよう。

7. できたら工房NPCの「完成した・判定」を押そう。床の印はこわさないでね。

ヒントは電球を押してみよう。

```blocks
player.onChat("q53", function () {
    agent.setSlot(1)
    agent.teleport(pos(-5, 1, 12), EAST)
    agent.place(DOWN)
    agent.teleport(pos(0, 1, 14), EAST)
    agent.place(DOWN)
    agent.teleport(pos(5, 1, 12), EAST)
    agent.place(DOWN)
})
```

## Q54 王立果樹園

**Q54 王立果樹園**

樹木が重ならない間隔を計算し、格子状に苗木を植える

1. 新しい「チャットコマンド」を置いて、run を q54 に変えよう。

2. 中に「エージェントのスロットを1にする」をつなごう。工房で用意されたブロックを使うよ。

3. Agentを位置 (-4,1,8)・東向きへ呼んで、「下にブロックを置く」をつなごう。

4. Agentを位置 (-2,1,10)・東向きへ呼んで、「下にブロックを置く」をつなごう。

5. Agentを位置 (0,1,8)・東向きへ呼んで、「下にブロックを置く」をつなごう。

6. Agentを位置 (2,1,10)・東向きへ呼んで、「下にブロックを置く」をつなごう。

7. Agentを位置 (4,1,8)・東向きへ呼んで、「下にブロックを置く」をつなごう。

8. 入口の金の床に立とう。緑の実行ボタンを押して、Tキーのチャットで q54 と入力しよう。

9. できたら工房NPCの「完成した・判定」を押そう。床の印はこわさないでね。

ヒントは電球を押してみよう。

```blocks
player.onChat("q54", function () {
    agent.setSlot(1)
    agent.teleport(pos(-4, 1, 8), EAST)
    agent.place(DOWN)
    agent.teleport(pos(-2, 1, 10), EAST)
    agent.place(DOWN)
    agent.teleport(pos(0, 1, 8), EAST)
    agent.place(DOWN)
    agent.teleport(pos(2, 1, 10), EAST)
    agent.place(DOWN)
    agent.teleport(pos(4, 1, 8), EAST)
    agent.place(DOWN)
})
```

## Q55 病害区画調査

**Q55 病害区画調査**

異常を示すブロックを検出し、地点数と座標を報告する

1. 新しい「チャットコマンド」を置いて、run を q55 に変えよう。

2. 中に「エージェントのスロットを1にする」をつなごう。工房で用意されたブロックを使うよ。

3. Agentを位置 (-4.0,1,10)・東向きへ呼ぼう。

4. 「8回くり返す」の中に「下にブロックを置く」→「前に1ブロックすすむ」をつなごう。

5. 入口の金の床に立とう。緑の実行ボタンを押して、Tキーのチャットで q55 と入力しよう。

6. できたら工房NPCの「完成した・判定」を押そう。床の印はこわさないでね。

ヒントは電球を押してみよう。

```blocks
player.onChat("q55", function () {
    agent.setSlot(1)
    agent.teleport(pos(-4.0, 1, 10), EAST)
    for (let i = 0; i < 8; i++) {
        agent.place(DOWN)
        agent.move(FORWARD, 1)
    }
})
```

## Q57 家畜の仕分け

**Q57 家畜の仕分け**

動物の種類ごとに選択し、対応する囲いへ移動させる

1. 新しい「チャットコマンド」を置いて、run を q57 に変えよう。

2. 中に「エージェントのスロットを1にする」をつなごう。工房で用意されたブロックを使うよ。

3. Agentを位置 (-8,0,1)・南向きへ呼ぼう。

4. 「前に12ブロックすすむ」→「ひだりまわり」→「前に8ブロックすすむ」をつなごう。

5. 入口の金の床に立とう。緑の実行ボタンを押して、Tキーのチャットで q57 と入力しよう。

6. できたら工房NPCの「完成した・判定」を押そう。床の印はこわさないでね。

ヒントは電球を押してみよう。

```blocks
player.onChat("q57", function () {
    agent.setSlot(1)
    agent.teleport(pos(-8, 0, 1), SOUTH)
    agent.move(FORWARD, 12)
    agent.turn(LEFT_TURN)
    agent.move(FORWARD, 8)
})
```

## Q58 王都牧場の繁殖計画

**Q58 王都牧場の繁殖計画**

入力数に応じて動物を各囲いへ均等に出現させる

1. 新しい「チャットコマンド」を置いて、run を q58 に変えよう。

2. 中に「エージェントのスロットを1にする」をつなごう。工房で用意されたブロックを使うよ。

3. Agentを位置 (-4,1,12)・南向きへ呼んで、「前にブロックを置く」をつなごう。

4. Agentを位置 (-2,3,12)・南向きへ呼んで、「前にブロックを置く」をつなごう。

5. Agentを位置 (0,2,12)・南向きへ呼んで、「前にブロックを置く」をつなごう。

6. Agentを位置 (2,0,12)・南向きへ呼んで、「前にブロックを置く」をつなごう。

7. Agentを位置 (4,4,12)・南向きへ呼んで、「前にブロックを置く」をつなごう。

8. 入口の金の床に立とう。緑の実行ボタンを押して、Tキーのチャットで q58 と入力しよう。

9. できたら工房NPCの「完成した・判定」を押そう。床の印はこわさないでね。

ヒントは電球を押してみよう。

```blocks
player.onChat("q58", function () {
    agent.setSlot(1)
    agent.teleport(pos(-4, 1, 12), SOUTH)
    agent.place(FORWARD)
    agent.teleport(pos(-2, 3, 12), SOUTH)
    agent.place(FORWARD)
    agent.teleport(pos(0, 2, 12), SOUTH)
    agent.place(FORWARD)
    agent.teleport(pos(2, 0, 12), SOUTH)
    agent.place(FORWARD)
    agent.teleport(pos(4, 4, 12), SOUTH)
    agent.place(FORWARD)
})
```

## Q59 羊飼いの誘導試験

**Q59 羊飼いの誘導試験**

複数の中継座標を使い、群れを門まで段階移動させる

1. 新しい「チャットコマンド」を置いて、run を q59 に変えよう。

2. 中に「エージェントのスロットを1にする」をつなごう。工房で用意されたブロックを使うよ。

3. Agentを位置 (-5,1,12)・東向きへ呼んで、「下にブロックを置く」をつなごう。

4. Agentを位置 (0,1,14)・東向きへ呼んで、「下にブロックを置く」をつなごう。

5. Agentを位置 (5,1,12)・東向きへ呼んで、「下にブロックを置く」をつなごう。

6. 入口の金の床に立とう。緑の実行ボタンを押して、Tキーのチャットで q59 と入力しよう。

7. できたら工房NPCの「完成した・判定」を押そう。床の印はこわさないでね。

ヒントは電球を押してみよう。

```blocks
player.onChat("q59", function () {
    agent.setSlot(1)
    agent.teleport(pos(-5, 1, 12), EAST)
    agent.place(DOWN)
    agent.teleport(pos(0, 1, 14), EAST)
    agent.place(DOWN)
    agent.teleport(pos(5, 1, 12), EAST)
    agent.place(DOWN)
})
```

## Q60 自動給餌巡回

**Q60 自動給餌巡回**

各囲いを巡り、残数を確認しながら必要量だけ資材を下ろす

1. 新しい「チャットコマンド」を置いて、run を q60 に変えよう。

2. 中に「エージェントのスロットを1にする」をつなごう。工房で用意されたブロックを使うよ。

3. Agentを位置 (-4,1,8)・東向きへ呼んで、「下にブロックを置く」をつなごう。

4. Agentを位置 (-2,1,10)・東向きへ呼んで、「下にブロックを置く」をつなごう。

5. Agentを位置 (0,1,8)・東向きへ呼んで、「下にブロックを置く」をつなごう。

6. Agentを位置 (2,1,10)・東向きへ呼んで、「下にブロックを置く」をつなごう。

7. Agentを位置 (4,1,8)・東向きへ呼んで、「下にブロックを置く」をつなごう。

8. 入口の金の床に立とう。緑の実行ボタンを押して、Tキーのチャットで q60 と入力しよう。

9. できたら工房NPCの「完成した・判定」を押そう。床の印はこわさないでね。

ヒントは電球を押してみよう。

```blocks
player.onChat("q60", function () {
    agent.setSlot(1)
    agent.teleport(pos(-4, 1, 8), EAST)
    agent.place(DOWN)
    agent.teleport(pos(-2, 1, 10), EAST)
    agent.place(DOWN)
    agent.teleport(pos(0, 1, 8), EAST)
    agent.place(DOWN)
    agent.teleport(pos(2, 1, 10), EAST)
    agent.place(DOWN)
    agent.teleport(pos(4, 1, 8), EAST)
    agent.place(DOWN)
})
```

