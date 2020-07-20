# 関数定義とゲーム全体の構造

シーンとシーン遷移がわかったので、ここではゲーム全体の構造を説明していきます。

---

## ゲーム全体の骨格

以下のコードとその実行結果を見てください。

```
-- Main
function main()
   while true do
      titleScene()
      playScene()
      gameoverScene()
   end
end

-- Title Scene
function titleScene()
   x8.cls()
   x8.fnt("TITILE", 40, 40)
   x8.wait()
   while true do
      if x8.btntrg(4) then break end
      x8.wait()
   end
end

-- Game Over Scene
function gameoverScene()
   x8.cls()
   x8.fnt("GAME OVER", 40, 60)
   x8.wait(30 * 3)
end

-- Play Scene
function playScene()
   x8.cls()
   x8.fnt("PLAY", 40, 50)
   x8.wait()
   while true do
      if x8.btntrg(4) then break end
      x8.wait()
   end
end

-- Start the game
main()
```

![](imgs/tutorial_01/x8_tuto_01_scenes.gif)

[シーンとシーン遷移](tutorial_01_05.md#シーン遷移のコード)で紹介したコードと全く同じ動きになります。

これは、**B.BREAKER**のコード全体から骨格だけを抜き出したものです。各シーンのコードが分割されているのがわかります。

---

## 関数定義

`function`は関数を作る（**関数定義**）ときに使います。こんな形をしています。

> `function` 関数名 `(` [パラメータリスト] `)` ブロック `end`

Note: このように文の形（**構文**）を説明する際に角括弧 **[ ]** と中括弧 **{ }** には特別な意味があります。**[a]** は **[a]** の部分が、あってもなくてもよいこをと表し、**{a}** は **{a}** の部分が、何回連続してもよく、また無くてもよいことを表しています。

**[パラメータリスト]** は引数を受け取るための変数名をカンマ`,`区切りで並べたものです。引数が不要なら [パラメータリスト] も不要です。

**ブロック** には関数が行う処理を書きます。

**関数定義は実際には、関数を作って変数に代入する式で、関数名は定義した関数を入れる変数名**です。関数定義は以下のように書くこともでき、同じ意味になります。

> 変数名 `= function (` [パラメータリスト] `)` ブロック `end`

---

## メイン関数

`main`関数の部分を見てください。

```
-- Main
function main()
   while true do
      titleScene()
      playScene()
      gameoverScene()
   end
end
```

この関数は、ゲーム全体の起点となり、各シーンを順番に呼び出す無限ループになっています。

Hint: このように、プログラムの起点となるような関数のことを**メイン関数**と呼ぶことがあります。Lua言語では特別な意味はありませんが、用語としてはよく出てきます。

---

## 全体の構造

もう一度、コード全体を見てみましょう。

```
-- Main
function main()
   while true do
      titleScene()
      playScene()
      gameoverScene()
   end
end

-- Title Scene
function titleScene()
   x8.cls()
   x8.fnt("TITILE", 40, 40)
   x8.wait()
   while true do
      if x8.btntrg(4) then break end
      x8.wait()
   end
end

-- Game Over Scene
function gameoverScene()
   x8.cls()
   x8.fnt("GAME OVER", 40, 60)
   x8.wait(30 * 3)
end

-- Play Scene
function playScene()
   x8.cls()
   x8.fnt("PLAY", 40, 50)
   x8.wait()
   while true do
      if x8.btntrg(4) then break end
      x8.wait()
   end
end

-- Start the game
main()
```

各シーン内の処理は既にわかっているので省略し、構造だけに着目すると以下のような形になります。

```
-- Main
メイン関数定義

-- Title Scene
タイトルシーン関数定義

-- Game Over Scene
ゲームオーバーシーン関数定義

-- Play Scene
プレイシーン関数定義

-- Start the game
メイン関数の呼び出し
```

**関数は定義しただけでは実行されません。**コードの最後でメイン関数を呼び出して、実行を開始しています。

**メイン関数の呼び出しをコードの最後で行っているのには理由があります。**試しにメイン関数呼び出しを`function playScene()`の直前に移動すると、メイン関数内の`playScene()`のところでエラーになります。これは、`playScene`関数を定義するまえに呼び出してしまうためです。

**変数は最初の代入が行われるまで、値が`nil`（値が無いという意味）になっています。**変数`playScene`を、その関数定義を実行する前（**関数を代入する前**）に呼び出そうとすると、まだ値が`nil`なためエラー（`nil`は呼び出せない）になってしまうのです。

このように、関数定義があるプログラムの場合、処理の起点を最後にすると上記のような問題を避けられます。

Note: うっかりして、代入するまえの変数を使ってしまい、エラーになったり意図しない動作になることはよくあります。そういうときは、変数への最初の代入がどこなのかと、本当にそこを通っているのかに注意しましょう。

コードがシーン毎に関数に分けられ、全体の流れはメイン関数にまとまっています。将来、シーンを追加したり順番を変えたくなっても、新しいシーン関数を追加してメイン関数から呼び出すだけなので、なんとなくスッキリしてる感じがすると思います。

Hint: とはいえ、シーンや機能毎にプログラムを分けて書くのは、そうしないとごちゃごちゃして困るようになってからで大丈夫です。はじめのうちは余計なことは気にせず、どんどんコードを書いていきましょう。

![](imgs/tutorial_01/x8_tuto_01_scenes.gif)

#### これで **関数定義とゲーム全体の構造** の説明はおしまいです。次行きましょー！！
