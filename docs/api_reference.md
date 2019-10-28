# x8ライブラリリファレンス

## はじめに

### 色番号

x8では色を0〜15の色番号で表します。また、16色の色のセットをパレットと呼びます。

### 描画ステート

x8はビデオ関連の命令に影響を与える、以下の描画ステートを持っています。

- 描画座標オフセット
    - 全ての描画命令は、位置をこのオフセット分ずらして描画します。
- 描画クリップ矩形
    - 全ての描画命令は、この矩形の内側にだけ描画結果を反映します。
- 描画パレット
    - 全ての描画命令は、描画する色をこのパレットで置き換えます。
- 抜き色情報
    - 全ての描画命令は、この情報で抜きになっている色を描画しません。
- デフォルト描画色
    - 色を指定可能な描画命令で、色を指定しなかった場合、この色で描画します。
- フォントスケール
    - フォント描画命令は、このスケールを反映して描画します。
- フォント間隔
    - フォント描画命令は、各々の文字をこの間隔を開けて描画します。
- 画面パレット
    - 描画結果の画面イメージは、最終的にこのパレットで色を置き換えて、表示されます。

### 画面イメージ

全ての描画命令は、画面イメージと呼ばれる領域に描画を行います。描画結果の画面イメージは、画面パレットで色を置き換えらた後、ディスプレイに表示されます。

### チップとチップ番号

x8では、Gfx領域を8x8で分割したものをチップと呼びます。チップ番号とはGfx領域の左上から順に（アドレス順に）、チップに振られた番号（0〜255）のことです。

### チップ属性

（工事中）

### スプライト

x8では、チップを直接描画したものを慣例的にスプライトと呼んでいます。

### マップ

x8では、Map領域での位置とサイズを指定して、そこに並べられたチップ群を描画したものを、慣例的にマップと呼んでいます。

### フォント

x8には、いくつかの組み込みフォントとそのAPIが用意されています。カタカナや特殊文字を含む文字列は、APIなどで扱う前にまず、`enc()`で8bitコードに変換する必要があります。

```
x8.fnt(x8.enc("ｶﾀｶﾅ ﾄｶ ←→↑↓ ﾄｶ ｶﾞ ﾊｲｯﾃｲﾙ ﾓｼﾞﾚﾂ ﾊ enc()ﾃﾞ 8bit ｺｰﾄﾞ ﾆ ﾍﾝｶﾝ ｽﾍﾞｼ"))
str_len = string.len(x8.enc("ｶﾀｶﾅ ﾄｶ ⒶⒷⒸⒹ ﾄｶ ｱｯﾃﾓ stringﾗｲﾌﾞﾗﾘ ﾊ ｿﾉﾏﾏ ﾂｶｴﾏｽ"))
```

### スレッド

（工事中）

## ビデオ関連

`x8.cls([col])`

- 色`col`で画面イメージをクリアします。
- 描画パレットの影響を受けますが、描画オフセット、描画クリップ、抜き色情報の影響は受けません。
- 引き数のデフォルト値 : `col=0`

`x8.clip([x[,y[,w[,h]]]])`

- 描画クリップ矩形に、位置`x,y`とサイズ`w,h`を設定します。引き数なしで呼ぶとリセットします。
- 全ての描画命令は、この矩形の内側にだけ描画結果を反映します。
- 引き数のデフォルト値 : `x=0`,`y=0`,`w=128`,`h=128`

`x8.camera([x[,y]])`

- 描画座標オフセットに`x,y`を設定します。引き数なしで呼ぶとリセットします。
- 全ての描画命令は、位置をこのオフセット分ずらして描画します。
- 引き数のデフォルト値 : `x=0`,`y=0`

`x8.color([col])`

- デフォルト描画色に`col`を設定します。
- 色を指定可能な描画命令で、色を指定しなかった場合、この色で描画します。
- 引き数のデフォルト値 : `col=7`

`x8.drwpal([col0[,col1]])`

- 描画パレットに、色`col0`を`col1`に置き換わるよう設定します。引き数なしで呼ぶとリセットします。
- 全ての描画命令は、描画する色をこのパレットで置き換えます。
- 引き数のデフォルト値 : `col0=0`,`col1=col1`

`x8.scrpal([col0[,col1]])`

- 画面パレットに、色`col0`を`col1`に置き換わるよう設定します。引き数なしで呼ぶとリセットします。
- 描画結果の画面イメージは、最終的にこのパレットで色を置き換えて、表示されます。
- 引き数のデフォルト値 : `col0=0`,`col1=col1`

`x8.colorkey([col[,trs]])`

- 抜き色情報に、色`col`を抜きにするかどうかを`trs`(boolean)に設定します。引き数なしで呼ぶとリセットします。
- 全ての描画命令は、この情報で抜きになっている色を描画しません。
- 引き数のデフォルト値 : `col=0`,`trs=true`

`x8.spr(n,x,y[,w[,h,[,flpx[,flpy]]]])`

- `n`番のチップをを位置`x,y`に描画します。サイズ`w,h`はチップ単位です。`flipx`で左右の、 `flipy`で上下の反転を指定できます。
- 描画ステートの影響を受けます。
- 引き数のデフォルト値 : `w=1`,`h=1`,`flipx=false`,`flipy=false`

`x8.gfx(gx,gy,gw,gh,x,y[,w[,h[,flpx[,flpy]]]])`

