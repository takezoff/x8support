# Lua 5.3 標準ライブラリ

## はじめに

このドキュメントは、Lua標準ライブラリの各項目の概要と、その詳細な説明へのリンク（外部リンク）をまとめたものです。
項目名をクリックするとその詳細な説明に飛ぶことができます。
簡単にするため、このドキュメントには**x8**で利用できる機能だけを記載してあります。

標準ライブラリのうち、**x8で利用出来るライブラリは以下の通りです。記載のないライブラリは利用できません。**

|ライブラリ|テーブル|詳細|
|:---|:---|:---|
|基本ライブラリ||**collectgarbage**、**dofile**、**loadfile**、**load**、**print**を除き利用可能|
|コルーチンライブラリ|**coroutine**|全て利用可能|
|文字列操作|**string**|**dump**、**pack**、**packsize**、**unpack**を除き利用可能|
|テーブル操作|**table**|全て利用可能|
|数学関数|**math**|全て利用可能|

## 基本機能

[基本機能ライブラリ](http://milkpot.sakura.ne.jp/lua/lua53_manual_ja.html#6.1)は、Luaの中核的な機能を**グローバル**に格納して提供します。

|名前|概要|
|:---|:---|
|[_G](http://milkpot.sakura.ne.jp/lua/lua53_manual_ja.html#pdf-_G)|グローバル環境を保持するグローバル変数|
|[_VERSION](http://milkpot.sakura.ne.jp/lua/lua53_manual_ja.html#pdf-_VERSION)|インタプリタのバージョン文字列|
|[assert](http://milkpot.sakura.ne.jp/lua/lua53_manual_ja.html#pdf-assert)|条件が偽なら意図的にエラー終了する|
|[error](http://milkpot.sakura.ne.jp/lua/lua53_manual_ja.html#pdf-error)|意図的にエラー終了する|
|[getmetatable](http://milkpot.sakura.ne.jp/lua/lua53_manual_ja.html#pdf-getmetatable)|オブジェクトのメタテーブルを取得する|
|[ipairs](http://milkpot.sakura.ne.jp/lua/lua53_manual_ja.html#pdf-ipairs)|汎用for文で利用できるようなイテレータを作る|
|[next](http://milkpot.sakura.ne.jp/lua/lua53_manual_ja.html#pdf-next)|テーブルのすべてのフィールドを巡回する|
|[pairs](http://milkpot.sakura.ne.jp/lua/lua53_manual_ja.html#pdf-pairs)|汎用for文で利用できるようなイテレータを作る|
|[pcall](http://milkpot.sakura.ne.jp/lua/lua53_manual_ja.html#pdf-pcall)|エラーが起きても終了しない関数呼び出しを行う|
|[rawequal](http://milkpot.sakura.ne.jp/lua/lua53_manual_ja.html#pdf-rawequal)|メタメソッドを呼ばずに等値比較を行う|
|[rawget](http://milkpot.sakura.ne.jp/lua/lua53_manual_ja.html#pdf-rawget)|メタメソッドを呼ばずにテーブルのインデックスに対応する値を取得する|
|[rawlen](http://milkpot.sakura.ne.jp/lua/lua53_manual_ja.html#pdf-rawlen)|メタメソッドを呼ばずにオブジェクトの長さを取得する|
|[rawset](http://milkpot.sakura.ne.jp/lua/lua53_manual_ja.html#pdf-rawset)|メタメソッドを呼ばずにテーブルのインデックスに対応する値を設定する|
|[select](http://milkpot.sakura.ne.jp/lua/lua53_manual_ja.html#pdf-select)|引数の情報を取得する|
|[setmetatable](http://milkpot.sakura.ne.jp/lua/lua53_manual_ja.html#pdf-setmetatable)|テーブルのメタテーブルを設定する|
|[tonumber](http://milkpot.sakura.ne.jp/lua/lua53_manual_ja.html#pdf-tonumber)|数値や文字列を数値や整数に変換する|
|[tostring](http://milkpot.sakura.ne.jp/lua/lua53_manual_ja.html#pdf-tostring)|任意の型の値を適当な文字列に変換する|
|[type](http://milkpot.sakura.ne.jp/lua/lua53_manual_ja.html#pdf-type)|値の型を型名の文字列に変換する|
|[xpcall](http://milkpot.sakura.ne.jp/lua/lua53_manual_ja.html#pdf-xpcall)|メッセージハンドラを指定できるpcall|

## コルーチン操作

[コルーチン操作ライブラリ](http://milkpot.sakura.ne.jp/lua/lua53_manual_ja.html#6.2)は、コルーチンを操作する機能をテーブル**coroutine**に格納して提供します。

|名前|概要|
|:---|:---|
|[coroutine.create](http://milkpot.sakura.ne.jp/lua/lua53_manual_ja.html#pdf-coroutine.create)|新しいコルーチンを作成する|
|[coroutine.isyieldable](http://milkpot.sakura.ne.jp/lua/lua53_manual_ja.html#pdf-coroutine.isyieldable)|実行中のコルーチンが中断可能かどうか調べる|
|[coroutine.resume](http://milkpot.sakura.ne.jp/lua/lua53_manual_ja.html#pdf-coroutine.resume)|コルーチンの実行を開始または継続する|
|[coroutine.running](http://milkpot.sakura.ne.jp/lua/lua53_manual_ja.html#pdf-coroutine.running)|実行中のコルーチン情報を取得する|
|[coroutine.status](http://milkpot.sakura.ne.jp/lua/lua53_manual_ja.html#pdf-coroutine.status)|コルーチンの状態を取得する|
|[coroutine.wrap](http://milkpot.sakura.ne.jp/lua/lua53_manual_ja.html#pdf-coroutine.wrap)|新しいコルーチンを作成して関数に包む|
|[coroutine.yield](http://milkpot.sakura.ne.jp/lua/lua53_manual_ja.html#pdf-coroutine.yield)|呼び出し元のコルーチンの実行を中断する|

## 文字列操作

[文字列操作ライブラリ](http://milkpot.sakura.ne.jp/lua/lua53_manual_ja.html#6.4)は、部分文字列の検索、部分文字列の抽出、パターンマッチングなど、文字列操作のための汎用的な機能をテーブル**string**に格納して提供します。

|名前|概要|
|:---|:---|
|[string.byte](http://milkpot.sakura.ne.jp/lua/lua53_manual_ja.html#pdf-string.byte)|文字列の各文字を文字コードに変換する|
|[string.char](http://milkpot.sakura.ne.jp/lua/lua53_manual_ja.html#pdf-string.char)|複数の整数を文字コードとして１つの文字列に変換する|
|[string.find](http://milkpot.sakura.ne.jp/lua/lua53_manual_ja.html#pdf-string.find)|文字列のパターンマッチ検索を行う|
|[string.format](http://milkpot.sakura.ne.jp/lua/lua53_manual_ja.html#pdf-string.format)|フォーマットを指定して文字列の書式化を行う|
|[string.gmatch](http://milkpot.sakura.ne.jp/lua/lua53_manual_ja.html#pdf-string.gmatch)|文字列のパターンマッチ結果を返すイテレータを取得する|
|[string.gsub](http://milkpot.sakura.ne.jp/lua/lua53_manual_ja.html#pdf-string.gsub)|文字列のパターンマッチ結果について置換などを行う|
|[string.len](http://milkpot.sakura.ne.jp/lua/lua53_manual_ja.html#pdf-string.len)|文字列の長さを取得する|
|[string.lower](http://milkpot.sakura.ne.jp/lua/lua53_manual_ja.html#pdf-string.lower)|文字列中の大文字を小文字に変換する|
|[string.match](http://milkpot.sakura.ne.jp/lua/lua53_manual_ja.html#pdf-string.match)|文字列のパターンマッチの最初の結果を取得する|
|[string.rep](http://milkpot.sakura.ne.jp/lua/lua53_manual_ja.html#pdf-string.rep)|回数とセパレータを指定して文字列を繰り返し連結する|
|[string.reverse](http://milkpot.sakura.ne.jp/lua/lua53_manual_ja.html#pdf-string.reverse)|文字列を反転する|
|[string.sub](http://milkpot.sakura.ne.jp/lua/lua53_manual_ja.html#pdf-string.sub)|文字列の部分文字列を取得する|
|[string.upper](http://milkpot.sakura.ne.jp/lua/lua53_manual_ja.html#pdf-string.upper)|文字列中の小文字を大文字に変換する|

## テーブル操作

[テーブル操作ライブラリ](http://milkpot.sakura.ne.jp/lua/lua53_manual_ja.html#6.6)は、テーブル操作のための汎用的な機能をテーブル**table**に格納して提供します。

|名前|概要|
|:---|:---|
|[table.concat](http://milkpot.sakura.ne.jp/lua/lua53_manual_ja.html#pdf-table.concat)|セパレータを指定してテーブルの全要素を文字列として連結する|
|[table.insert](http://milkpot.sakura.ne.jp/lua/lua53_manual_ja.html#pdf-table.insert)|リストに要素を挿入する|
|[table.move](http://milkpot.sakura.ne.jp/lua/lua53_manual_ja.html#pdf-table.move)|テーブルの要素を別のテーブルまたは同じテーブルの別の位置に移動する|
|[table.pack](http://milkpot.sakura.ne.jp/lua/lua53_manual_ja.html#pdf-table.pack)|複数の値をキーが整数のテーブルにまとめる|
|[table.remove](http://milkpot.sakura.ne.jp/lua/lua53_manual_ja.html#pdf-table.remove)|リストから要素を削除する|
|[table.sort](http://milkpot.sakura.ne.jp/lua/lua53_manual_ja.html#pdf-table.sort)|テーブルの要素をソートする|
|[table.unpack](http://milkpot.sakura.ne.jp/lua/lua53_manual_ja.html#pdf-table.unpack)|テーブルを各要素にバラして取得する|

## 数学関数

[数学関数ライブラリ](http://milkpot.sakura.ne.jp/lua/lua53_manual_ja.html#6.7)は、基本的な数学関数をテーブル**math**に格納して提供します。

|名前|概要|
|:---|:---|
|[math.abs](http://milkpot.sakura.ne.jp/lua/lua53_manual_ja.html#pdf-math.abs)|絶対値を取得する|
|[math.acos](http://milkpot.sakura.ne.jp/lua/lua53_manual_ja.html#pdf-math.acos)|逆余弦を取得する|
|[math.asin](http://milkpot.sakura.ne.jp/lua/lua53_manual_ja.html#pdf-math.asin)|逆正弦を取得する|
|[math.atan](http://milkpot.sakura.ne.jp/lua/lua53_manual_ja.html#pdf-math.atan)|逆正接を取得する|
|[math.ceil](http://milkpot.sakura.ne.jp/lua/lua53_manual_ja.html#pdf-math.ceil)|整数に切り上げる|
|[math.cos](http://milkpot.sakura.ne.jp/lua/lua53_manual_ja.html#pdf-math.cos)|余弦を取得する|
|[math.deg](http://milkpot.sakura.ne.jp/lua/lua53_manual_ja.html#pdf-math.deg)|角度をラジアンから度に変換する|
|[math.exp](http://milkpot.sakura.ne.jp/lua/lua53_manual_ja.html#pdf-math.exp)|自然対数の底eのべき乗の値を取得する|
|[math.floor](http://milkpot.sakura.ne.jp/lua/lua53_manual_ja.html#pdf-math.floor)|整数に切り下げる|
|[math.fmod](http://milkpot.sakura.ne.jp/lua/lua53_manual_ja.html#pdf-math.fmod)|商をゼロに向けて丸めた割り算の剰余を取得する|
|[math.huge](http://milkpot.sakura.ne.jp/lua/lua53_manual_ja.html#pdf-math.huge)|いかなる数値よりも大きな数値|
|[math.log](http://milkpot.sakura.ne.jp/lua/lua53_manual_ja.html#pdf-math.log)|対数を取得する|
|[math.max](http://milkpot.sakura.ne.jp/lua/lua53_manual_ja.html#pdf-math.max)|複数の値のうち最大の値を取得する|
|[math.maxinteger](http://milkpot.sakura.ne.jp/lua/lua53_manual_ja.html#pdf-math.maxinteger)|整数の最大値|
|[math.min](http://milkpot.sakura.ne.jp/lua/lua53_manual_ja.html#pdf-math.min)|複数の値のうち最小の値を取得する|
|[math.mininteger](http://milkpot.sakura.ne.jp/lua/lua53_manual_ja.html#pdf-math.mininteger)|整数の最小値|
|[math.modf](http://milkpot.sakura.ne.jp/lua/lua53_manual_ja.html#pdf-math.modf)|整数部と小数部を取得する|
|[math.pi](http://milkpot.sakura.ne.jp/lua/lua53_manual_ja.html#pdf-math.pi)|円周率π|
|[math.rad](http://milkpot.sakura.ne.jp/lua/lua53_manual_ja.html#pdf-math.rad)|角度を度からラジアンに変換する|
|[math.random](http://milkpot.sakura.ne.jp/lua/lua53_manual_ja.html#pdf-math.random)|ランダムな数値や整数を取得する|
|[math.randomseed](http://milkpot.sakura.ne.jp/lua/lua53_manual_ja.html#pdf-math.randomseed)|擬似乱数生成器の種を設定する|
|[math.sin](http://milkpot.sakura.ne.jp/lua/lua53_manual_ja.html#pdf-math.sin)|正弦を取得する|
|[math.sqrt](http://milkpot.sakura.ne.jp/lua/lua53_manual_ja.html#pdf-math.sqrt)|平方根を取得する|
|[math.tan](http://milkpot.sakura.ne.jp/lua/lua53_manual_ja.html#pdf-math.tan)|正接を取得する|
|[math.tointeger](http://milkpot.sakura.ne.jp/lua/lua53_manual_ja.html#pdf-math.tointeger)|値を整数に変換する|
|[math.type](http://milkpot.sakura.ne.jp/lua/lua53_manual_ja.html#pdf-math.type)|値が整数か浮動小数点数か数値以外かを調べる|
|[math.ult](http://milkpot.sakura.ne.jp/lua/lua53_manual_ja.html#pdf-math.ult)|2つの整数を符号なし整数として比較する|
