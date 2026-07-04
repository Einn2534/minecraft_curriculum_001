# Minecraft MakeCode 教材

Minecraft Education の Code Builder と MakeCode を使って、イベントとブロック配置を練習する教材です。

この教材では、チャット命令でスライムブロックの場所を作り、プレイヤーがはねるたびにブタを出します。

## 教材一覧

- `bouncing-pigs.md`: はねるブタのチュートリアル

## 作成手順

- [TUTORIAL_CREATION_GUIDE.md](TUTORIAL_CREATION_GUIDE.md): 新しいチュートリアルを作るときの手順書

## 授業のねらい

- チャット命令でプログラムを実行する。
- 指定した範囲をスライムブロックで満たす。
- プレイヤーがはねたときのイベントを使う。
- モブを指定した場所に出す。
- ランダムな位置を使って動きのある結果にする。

## 生徒に配るURL

GitHub に公開したあと、次の形で URL を配布します。

```text
https://minecraft.makecode.com/#tutorial:https://github.com/<owner>/<repo>/bouncing-pigs
```

`<owner>` と `<repo>` は、実際の GitHub ユーザー名または組織名、リポジトリ名に置き換えてください。

このリポジトリの場合:

```text
https://minecraft.makecode.com/#tutorial:https://github.com/Einn2534/minecraft_curriculum_001/bouncing-pigs
```

## 先生側の準備

1. このリポジトリを GitHub に公開します。
2. `https://makecode.com/tutorial-tool` を開きます。
3. target で `Minecraft` を選びます。
4. `bouncing-pigs.md` の内容を貼り付けます。
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
8. Minecraft のチャットで `slime` と入力します。
9. スライムブロックの上ではねて、ブタが出てくるか確認します。

## 完成時の動き

1. `slime` で、広いスライムブロックの場所ができる。
2. プレイヤーがスライムの上ではねる。
3. はねるたびに、空中のランダムな場所からブタが出てくる。

## 授業中の確認ポイント

- 実行前に緑のボタンを押しているか。
- チャット命令が `slime` になっているか。
- スライムブロックの範囲が `-20` から `20` になっているか。
- `プレイヤーがはねたとき` の中に `ブタを出す` 命令が入っているか。
- ランダムな位置の範囲が `~-10 ~20 ~-10` から `~10 ~20 ~10` になっているか。

## よくあるつまずき

- スライムが出ない場合は、先に `slime` をチャットで実行しているか確認します。
- ブタが出ない場合は、スライムの上ではねているか確認します。
- ブタが地面に出る場合は、Y 座標が `20` になっているか確認します。
- 古い内容が出る場合は、MakeCode のキャッシュが残っている可能性があります。シークレットウィンドウで開くか、MakeCode 側で再読み込みして確認します。

## 発展課題

- 出てくるモブをブタ以外に変える。
- スライムの場所をもっと広くする。
- ブタが出てくる高さを変える。
- ランダムな範囲を広げる。

## 参考

- [MakeCode Tutorials](https://makecode.com/writing-docs/tutorials)
- [MakeCode User tutorials](https://makecode.com/writing-docs/user-tutorials)
- [MakeCode Bouncing Pigs](https://minecraft.makecode.com/tutorials/bouncing-pigs)
- [Minecraft Education Code Builder](https://edusupport.minecraft.net/hc/en-us/articles/360047116992-Code-Builder-in-Minecraft-Education)
