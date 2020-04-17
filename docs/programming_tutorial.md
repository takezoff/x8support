# プログラミングチュートリアル

プログラムはCodeエディタからLua言語（Lua 5.3）を利用して書くことができます。
Codeエディタで入力と表示に対応しているのは、ASCIIコード（半角英数記号）と一部の文字（カナ、特殊記号）だけなことに注意してください。
このサイトをアプリが起動している端末で開けば、下で紹介しているプログラムコードを端末のクリップボードを介してコピー＆ペーストできます。ペーストはCodeエディタの**「CBから貼り付け」**で行います。

---

## Hello World!

<img src="imgs/tutorial/x8_tuto_hello_world.png" width="448">

画面に文字列を表示してみます。
```
x8.fnt("Hello World!",0,0)
```
- `fnt(..)`が文字列を画面に表示する命令（関数）です。（APIという時もあります）
- `x8.`はx8独自のAPIであることを表しています。x8独自APIを使う場合は`x8.`を頭に付けます。
- 関数には処理に必要な情報（引き数）を渡します。`"`で囲まれた部分が表示する文字列で、その後の`0,0`は画面での座標(x,y)を表しています。

---

## プログラムにコメントを入れる

プログラムの中にプログラムとは解釈されないメモ（コメント）を書くことができます。
```
-- Comment @ｺﾒﾝﾄ

--[[
   This is
   all comments.
   @ｺﾚﾊ ｽﾍﾞﾃ ｺﾒﾝﾄ
]]

x8.fnt("Hello World!",0,0) -- Comments until the end of the line @ｷﾞｮｳﾏﾂﾏﾃﾞ ｺﾒﾝﾄ
```
- `--`の後、行の終わりまではコメントになります。（行末コメント）
- `--[[`から`]]`までの間は全てコメントになります。（ブロックコメント）

---

## 図形を描く

<img src="imgs/tutorial/x8_tuto_draw_shapes.png" width="448">

画面に図形を描いてみます。

```
-- Draw shapes on the screen. @ｶﾞﾒﾝﾆ ｽﾞｹｲｦ ﾋﾞｮｳｶﾞ

-- Draw a pixel. @ﾋﾟｸｾﾙｦ ﾋﾞｮｳｶﾞ
x8.pixel(30,20,7)

-- Draw a straight line. @ﾁｮｸｾﾝｦ ﾋﾞｮｳｶﾞ
x8.line(70,30,110,10,8)

-- Draw a filled rectangle. @ﾇﾘﾂﾌﾞｻﾚﾀ ｸｹｲｦ ﾋﾞｮｳｶﾞ
x8.rect(20,50,60,70,9)

-- Draw a rectangle. @ｸｹｲｦ ﾋﾞｮｳｶﾞ
x8.rectbdr(80,45,100,75,11)

-- Draw a filled circle. @ﾇﾘﾂﾌﾞｻﾚﾀ ｴﾝｦ ﾋﾞｮｳｶﾞ
x8.circ(40,100,10,12)

-- Draw a circle. @ｴﾝｦ ﾋﾞｮｳｶﾞ
x8.circbdr(90,100,15,13)
```
- `pixel()`は画面に点を描きます。
- `line()`は始点(x,y)と終点(x,y)を指定して、画面に直線を描きます。
- `rectbdr()`は左上(x,y)と右下(x,y)を指定して、画面に矩形を描きます。
- `rect()`は左上(x,y)と右下(x,y)を指定して、画面に塗りつぶされた矩形を描きます。
- `circbdr()`は中心(x,y)と半径を指定して、画面に円を描きます。
- `circ()`は中心(x,y)と半径を指定して、画面に塗りつぶされた円を描きます。

---

## メインループを作る

![](imgs/tutorial/x8_tuto_main_loop.gif "Main loop")

無限に回るループを作って、プログラムが終了しないようにしてみます。
これは、ゲームでよくあるメインループになります。
```
-- Main Loop @ﾒｲﾝﾙｰﾌﾟ

count = 0 -- Frame counter @ﾌﾚｰﾑｶｳﾝﾀ

-- Infinite loop @ﾑｹﾞﾝﾙｰﾌﾟ
while true do

   -- You must always call wait() in an infinite loop. @ﾑｹﾞﾝﾙｰﾌﾟﾅｲﾃﾞﾊ ｶﾅﾗｽﾞ wait() ｦ ﾖﾌﾞ
   x8.wait()

   -- Clean the screen. @ｶﾞﾒﾝｦ ｸﾘｱ
   x8.cls()

   -- Here is the processing in the frame. @ｺｺﾆ ﾌﾚｰﾑﾃﾞﾉ ｼｮﾘｦ ｷｼﾞｭﾂｼﾏｽ
   x8.fnt(count, 0, 0)
   count = count + 1

end
```
- 無限ループ内では、必ず`wait()`を呼ぶ必要があることに注意してください。
- `wait()`が無い場合、一定時間でタイムアウトエラーによりプログラムが停止します。
- `cls()`は画面に描かれたものを全て消します。

