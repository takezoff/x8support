# クイックスタート

## 1.サンプルゲームを遊んでみよう

### Home画面

アプリを起動すると下のような[Home画面](manual.md#Home画面)が表示されます。
ここは同梱されているサンプルを開いたりユーザーが作ったファイルを管理したりできる画面です。

- <img src="imgs/icons/ui_icon_76.png" width="18"> **サンプルフォルダ**タブを選択します。
- シューティングゲームのサンプル`CockatielSoul`を選びます。
- <img src="imgs/icons/ui_icon_60.png" width="18"> **あそぶ**ボタンで**x8マシン**が起動してゲームが始まります。

![](imgs/quick_start/x8_qs_home_play.png "Home Screen")

### Runモード

- ゲームを遊ぶ[Runモード](manual.md#Runモード)です。画面の左右にあるゲームパッドボタンを操作してゲームを遊んでみてね。
- <img src="imgs/icons/ui_icon_86.png" width="18"> **メニュー**ボタンで開くメニューの**終了**を選べばHome画面に戻れます。

![](imgs/quick_start/x8_qs_run_play.png "Run Mode")

![](imgs/quick_start/x8_qs_run_menu.png "Run Mode Menu")

#### **おめでとうございます！サンプルゲームで遊べるようになりました！**

---

## 2.サンプルゲームの中を見てみよう

サンプルゲームのプロジェクトの中身を覗いてみましょう。

### プロジェクトを開く

- <img src="imgs/icons/ui_icon_76.png" width="18"> **サンプルフォルダ**タブを選択します。
- シューティングゲームのサンプル`CockatielSoul`を選びます。
- <img src="imgs/icons/ui_icon_74.png" width="18"> **開く**ボタンでプロジェクトを開いてスタジオに遷移します。

![](imgs/quick_start/x8_qs_home_open.png "Home Screen")

### Codeエディタ

- プロジェクトを開くと最初に表示されるのが <img src="imgs/icons/ui_icon_04.png" width="18"> **[Codeエディタ](manual.md#Codeエディタ)**です。このサンプルゲームのプログラムが書いてあります。画面右端のスクロールバーでスクロールして見てみましょう。

![](imgs/quick_start/x8_qs_code_editor.png "Code Editor")

### 文字入力とUndo

- <img src="imgs/icons/ui_icon_62.png" width="18"> **[画面キーボード](manual.md#画面キーボード)**ボタンでキーボードを出してなにか入力してみましょう。（[外部キーボード](manual.md#外部キーボード)にも対応しています。）
- <img src="imgs/icons/ui_icon_14.png" width="18"> **Undo**（元に戻す）ボタンで今行った変更を元に戻せます。押し続けると可能な限りUndoし続けます。

![](imgs/quick_start/x8_qs_code_osk.png "Screen Keyboard")

### Gfxエディタ

- <img src="imgs/icons/ui_icon_05.png" width="18"> **[Gfxエディタ](manual.md#Gfxエディタ)**を開いてみましょう。このサンプルゲームで使われているグラフィックス素材を見ることが出来ます。
- 右側のビューで見たい範囲をドラッグすると左側のビューに反映されます。ゲームで出てくるキャラクターたちの画像データを見られます。
- 画面が小さくて難しい場合は[タッチカーソル](manual.md#Studio共通のUIと操作)を出してボタンを押しながらドラッグすることで、細かい位置を正確にドラッグ出来ます。

![](imgs/quick_start/x8_qs_gfx_editor.png "Gfx Editor")

### Mapエディタ

- <img src="imgs/icons/ui_icon_06.png" width="18"> **[Mapエディタ](manual.md#Mapエディタ)**を開いてみましょう。このサンプルゲームで使われているマップデータを見ることが出来ます。
- **Map選択ビュー**をドラッグすると**エディットビュー**に反映されます。ゲームでスクロールする地形や敵の配置などのデータを見られます。

![](imgs/quick_start/x8_qs_map_editor.png "Map Editor")

### Sfxエディタ

- <img src="imgs/icons/ui_icon_07.png" width="18"> **[Sfxエディタ](manual.md#Sfxエディタ)**を開いてみましょう。このサンプルゲームで使われているサウンドデータを見られます。
- <img src="imgs/icons/ui_icon_07.png" width="12"> **Sfx選択**で効果音を選ぶとその内容がエディタに表示されます。
- <img src="imgs/icons/ui_icon_11.png" width="18"> **再生**ボタンと <img src="imgs/icons/ui_icon_39.png" width="18"> **停止**ボタンで効果音を再生／停止出来ます。

![](imgs/quick_start/x8_qs_sfx_editor.png "Sfx Editor")

### プロジェクトを閉じる

- ひととおり見終わったら画面左下の <img src="imgs/icons/ui_icon_01.png" width="18"> **ファイルメニュー**から**閉じる**を選択します。プロジェクトを閉じてHome画面に戻ります。

#### **おめでとうございます！ゲームの中がどうなっているのか見られるようになりました！**

---

## 3.サンプルゲームを改造してみよう

サンプルゲームを改造して別名で保存してみましょう。

### プログラムの変更

- シューティングゲームのサンプル`CockatielSoul`を開き**Codeエディタ**に移動します。
- <img src="imgs/icons/ui_icon_62.png" width="18"> **画面キーボード**を出し、カーソルキー（`←` `→` `↑` `↓`）で`10`行目に移動します。
- `TEST_BOSS`の`T`にカーソルを移動し、`BS`キーを何回か押して行頭まで削除します。間違えたら <img src="imgs/icons/ui_icon_14.png" width="18"> **Undo**してやり直しましょう。
- 変更したらもう一度 <img src="imgs/icons/ui_icon_62.png" width="18"> をタップして**画面キーボード**を消します。

![](imgs/quick_start/x8_qs_code_edit.png "Code Edit")

### Debugモード

- <img src="imgs/icons/ui_icon_59.png" width="18"> **[Debugモード](manual.md#Debugモード)**に移動してプログラムを実行してみましょう。ここでは開発中のゲームをテスト出来ます。
- <img src="imgs/icons/ui_icon_59.png" width="18"> **デバッグ実行**ボタンで実行を開始します。 <img src="imgs/icons/ui_icon_12.png" width="18"> **一時停止**ボタンで実行のポーズ／ポーズ解除ができます。
- ゲームをスタートするといきなりボス（大きな鳥）が出てくるようになりました。ボス戦からスタートするようプログラムに仕込まれた設定を有効にしたため、ゲームの動作が変わったことを確認出来ます。

![](imgs/quick_start/x8_qs_debug_mode.png "Debug Mode")

### スクリーンショット

- 適当な場面で <img src="imgs/icons/ui_icon_12.png" width="18"> **一時停止**します。
- <img src="imgs/icons/ui_icon_69.png" width="18"> **スクリーンショット**ボタンを押すと[Home画面](manual.md#Home画面)用のスクリーンショットを設定でるウィンドウが開きますので、**設定**してウィンドウを閉じます。
- 設定したスクリーンショットは後ほどホーム画面で確認出来ます。

![](imgs/quick_start/x8_qs_screenshot.png "Screenshot")

### 名前をつけて保存

- 改造したゲームに名前をつけて保存しましょう。画面左下の <img src="imgs/icons/ui_icon_01.png" width="18"> **ファイルメニュー**を開き**名前を付けて保存...**を選択するとプロジェクトを保存するためのウィンドウが開きます。
- <img src="imgs/icons/ui_icon_62.png" width="18"> **画面キーボード**で適当な名前を付けて`Enter`キーでファイルが保存されます。ここでは`boss_test`としています。ファイル名に使える文字数と文字種には制限があります。拡張子も付けられません。
- ゲームを保存したらプロジェクトを閉じてHome画面に戻ります。

![](imgs/quick_start/x8_qs_save_as.png "Save As")

### プロジェクトフォルダ

- ユーザーが作成したプロジェクトファイルは <img src="imgs/icons/ui_icon_75.png" width="18"> **プロジェクトフォルダ**に保存されます。先程の`boss_test`が保存され、スクリーンショットも反映されているのが確認出来ます。

![](imgs/quick_start/x8_qs_user_project.png "User Project")

#### **おめでとうございます！サンプルを改造して別のプロジェクトとして保存出来るようになりました！**

---

## 4.新しいプロジェクトを作成してプログラムを書いてみよう

プロジェクトを新規作成してプログラミングを始めてみましょう。

### プロジェクト新規作成

- **Home画面**の <img src="imgs/icons/ui_icon_80.png" width="18"> **プロジェクト新規作成**ボタンで空のプロジェクトを新規に作成します。

![](imgs/quick_start/x8_qs_home_new_project.png "New project")

### プログラムを書く

- **Codeエディタ**で <img src="imgs/icons/ui_icon_62.png" width="18"> **[画面キーボード](manual.md#画面キーボード)**を出して以下のように入力します。（[外部キーボード](manual.md#外部キーボード)にも対応しています。）
```
x8.fnt("Hello World!",0,0)
```
- 文字を入力していると**[補完ポップアップ](manual.md#Codeエディタ)**が出てきますが、今は気にせず入力を続けましょう。

![](imgs/quick_start/x8_qs_code_comp.png "")

![](imgs/quick_start/x8_qs_code_hello_world.png "")

### プログラムを実行する

- **Debugモード**に移動し <img src="imgs/icons/ui_icon_59.png" width="18"> **デバッグ実行**してみます。プログラムが正しければマシン画面の左上に`Hello World!`と表示されます。
- うまく表示されない場合は**Codeエディタ**に戻ってプログラムが正しく入力されているか確認して下さい。

![](imgs/quick_start/x8_qs_debug_hello_world.png "")

#### **おめでとうございます！x8マシンのプログラミングに成功しました！**

- この初めてのプロジェクトを取っておきたい場合は <img src="imgs/icons/ui_icon_01.png" width="18"> **ファイルメニュー**の**保存**でプロジェクトを保存しましょう。最初に保存する際はファイル名を入力するウィンドウが開きます。

### もう少しやってみる

- **Codeエディタ**に戻って先程入力したプログラムの下に以下を追加します。
```
x8.circ(40,40,10,9)
```

![](imgs/quick_start/x8_qs_code_circ.png "")

- 再び**Debugモード**に移動して実行してみます。プログラムが正しければ`Hello World!`に加えて**オレンジ色の円**も表示されます。
- うまく表示されない場合は**Codeエディタ**に戻ってプログラムが正しく入力されているか確認して下さい。

![](imgs/quick_start/x8_qs_debug_circ.png "")

#### **おめでとうございます！プログラムにより画面に図形を描けるようになりました！**

---

## 5.全ての機能を利用するには...

初期状態ではプログラミング以外のエディタ機能がロックされていて編集出来ません。

- Home画面の <img src="imgs/icons/ui_icon_72.png" width="18"> **購入ウィンドウ**からサブスクリプション**「全機能アンロック」**を購入すると以下のような全ての機能が利用可能になります！
    - Gfxエディタ、Mapエディタによるゲームのグラフィックス作成機能
    - Sfxエディタによるゲームの効果音作成機能
    - その他、将来のアップデートで追加される機能など
- 購入についての詳しい説明は**購入ウィンドウ**の**ヘルプ**をご確認下さい。
- **Codeエディタによるプログラミング機能は無料のままご利用いただけます！**

---

## 6.このあとは...

#### **おめでとうございます！ゲームを作る準備が出来ました！このあとは...**

- このままプログラミングのチュートリアルを進めたい方は[プログラミングチュートリアル](programming_tutorial.md)へどうぞ。
- x8studioの詳しい使い方を知りたい方は[マニュアル](manual.md)へどうぞ。
- x8独自のAPIについて詳しく知りたい方は[APIリファレンス](api_reference.md)へどうぞ。

#### **ゲームプログラミングの楽しさを少しでも知ってもらえたら嬉しいです！**
