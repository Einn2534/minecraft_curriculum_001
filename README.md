# Minecraft MakeCode 教材

Minecraft Education の Code Builder と MakeCode を使って、エージェントに命令を出す練習をする教材です。

この教材では、チャット命令でエージェントを呼び出し、ブロックを持たせ、移動しながら砂岩の四角形を作ります。

## 教材一覧

- `agent-square.md`: エージェントで四角形を作るチュートリアル

## 授業のねらい

- チャット命令でプログラムを実行する。
- エージェントをプレイヤーの位置へ移動させる。
- エージェントにブロックを持たせる。
- くり返し処理を使って同じ動きをまとめる。
- Minecraft の画面でプログラムの結果を確認する。

## 生徒に配るURL

GitHub に公開したあと、次の形で URL を配布します。

```text
https://minecraft.makecode.com/#tutorial:https://github.com/<owner>/<repo>/agent-square
```

`<owner>` と `<repo>` は、実際の GitHub ユーザー名または組織名、リポジトリ名に置き換えてください。

例:

```text
https://minecraft.makecode.com/#tutorial:https://github.com/example/minecraft-makecode-lessons/agent-square
```

## 先生側の準備

1. このリポジトリを GitHub に公開します。
2. `https://makecode.com/tutorial-tool` を開きます。
3. target で `Minecraft` を選びます。
4. `agent-square.md` の内容を貼り付けます。
5. `Run Tutorial` で、各ステップとブロック表示を確認します。
6. GitHub 公開後の URL でも、チュートリアルが開けることを確認します。

## 生徒側の手順

1. Minecraft Education を開きます。
2. ワールドに入ります。
3. キーボードの `C` キーで Code Builder を開きます。
4. Microsoft MakeCode を選びます。
5. 先生から配られた URL を開きます。
6. チュートリアルの手順どおりにブロックを作ります。
7. 緑の実行ボタンを押します。
8. Minecraft のチャットで `tp`、`load`、`pen`、`square` の順に入力します。

## 完成時の動き

1. `tp` でエージェントが自分の近くへ来る。
2. `load` でエージェントに砂岩が入る。
3. `pen` で、歩きながらブロックを置く設定になる。
4. `square` で、5ブロック進んで左に曲がる動きを4回くり返す。

## 授業中の確認ポイント

- 実行前に緑のボタンを押しているか。
- エージェントの1番スロットに砂岩が入っているか。
- エージェントの前に障害物がないか。
- `square` の中に「くり返し 4 回」が入っているか。
- 「前へ 5 ブロック」と「左へ曲がる」の順番になっているか。

## よくあるつまずき

- エージェントが来ない場合は、チャット命令が `tp` になっているか確認します。
- ブロックを置かない場合は、先に `load` と `pen` を実行します。
- 途中で止まる場合は、平らで広い場所に移動して `tp` からやり直します。
- 古い内容が出る場合は、MakeCode のキャッシュが残っている可能性があります。シークレットウィンドウで開くか、MakeCode 側で再読み込みして確認します。

## 発展課題

- 四角形の1辺を `5` から `8` に変える。
- 砂岩以外のブロックに変える。
- 右へ曲がる四角形に変える。
- 三角形や長方形を作る命令を追加する。

## 参考

- [MakeCode Tutorials](https://makecode.com/writing-docs/tutorials)
- [MakeCode User tutorials](https://makecode.com/writing-docs/user-tutorials)
- [MakeCode Control options](https://makecode.com/writing-docs/tutorials/control-options)
- [Minecraft Education Code Builder](https://edusupport.minecraft.net/hc/en-us/articles/360047116992-Code-Builder-in-Minecraft-Education)