---

## 図形をランダムにたくさん描く

![](imgs/tutorial/x8_tuto_draw_circles.gif "Draw circles")

たくさんの円をランダムに描いてみます。

```
-- Draw a lot of circles. @ﾀｸｻﾝﾉ ｴﾝｦ ﾋﾞｮｳｶﾞ

-- Main loop. @ﾒｲﾝﾙｰﾌﾟ
while true do

   -- Wait for frame update. @ﾌﾚｰﾑｺｳｼﾝｦ ﾏﾂ
   x8.wait()

   -- Draw a circle at random. @ｴﾝｦ ﾗﾝﾀﾞﾑﾆ ﾋﾞｮｳｶﾞ
   x = math.random(128)
   y = math.random(128)
   r = math.random(20)
   c = math.random(15)
   x8.circ(x, y, r, c)

end
```
- `math.random(n)`は1〜nまでのランダムな数を返します。

---

## 画面をクリアする

![](imgs/tutorial/x8_tuto_clear_screen.gif "Clear screen")

フレーム毎に、画面をクリアしてから図形を描いてみます。

```
-- Clear the screen. @ｶﾞﾒﾝｦ ｸﾘｱｽﾙ

-- Main loop. @ﾒｲﾝﾙｰﾌﾟ
while true do

   -- Wait for 20 frames update. @20ﾌﾚｰﾑ ﾏﾂ
   x8.wait(20)

   -- Clear the screen. @ｶﾞﾒﾝｦ ｸﾘｱｽﾙ
   x8.cls()

   -- Draw a circle at random. @ﾗﾝﾀﾞﾑﾆ ｴﾝｦ ﾋﾞｮｳｶﾞ
   x = math.random(128)
   y = math.random(128)
   r = math.random(20)
   c = math.random(15)
   x8.circ(x, y, r, c)

end
```
- `cls()`は画面に描かれたものを全て消します。
- `wait(n)`は、ここでnフレーム待ちます。省略時のnは1です。

---

## 図形を動かす

![](imgs/tutorial/x8_tuto_move_circle.gif "Move circle")

図形を描く位置をフレーム毎に変えることで、図形を動かしてみます。
```
-- Move the circle. @ｴﾝｦ ｳｺﾞｶｽ

x = 20 -- x
v = 2  -- velocity @ｿｸﾄﾞ

-- Main loop. @ﾒｲﾝﾙｰﾌﾟ
while true do

   -- Wait for frame update. @ﾌﾚｰﾑｺｳｼﾝｦ ﾏﾂ
   x8.wait()

   -- Clear the screen. @ｶﾞﾒﾝｦ ｸﾘｱｽﾙ
   x8.cls()

   -- Draw the circle. @ｴﾝｦ ﾋﾞｮｳｶﾞ
   x8.circ(x, 50, 10, 3)

   -- Update the position of the circle. @ｴﾝﾉ ｻﾞﾋｮｳｦ ｺｳｼﾝ
   x = x + v

   -- Invert velocity at screen edge. @ｶﾞﾒﾝﾉﾊｼﾃﾞ ｿｸﾄﾞｦ ﾊﾝﾃﾝ
   if (x < 20) or (x > 100) then v = -v end

end
```
- よくあるアニメーションは普通、フレーム毎に位置や画像を少しずつ変更することで実現します。

---

## ボタンの入力を取得する

![](imgs/tutorial/x8_tuto_button_input.gif "Input buttons")

