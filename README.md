# Minecraft MakeCode チュートリアル教材

このリポジトリは、Minecraft Education の授業で使う MakeCode 自作チュートリアル教材です。

生徒には MakeCode のチュートリアルURLを配り、Minecraft Education の Code Builder から開いて使います。

## 教材

- `agent-square.md`: エージェントで四角を作ろう

## 生徒用URL

GitHubに公開したあと、次の形で生徒へ配布します。

```text
https://minecraft.makecode.com/#tutorial:https://github.com/<owner>/<repo>/agent-square
```

`<owner>` と `<repo>` は、実際のGitHubユーザー名または組織名、リポジトリ名に置き換えてください。

例:

```text
https://minecraft.makecode.com/#tutorial:https://github.com/example/minecraft-makecode-lessons/agent-square
```

## 先生側の準備

1. このリポジトリをGitHubに公開します。
2. `https://makecode.com/tutorial-tool` を開きます。
3. target に `Minecraft` を選びます。
4. `agent-square.md` の内容を貼り付けます。
5. `Run Tutorial` でステップ表示とブロック表示を確認します。
6. GitHub公開後の生徒用URLでも読み込みを確認します。

## 生徒側の手順

1. Minecraft Education を開きます。
2. ワールドに入ります。
3. キーボードの `C` キーで Code Builder を開きます。
4. Microsoft MakeCode を選びます。
5. 先生から配られたURLを開きます。
6. チュートリアルの手順どおりにブロックを作ります。
7. 緑の実行ボタンを押してから、Minecraftのチャットで `tp`、`rl`、`pd`、`square` の順に入力します。

## 授業中の確認ポイント

- `tp` でエージェントが自分の近くへ来ること。
- `rl` でエージェントの1番スロットに砂岩が入ること。
- `pd` のあとにエージェントが動くと、ブロックを置きながら進むこと。
- `square` で前へ5ブロック進んで左へ曲がる動きを4回くり返すこと。

## よくあるつまずき

- ブロックを置かない場合は、先に `rl` を実行しているか確認します。
- エージェントが動かない場合は、障害物がない平らな場所で `tp` からやり直します。
- MakeCodeでコードを作ったあと、緑の実行ボタンを押しているか確認します。
- チュートリアルを更新しても古い内容が出る場合は、MakeCodeのキャッシュが残っている可能性があります。シークレットウィンドウで開くか、MakeCode側でリリースを作成してから再確認します。

## 参考

- [MakeCode Tutorials](https://makecode.com/writing-docs/tutorials)
- [MakeCode User tutorials](https://makecode.com/writing-docs/user-tutorials)
- [MakeCode Control options](https://makecode.com/writing-docs/tutorials/control-options)
- [Minecraft Education Code Builder](https://edusupport.minecraft.net/hc/en-us/articles/360047116992-Code-Builder-in-Minecraft-Education)
