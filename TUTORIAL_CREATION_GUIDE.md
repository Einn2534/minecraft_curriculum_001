# 新しいチュートリアルを作る手順

Minecraft Education の MakeCode 用チュートリアルを、このリポジトリに追加・更新するときの手順です。

## 1. 作る内容を決める

先に次の4つを決めます。

- タイトル: 生徒に見せる名前
- ファイル名: URL に使う名前。半角英数字と `-` を使う
- 完成時の動き: Minecraft で何が起きれば成功か
- 使うブロック: `プレイヤー`、`ブロック`、`モブ`、`ポジション` など

例:

```text
タイトル: はねるブタ
ファイル名: bouncing-pigs.md
完成時の動き: スライムの上ではねるとブタが出る
配布URL: https://minecraft.makecode.com/#tutorial:https://github.com/Einn2534/minecraft_curriculum_001/bouncing-pigs
```

## 2. Markdown ファイルを作る

新しい `.md` ファイルを作ります。

基本形:

````markdown
# チュートリアルのタイトル

## はじめに @unplugged

このチュートリアルで作るものを説明します。

![完成イメージ](https://raw.githubusercontent.com/Einn2534/minecraft_curriculum_001/master/assets/example.png)

## Step 1: 最初の手順

生徒にやってほしいことを書きます。

```blocks
player.onChat("start", function () {
})
```
````

ポイント:

- `#` の見出しがチュートリアル名になります。
- `## はじめに @unplugged` は説明だけの画面になります。
- 各 `##` 見出しが1ステップになります。
- ` ```blocks ` のコードは、そのステップのヒントとして表示されます。
- 正解コードを最初から見せたくない場合は、`### @explicitHints true` を書きません。

## 3. ブロックのマークを本文に出す

本文中にカテゴリの色付きマークを出したいときは、MakeCode のインラインブロック参照を使います。

必ずバッククォート2個で囲みます。

```markdown
``||player:チャットされたとき||``
``||blocks:スライムで満たす||``
``||mobs:ブタを出す||``
``||positions:ランダムな場所||``
```

よくある間違い:

```markdown
||player:チャットされたとき||
```

この書き方だと、マークにならず `||player:...||` がそのまま表示されます。

## 4. 画像を入れる

画像は `assets/` に入れます。

例:

```text
assets/bouncing-pigs-preview.png
```

Markdown では GitHub の raw URL を使います。

```markdown
![完成イメージ](https://raw.githubusercontent.com/Einn2534/minecraft_curriculum_001/master/assets/bouncing-pigs-preview.png)
```

注意:

- 一時フォルダや自分のPCのパスは使いません。
- GitHub に push されていない画像は MakeCode から表示できません。
- 画像を変更したあとも、MakeCode 側で Release が必要です。

## 5. pxt.json に追加する

新しい Markdown ファイルを追加したら、`pxt.json` の `files` に入れます。

例:

```json
"files": [
    "README.md",
    "bouncing-pigs.md",
    "main.ts"
]
```

注意:

- `.md` ファイル名は `files` に入れます。
- `main.ts` は、チュートリアル開始時に実行したいコードがないなら空でよいです。
- MakeCode が `targetVersions` を自動追加した場合は、消さずにコミットします。

## 6. ローカルで確認する

公開前に、次のどちらかで確認します。

- `https://makecode.com/tutorial-tool` で target を `Minecraft` にして確認する。
- Minecraft MakeCode に GitHub リポジトリを読み込み、左の Explorer で `.md` の実験アイコンを押す。

確認ポイント:

- 日本語が文字化けしていない。
- 画像が表示される。
- 本文のブロック参照マークが表示される。
- 正解コードが本文に丸見えになっていない。
- ヒントを開くと必要なコードが出る。
- 最後までステップ移動できる。

## 7. GitHub に反映する

変更を commit して push します。

例:

```powershell
git status --short
git add README.md pxt.json 新しいファイル.md assets/画像.png
git commit -m "新しいチュートリアルを追加"
git push origin master
```

MakeCode エディタ上でローカル変更が出ている場合は、MakeCode の GitHub 画面で次を行います。

1. 変更内容を確認する。
2. 変更点の説明を書く。
3. `変更をコミットしてプッシュ` を押す。

## 8. MakeCode 側で Release を作る

GitHub に push しただけでは、MakeCode のチュートリアル表示が古いままになることがあります。

必ず MakeCode エディタ側で Release を作ります。

手順:

1. `https://minecraft.makecode.com/` を開く。
2. `読み込む` から `あなたのGitHubリポジトリ...` を選ぶ。
3. `Einn2534/minecraft_curriculum_001` を開く。
4. 必要なら `変更を取得（プル）` を押す。
5. 左下の GitHub アイコンを押す。
6. `Release` または `Create release` を押す。

重要:

- GitHub.com の `Create a new release` ではなく、MakeCode エディタ側の Release を使います。
- MakeCode 側の Release を作ると、クラウドキャッシュが更新されます。

## 9. 生徒に配る URL を作る

URL は `.md` を外して作ります。

```text
https://minecraft.makecode.com/#tutorial:https://github.com/Einn2534/minecraft_curriculum_001/<ファイル名>
```

例:

```text
https://minecraft.makecode.com/#tutorial:https://github.com/Einn2534/minecraft_curriculum_001/bouncing-pigs
```

今の `bouncing-pigs.md` を使う場合:

```text
https://minecraft.makecode.com/#tutorial:https://github.com/Einn2534/minecraft_curriculum_001/bouncing-pigs
```

## 10. 反映されないとき

順番に確認します。

1. GitHub のファイルが最新になっているか。
2. 画像が `assets/` に push されているか。
3. 新しい `.md` が `pxt.json` の `files` に入っているか。
4. MakeCode エディタ側で Release を作ったか。
5. シークレットウィンドウで開き直したか。
6. URL の最後が `.md` なしになっているか。

それでも古い場合は、数分待ってから再度開きます。

## 参考リンク

- [MakeCode Tutorials](https://makecode.com/writing-docs/tutorials)
- [MakeCode User tutorials](https://makecode.com/writing-docs/user-tutorials)
- [MakeCode Control options](https://makecode.com/writing-docs/tutorials/control-options)
- [pxt-tutorial-sample](https://github.com/microsoft/pxt-tutorial-sample)