ボタンの入力を取得して、ボタンの状態を表示してみます。
```
-- Get button input. @ﾎﾞﾀﾝﾉ ﾆｭｳﾘｮｸｦ ｼｭﾄｸ

-- Main loop. @ﾒｲﾝﾙｰﾌﾟ
while true do

   -- Wait for frame update. @ﾌﾚｰﾑｺｳｼﾝｦ ﾏﾂ
   x8.wait()

   -- Clear the screen. @ｶﾞﾒﾝｦ ｸﾘｱｽﾙ
   x8.cls()

   -- Show button trigger status. @ﾎﾞﾀﾝﾉ ﾄﾘｶﾞｰﾉ ｼﾞｮｳﾀｲｦ ﾋｮｳｼﾞ
   x8.color(7)
   if x8.btntrg(0) then x8.rect(10-2, 50-2, 20+2, 60+2) end -- ←
   if x8.btntrg(1) then x8.rect(40-2, 50-2, 50+2, 60+2) end -- →
   if x8.btntrg(2) then x8.rect(25-2, 35-2, 35+2, 45+2) end -- ↑
   if x8.btntrg(3) then x8.rect(25-2, 65-2, 35+2, 75+2) end -- ↓
   if x8.btntrg(4) then x8.circ(95, 70, 6+2) end -- Ⓐ
   if x8.btntrg(5) then x8.circ(110,55, 6+2) end -- Ⓑ
   if x8.btntrg(6) then x8.circ(80, 55, 6+2) end -- Ⓒ
   if x8.btntrg(7) then x8.circ(95, 40, 6+2) end -- Ⓓ

   -- Draw buttons. @ﾎﾞﾀﾝｦ ﾋﾞｮｳｶﾞ
   x8.color(1)
   x8.rect(10, 50, 20, 60) -- ←
   x8.rect(40, 50, 50, 60) -- →
   x8.rect(25, 35, 35, 45) -- ↑
   x8.rect(25, 65, 35, 75) -- ↓
   x8.circ(95, 70, 6) -- Ⓐ
   x8.circ(110,55, 6) -- Ⓑ
   x8.circ(80, 55, 6) -- Ⓒ
   x8.circ(95, 40, 6) -- Ⓓ

   -- Show button press status. @ﾎﾞﾀﾝﾉ ｵｳｶﾉ ｼﾞｮｳﾀｲｦ ﾋｮｳｼﾞ
   x8.color(7)
   if x8.btnprs(0) then x8.rect(10+2, 50+2, 20-2, 60-2) end -- ←
   if x8.btnprs(1) then x8.rect(40+2, 50+2, 50-2, 60-2) end -- →
   if x8.btnprs(2) then x8.rect(25+2, 35+2, 35-2, 45-2) end -- ↑
   if x8.btnprs(3) then x8.rect(25+2, 65+2, 35-2, 75-2) end -- ↓
   if x8.btnprs(4) then x8.circ(95, 70, 6-2) end -- Ⓐ
   if x8.btnprs(5) then x8.circ(110,55, 6-2) end -- Ⓑ
   if x8.btnprs(6) then x8.circ(80, 55, 6-2) end -- Ⓒ
   if x8.btnprs(7) then x8.circ(95, 40, 6-2) end -- Ⓓ
end
```
- `btnprs(n)`は、n番のボタンが現在押されているかどうかを`true`か`false`で返します。
- `btntrg(n)`は、n番のボタンがこのフレームで、押されていない → 押された、と変化したかどうかを`true`か`false`で返します。

---

## 図形をボタン入力で制御する

![](imgs/tutorial/x8_tuto_control_circle.gif "Control circle")

図形をボタン入力によって動かしたり、色や大きさを変えたりしてみます。
```
-- Move circle with button input. @ﾎﾞﾀﾝﾆｭｳﾘｮｸﾃﾞ ｴﾝｦ ｳｺﾞｶｽ

x = 50 -- x
y = 50 -- y
r = 20 -- radius @ﾊﾝｹｲ
c = 7  -- color @ｶﾗｰ
v = 2  -- velocity @ｿｸﾄﾞ

-- Main loop. @ﾒｲﾝﾙｰﾌﾟ
while true do

   -- Wait for frame update. @ﾌﾚｰﾑｺｳｼﾝｦ ﾏﾂ
   x8.wait()

   -- Clear the screen. @ｶﾞﾒﾝｦ ｸﾘｱｽﾙ
   x8.cls()

   -- Move with direction buttons. @ﾎｳｺｳﾎﾞﾀﾝﾃﾞ ｲﾄﾞｳ
   if x8.btnprs(0) then x = x - v end -- ←
   if x8.btnprs(1) then x = x + v end -- →
   if x8.btnprs(2) then y = y - v end -- ↑
   if x8.btnprs(3) then y = y + v end -- ↓

   -- Change color and size with A and B button. @Aﾎﾞﾀﾝﾄ Bﾎﾞﾀﾝﾃﾞ ｲﾛﾄ ｻｲｽﾞｦ ｶｴﾙ
   if x8.btntrg(4) then c = math.random(15) end -- Ⓐ
   if x8.btntrg(5) then r = math.random(30) end -- Ⓑ

   -- Draw the circle @ｴﾝｦ ﾋﾞｮｳｶﾞ
   x8.circ(x, y, r, c)
end
```
- ゲームでキャラクターを動かしたりする基本的な方法になります。

---

## スプライトを表示する

<img src="imgs/tutorial/x8_tuto_draw_sprite.jpg" width="448">

画面にスプライトを表示してみます。