- Gfx内の位置`gx,gy`、サイズ`gw,gh`の矩形領域を、画面の位置`x,y`に描画します。`w,h`で描画サイズを指定できます。全てピクセル単位です。`flipx`で左右の、 `flipy`で上下の反転を指定できます。
- 描画ステートの影響を受けます。
- 引き数のデフォルト値 : `w=gw`,`h=gh`,`flipx=false`,`flipy=false`

`x8.map(mapx,mapy,x,y[,mapw[,maph]])`

- Map内の位置`mapx,mapy`のチップを、画面の位置`x,y`に描画します。Map内のサイズを`mapw,maph`によりチップ単位で指定できます。
- 描画ステートの影響を受けます。
- 引き数のデフォルト値 : `mapw=1`,`maph=1`

`x8.mapget(mapx,mapy)`

- Map内の位置`mapx,mapy`のチップ番号を取得します。

`x8.mapset(mapx,mapy,val)`

- Map内の位置`mapx,mapy`のチップ番号を`val`に設定します。

`x8.atrget(n[,bit])`

- `n`番のチップ属性を取得します。`bit`があればそのビット値をbooleanで、なければチップ属性値をそのまま返します。

`x8.atrset(n[,bit][,val])`

- `n`番のチップ属性を`val`に設定します。`bit`があれば`val`をbooleanとしてそのビット値を、なければ`val`をチップ属性値としてそのまま設定します。
- 引き数のデフォルト値 : `bit`がある場合`val=false`

`x8.scrget(x,y)`

- 画面イメージの位置`x,y`のピクセルの色を取得します。

`x8.scrset(x,y,col)`

- 画面イメージの位置`x,y`のピクセルの色を設定します。
- 描画命令ではないため描画ステートの影響を受けません。

`x8.gfxget(sprx,spry)`

- Gfx内の位置`x,y`のピクセルの色を取得します。

`x8.gfxset(sprx,spry,col)`

- Gfx内の位置`x,y`のピクセルの色を設定します。
- 描画命令ではないため描画ステートの影響を受けません。

`x8.pixel(x,y[,col])`

- 画面の位置`x,y`にピクセルを描画します。
- 描画ステートの影響を受けます。
- 引き数のデフォルト値 : `col=デフォルト描画色`

`x8.line(x0,y0,x1,y1[,col])`

- 画面に始点`x0,y0`終点`x1,y1`の直線を描画します。
- 描画ステートの影響を受けます。
- 引き数のデフォルト値 : `col=デフォルト描画色`

`x8.rectbdr(x0,y0,x1,y1[,col])`

- 画面に左上`x0,y0`右下`x1,y1`の矩形を描画します。
- 描画ステートの影響を受けます。
- 引き数のデフォルト値 : `col=デフォルト描画色`

`x8.rect(x0,y0,x1,y1[,col])`

- 画面に左上`x0,y0`右下`x1,y1`の塗りつぶされた矩形を描画します。
- 描画ステートの影響を受けます。
- 引き数のデフォルト値 : `col=デフォルト描画色`

`x8.circbdr(x,y,r[,col])`

- 画面に中心点`x,y`半径`r`の円を描画します。
- 描画ステートの影響を受けます。
- 引き数のデフォルト値 : `col=デフォルト描画色`

`x8.circ(x,y,r[,col])`

- 画面に中心点`x,y`半径`r`の塗りつぶされた円を描画します。
- 描画ステートの影響を受けます。
- 引き数のデフォルト値 : `col=デフォルト描画色`

---

## オーディオ関連

`x8.sfx(n[,spd[,pitch[,start[,len]]]])`
- Play sfx

`x8.phr(n[,sp[,pitch[,start[,end]]]])`
- Play phrase

`x8.music(n[,spd[,pitch[,start[,end]]]])`
- Play music

`x8.hdlstop(hdl)`
- Stop audio handle

`x8.sfxstop()`
- Stop all sfxs

`x8.phrstop()`
- Stop all phrases

`x8.musicstop()`
- Stop all music

`x8.sfxch([chmask])`
- Set channel for sfxs

`x8.phrch([chmask])`
- Set channel for phrases

`x8.musicch([chmask])`
- Set channel for music

---

## フォント関連

`x8.fnt(str,x,y[,col])`
- Draw font string

`x8.fntscale([sclx[,scly]])`
- Set font scale

`x8.fntspace([spcx[,spcy]])`
- Set font spacing

`x8.fntmeas(str) -> size_x,size_y`
- Get string drawing size

`x8.enc(str)`
- Encode to 8-bit characters

---

## 入力関連

`x8.btnprs([bit])`

- ボタンの

`x8.btntrg([bit])`
- Get button trigger

---

## スレッド関連

`x8.thrstart(f[,arg1,...])`
- Start thread

`x8.thrcancel(hdl)`
- Destroy thread

`x8.thrself()`
- Get own thread

`x8.thrprio(hdl[,prio])`
- Set thread priority

`x8.thralive(hdl)`
- Check thread existence

---

## その他

`x8.log(str)`
- Log output

`x8.wait([frms])`
- Wait for frames

`x8.fps([fps])`
- Get and set fps

`x8.peek(addr)`
- Read memory

`x8.poke(addr,val)`
- Write memory

`x8.memcpy(dstaddr,srcaddr,len)`
- Copy memory

`x8.test([..])`
- for develop(no effect)