スプライトとはGfxのチップ（8x8ドット単位の画像）を画面に表示したものです。
Gfxエディタでスプライトとして表示したい絵を描いたら、その絵の左上をタッチしてチップ番号を覚えておきます。

<img src="imgs/tutorial/x8_tuto_gfx_spr1.png" width="448">
<img src="imgs/tutorial/x8_tuto_gfx_spr2.png" width="448">

準備が出来たらチップ番号を指定してスプライトを表示してみます。
```
-- x8.spr(n,x,y[,w[,h,[,flpx[,flpy]]]])

-- Draw a 1x1 size chip. @1x1ｻｲｽﾞﾉ ﾁｯﾌﾟｦ ﾋﾞｮｳｶﾞｽﾙ
x8.spr(1, 10, 20)

-- Draw a 2x2 size chip. @2x2ｻｲｽﾞﾉ ﾁｯﾌﾟｦ ﾋﾞｮｳｶﾞｽﾙ
x8.spr(2, 10, 40, 2, 2)

-- Draw a 2x2 size chip with a 2x1 size. @2x2ｻｲｽﾞﾉ ﾁｯﾌﾟｦ 2x1ｻｲｽﾞﾃﾞ ﾋﾞｮｳｶﾞｽﾙ
x8.spr(2, 30, 40, 2, 1)

-- Flip left and right to draw. @ｻﾕｳﾊﾝﾃﾝｼﾃ ﾋﾞｮｳｶﾞｽﾙ
x8.spr(1, 10, 70, 1, 1, true)

-- Flip up and down to draw. @ｼﾞｮｳｹﾞﾊﾝﾃﾝｼﾃ ﾋﾞｮｳｶﾞｽﾙ
x8.spr(1, 30, 70, 1, 1, false, true)
```

- `spr(n,x,y)`で`n`番のチップを画面の`x,y`に表示できます。`w,h`で**チップ単位**の表示サイズを、`flpx,flpy`で左右上下の反転を指定できます。
- スプライトはゲームのキャラクターや弾などを表現する一番簡単な方法です。

---

## Gfxの画像を表示する

<img src="imgs/tutorial/x8_tuto_draw_gfx_images.jpg" width="448">

画面にGfxの画像を表示してみます。

Gfxエディタで表示したい絵を描いたら、その画像領域をドラッグで選択してGfx内での位置とサイズを覚えておきます。

<img src="imgs/tutorial/x8_tuto_gfx_spr2_16x16.png" width="448">

準備が出来たらGfx内での位置とサイズを指定して画像をを表示してみます。
```
-- x8.gfx(gx,gy,gw,gh,x,y[,w[,h[,flpx[,flpy]]]])

-- Scaling and drawing Gfx images without changing the aspect ratio.
-- @Gfxｶﾞｿﾞｳｦ ﾀﾃﾖｺﾋｦ ｶｴｽﾞﾆ ｶｸｼｭｸｼﾃ ﾋﾞｮｳｶﾞｽﾙ
x8.gfx(16, 0, 16, 16,  8, 8,  8,  8) -- 8x8
x8.gfx(16, 0, 16, 16, 24, 8, 16, 16) -- 16x16
x8.gfx(16, 0, 16, 16, 48, 8, 24, 24) -- 24x24
x8.gfx(16, 0, 16, 16, 80, 8, 32, 32) -- 32x32

-- Flip and draw Gfx images in different aspect ratios.
-- @Gfxｶﾞｿﾞｳｦ ﾀﾃﾖｺﾋｦ ｶｴﾃ ﾊﾝﾃﾝｼﾃ ﾋﾞｮｳｶﾞｽﾙ
x8.gfx(16, 0, 16, 16,   4, 64, 32, 16) -- 32x16
x8.gfx(16, 0, 16, 16,  44, 64, 32, 16, true) -- 32x16,left-right reversal @ｻﾕｳﾊﾝﾃﾝ
x8.gfx(16, 0, 16, 16,  84, 64, 16, 32) -- 16x32
x8.gfx(16, 0, 16, 16, 108, 64, 16, 32, false, true) -- 16x32,upside down @ｼﾞｮｳｹﾞﾊﾝﾃﾝ
```

- `gfx(gx,gy,gw,gh,x,y)`でGfx内の位置`gx,gy`、サイズ`gw,gh`の絵を、画面の位置`x,y`に表示できます。`w,h`で**ピクセル単位**の表示サイズを、`flpx,flpy`で左右上下の反転を指定できます。
- Gfx内でのサイズの整数倍または整数で割ったサイズ以外で表示すると、絵が少し崩れてしまいますがこれは仕様です。
- `gfx()`はスプライトよりもちょっと凝った表現が出来ます。

---

