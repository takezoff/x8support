# マニュアル

## Home

![](imgs/manual/x8_doc_home_desc.png "Home/sample")

- **プロジェクト情報**にはファイルリストで選択されたプロジェクトファイルの情報が表示されます。
    - **スクリーンショット**はDebugモードで撮影されたスクリーンショットです。
    - **プロジェクトコメント**はコード先頭に記述されたコメントです。コードの先頭から行頭が`--`で始まる、最大４行のコメントがここに表示されます。
- **プロジェクト新規作成**ボタンを押すと、空のプロジェクトを作成してStudioに遷移します。
- **フォルダタブ**はファイルリストを表示するフォルダを選択します。
    - <img src="imgs/icons/ui_icon_05.png" width="18"> **サンプルフォルダ**はアプリに同梱されているサンプルファイルが入っているフォルダです。ファイルをセーブしたり削除したりすることは出来ません。サンプルファイルのカスタマイズは可能ですが、セーブはプロジェクトフォルダで行われます。
    - <img src="imgs/icons/ui_icon_75.png" width="18"> **プロジェクトフォルダ**はユーザー作成のプロジェクトが保存されるフォルダです。ファイルをセーブしたり削除することが出来ます。
- **ファイルリスト**にはフォルダタブで選択されているフォルダのファイルが表示されます。ファイルを選択して、行いたい操作を**ファイル操作**で選択します。
- **ファイル操作**では選択しているファイルを操作します。
    - <img src="imgs/icons/ui_icon_74.png" width="18"> **開く**で選択しているプロジェクトを開いてStudioに遷移します。
    - <img src="imgs/icons/ui_icon_60.png" width="18"> **あそぶ**で選択しているプロジェクトを直接Runモードで開始します。
    - <img src="imgs/icons/ui_icon_71.png" width="18"> **削除**で選択しているファイルを削除します。

---

## Studio共通のUIと操作

![](imgs/manual/x8_doc_studio_desc.png "Studio Common")

### トップバーとボトムバー
トップバーとボトムバーは、全てのエディタで共通のUIです。

- **ヒント**にはタッチしているUIのヒントや、一時的な通知などが表示されます。
- **ステータス**には現在の状態に関連する情報が表示されます。
- **プロジェクト名**には現在エディット中のプロジェクト名が表示されます。
- **プロジェクトステータス**にはプロジェクトの状態（`-`変更なし、`*`変更あり）が表示されます。
- **メニュー**
    - <img src="imgs/icons/ui_icon_00.png" width="18"> **x8メニュー**
        - 本アプリの情報やサポートページへのリンクなど
    - <img src="imgs/icons/ui_icon_01.png" width="18"> **ファイルメニュー**
        - 開いているプロジェクトファイルの操作など
    - <img src="imgs/icons/ui_icon_03.png" width="18"> **オプションメニュー**
        - 入力設定など
- **エディタ**
    - <img src="imgs/icons/ui_icon_04.png" width="18"> **Codeエディタ**
    - <img src="imgs/icons/ui_icon_05.png" width="18"> **Gfxエディタ**
    - <img src="imgs/icons/ui_icon_06.png" width="18"> **Mapエディタ**
    - <img src="imgs/icons/ui_icon_07.png" width="18"> **Sfxエディタ**
    - <img src="imgs/icons/ui_icon_59.png" width="18"> **Debugモード**
- **Runモード**
    - <img src="imgs/icons/ui_icon_60.png" width="18"> **Runモード**
- **Undo/Redo**
    - <img src="imgs/icons/ui_icon_14.png" width="18"> **Undo**（もとに戻す）
    - <img src="imgs/icons/ui_icon_15.png" width="18"> **Redo**（やり直す）

### <img src="imgs/icons/ui_icon_28.png" width="30"> タッチカーソル
**タッチカーソル**は指でのタッチでは難しい細かい作業を行う場合に利用します。

- ボタン以外の部分をドラッグすると、タッチカーソルを移動できます。
- ボタンを押すと、タッチカーソルのポインタ（タッチカーソル上方の点）の位置をタッチできます。
- ボタンを押しながら移動すると、タッチカーソルのポインタの位置でラッグができます。

![](imgs/manual/x8_doc_touch_cursor.gif "Touch Cursor")

### <img src="imgs/icons/ui_icon_62.png" width="30"> スクリーンキーボード
**スクリーンキーボード**は外部キーボードを使わずに文字入力を行う場合に利用します。`Shift`、`Ctrl`、`Alt`の修飾トグルには、その左にロックするトグルがあり、ロックされていないと１回の文字入力で修飾がオフになります。`Mode`キーで、**通常文字** → **特殊文字** → **カナ**、の順に入力モードが切り替わります。（カナはJPキーボードの場合だけです）

![](imgs/manual/x8_doc_screen_keyboard.gif "Screen Keyboard")

---

## Codeエディタ

![](imgs/manual/x8_doc_code_desc.png "Code Editor")

- **コードエリア**にはプログラムコードが表示されます。ここでプログラミングを行います。
- **コード選択**
    - <img src="imgs/icons/ui_icon_63.png" width="18"> **コード切り替え**はエディットするコードを、直前にエディットしていたコードと切り替えます。
    - <img src="imgs/icons/ui_icon_04.png" width="18"> **コード選択**はエディットするコードを選択します。
- **エディットツール**
    - <img src="imgs/icons/ui_icon_02.png" width="18"> **編集メニュー**はコピーやペーストなどの編集機能のメニューです。
    - <img src="imgs/icons/ui_icon_90.png" width="18"> **移動メニュー**はページ移動や行頭へ移動などのカーソル移動機能のメニューです。
    - <img src="imgs/icons/ui_icon_91.png" width="18"> **検索メニュー**は検索機能のメニューです。
    - <img src="imgs/icons/ui_icon_92.png" width="18"> **入力モードメニュー**は入力モードを切り替えるメニューです。

### コード補完とコードスニペット
コードエリアに文字を入力すると、補完候補があれば補完ポップアップが開きます。ワードの末尾にカーソルを合わせて`Alt+Tab`でも（補完候補があれば）開くことができます。

![](imgs/manual/x8_doc_completion_popup.gif "Completion Popup")

- そのまま文字入力を続けると、候補が絞られます。
- `Tab`,`Shift+Tab`で候補を選択して、`Enter`で確定出来ます。
- `Ctrl+Tab`または`Esc`を押すかカーソル移動操作を行うと、ポップアップは閉じます。
- 補完中に`Alt+Tab`で、補完候補に対応するコードスニペットを入力できます。

---

## Gfxエディタ

![](imgs/manual/x8_doc_gfx_desc.png "Gfx Editor")

- **エディットビュー**ではGfxビューで選択されたエリアをエディットします。
- **Gfxビュー**ではエディットするGfxエリアを選択します。
- **スタンプビュー**にはキャプチャされたスタンプデータが表示されます。
    - <img src="imgs/icons/ui_icon_31.png" width="18"> はスタンプデータの`color:0`の抜き設定を切り替えます。
- **カラーパレット**は描画ツールで参照されるカラーを選択します。
- **描画ツール**
    - <img src="imgs/icons/ui_icon_33.png" width="18"> ペンで描画する（※タッチしたまま選択、離して確定）
        - <img src="imgs/icons/ui_icon_33.png" width="18"> ピクセルペン
        - <img src="imgs/icons/ui_icon_34.png" width="18"> 四角いペン
        - <img src="imgs/icons/ui_icon_35.png" width="18"> 丸いペン
    - <img src="imgs/icons/ui_icon_40.png" width="18"> スタンプデータを描画する
    - <img src="imgs/icons/ui_icon_64.png" width="18"> スタンプデータをキャプチャする
    - <img src="imgs/icons/ui_icon_02.png" width="18"> チップ属性をエディットする
    - <img src="imgs/icons/ui_icon_32.png" width="18"> エディットビューでエリアを選択します。
    - <img src="imgs/icons/ui_icon_67.png" width="18"> 選択エリアの効果を選ぶ
        - <img src="imgs/icons/ui_icon_67.png" width="18"> 選択エリアに関係なくエディットを可能にします。
        - <img src="imgs/icons/ui_icon_65.png" width="18"> 選択エリアの内側だけをエディットを可能にします。
        - <img src="imgs/icons/ui_icon_66.png" width="18"> 選択エリアの外側だけをエディットを可能にします。
    - <img src="imgs/icons/ui_icon_68.png" width="18"> グリッドを表示します。
- **Gfx選択ツール**
    - <img src="imgs/icons/ui_icon_38.png" width="18"> エディットするGfx選択エリアの形とサイズを固定します。
    - <img src="imgs/icons/ui_icon_68.png" width="18"> グリッドを表示します。

![](imgs/manual/x8_doc_gfx_attr_desc.png "Gfx Editor")

- <img src="imgs/icons/ui_icon_02.png" width="18"> **チップ属性エディット**
    - チップ(8x8)に対応する1byte(8bit)の属性データをエディットします。
    - 8色のカラーパレットがエディットする属性データのビット位置に対応しています。
    - エディットビューで色を塗ることで対応するビットをONに出来ます。

---

## Mapエディタ

![](imgs/manual/x8_doc_map_desc.png "Map Editor")

- **エディットビュー**ではMap選択ビューで選択されたエリアをエディットします。
- **Gfxビュー**ではエディットビューに設定するチップ矩形を選択します。
- **チップ番号：0**のチップはMapエディタおよび実際のマップ描画において、描画されないチップ（抜きのチップ）として機能します。スプライトとしては他の領域と区別なく描画されます。
- **スタンプビュー**にはキャプチャされたスタンプデータが表示されます。
- **Map選択ビュー**ではエディットするMapエリアをタッチで選択します。
- **Mapカーソルキー**はMap選択ビューの選択矩形を操作します。
    - <img src="imgs/icons/ui_icon_18.png" width="18"> <img src="imgs/icons/ui_icon_19.png" width="18"> <img src="imgs/icons/ui_icon_16.png" width="18"> <img src="imgs/icons/ui_icon_17.png" width="18"> 選択エリアを移動します。
    - <img src="imgs/icons/ui_icon_93.png" width="18"> 選択エリアを左上にリセットします。
    - <img src="imgs/icons/ui_icon_94.png" width="18"> 現在の選択エリアの左上を固定します。固定した状態でカーソルを移動するとエリアのサイズを変更できます。
- **配置ツール**
    - <img src="imgs/icons/ui_icon_05.png" width="18"> Gfxビューで選択されているチップを配置する
    - <img src="imgs/icons/ui_icon_40.png" width="18"> スタンプデータを配置する
    - <img src="imgs/icons/ui_icon_64.png" width="18"> スタンプデータをキャプチャする
    - <img src="imgs/icons/ui_icon_32.png" width="18"> エディットビューでエリアを選択します。
    - <img src="imgs/icons/ui_icon_67.png" width="18"> 選択エリアの効果を選ぶ
        - <img src="imgs/icons/ui_icon_67.png" width="18"> 選択エリアに関係なくエディットを可能にします。
        - <img src="imgs/icons/ui_icon_65.png" width="18"> 選択エリアの内側だけをエディットを可能にします。
        - <img src="imgs/icons/ui_icon_66.png" width="18"> 選択エリアの外側だけをエディットを可能にします。
    - <img src="imgs/icons/ui_icon_68.png" width="18"> グリッドを表示します。
- **Gfx選択ツール**
    - <img src="imgs/icons/ui_icon_38.png" width="18"> エディットするGfx選択エリアの形とサイズを固定します。
    - <img src="imgs/icons/ui_icon_68.png" width="18"> グリッドを表示します。

---

## Sfxエディタ

![](imgs/manual/x8_doc_sfx_desc.png "Sfx Editor")

- **エディットビュー**ではSfxを構成する16個のノートをタッチでエディット出来ます。
    - **ノート**の表示では、波線とそれに付随する数値が波形とピッチオフセットを、緑のブロックがボリューム値を表しています。
- **エディットツール**
    - <img src="imgs/icons/ui_icon_07.png" width="18"> エディットするSfxを選択します。
    - <img src="imgs/icons/ui_icon_52.png" width="18"> Sfxの有効／無効を切り替えます。
    - <img src="imgs/icons/ui_icon_53.png" width="18"> 他のSfxからコピーして設定します。
    - <img src="imgs/icons/ui_icon_54.png" width="18"> 再生スピードを設定します。数値が小さいほど速くなります。
    - <img src="imgs/icons/ui_icon_42.png" width="18"> ループの有効／無効を切り替えます。有効な場合はエディットビュー下の<img src="imgs/icons/ui_icon_42.png" width="18">をドラッグして、ループ位置を設定できます。
    - <img src="imgs/icons/ui_icon_49.png" width="18"> ノートをタッチして音高を設定出来ます。調整キーでも音高を設定出来ます。
    - <img src="imgs/icons/ui_icon_50.png" width="18"> タッチで選択したノートの音高を鍵盤で設定出来ます。選択位置は自動的に右へ移動します。調整キーでも音高を設定出来ます。
    - <img src="imgs/icons/ui_icon_51.png" width="18"> タッチでノートのボリュームを設定出来ます。調整キーでもボリュームを設定出来ます。
    - <img src="imgs/icons/ui_gfx_icon_08.png" width="18"> タッチでノートの波形を設定出来ます。（※タッチしたまま選択、離して確定）
        - <img src="imgs/icons/ui_gfx_icon_08.png" width="18"> サイン波
        - <img src="imgs/icons/ui_gfx_icon_09.png" width="18"> 矩形波(1:1)
        - <img src="imgs/icons/ui_gfx_icon_10.png" width="18"> 矩形波(1:3)
        - <img src="imgs/icons/ui_gfx_icon_11.png" width="18"> 矩形波(1:7)
        - <img src="imgs/icons/ui_gfx_icon_12.png" width="18"> ノコギリ波
        - <img src="imgs/icons/ui_gfx_icon_13.png" width="18"> 三角波
        - <img src="imgs/icons/ui_gfx_icon_14.png" width="18"> ホワイトノイズ
        - <img src="imgs/icons/ui_gfx_icon_15.png" width="18"> ノイズ(音高あり)
    - <img src="imgs/icons/ui_icon_10.png" width="18"> 鍵盤でピッチオフセットを指定して、試し弾きが出来ます。
- **再生ツール**
    - <img src="imgs/icons/ui_icon_11.png" width="18"> Sfxを再生します。
    - <img src="imgs/icons/ui_icon_39.png" width="18"> Sfxの再生を停止します。
- **鍵盤**
    - 黄色い枠は`ピッチオフセット:0`を表しています。

---

## Debugモード

![](imgs/manual/x8_doc_debug_desc.png "Debug Mode")

- **デバッグツール**
    - <img src="imgs/icons/ui_icon_59.png" width="18"> デバッグ実行を開始／停止します。
    - <img src="imgs/icons/ui_icon_12.png" width="18"> デバッグ実行をポーズ／ポーズ解除します。
    - <img src="imgs/icons/ui_icon_13.png" width="18"> 仮想マシンをリセットします。
    - <img src="imgs/icons/ui_icon_70.png" width="18"> ログビューの表示／非表示を切り替えます。
    - <img src="imgs/icons/ui_icon_71.png" width="18"> ログをクリアします。
    - <img src="imgs/icons/ui_icon_69.png" width="18"> Home画面のプロジェクト情報に表示されるスクリーンショットを撮影します。
- **ログビュー**
    - <img src="imgs/icons/ui_icon_70.png" width="18"> ログビュー表示がONの場合、ゲーム画面上に各ログの１行目が表示されます。タッチでログを選択すると、ログ詳細ビューにそのログの詳細が表示されます。
    - **ログ詳細ビュー**をタッチすると**ログ詳細ウィンドウ**が開きます。
- **ログ詳細ウィンドウ**
    - ログにエラー箇所が表示されている場合、`エラーに移動`ボタンを押すとCodeエディタに遷移してエラー位置に移動出来ます。
- **ボリューム**
    - 仮想マシンのボリュームを変更出来ます。何らかの要因で仮想マシンがポーズされると自動的に0に設定されます。
- **ゲームパッドボタン**
    - 仮想マシンのゲームパッドのボタンです。赤い数字で示されているのは、APIでボタン情報を取得する際のビット位置です。

---

## Runモード

![](imgs/manual/x8_doc_run_desc.png "Run Mode")

- **メニューボタン**を押すと仮想マシンの**再起動**または**終了**を実行するメニューが開きます。

---

## 画面キーボード

- <img src="imgs/icons/ui_icon_03.png" width="18"> **オプションメニュー**の**入力設定**で画面キーボードを以下のものから選べます。
    - **QWERTY JP**で日本語キーボードになります。**カナ**が入力出来ます。
    - **QWERTY US**で英語キーボードになります。**カナ**は入力出来ません。

---

## 外部キーボード

- **外部キーボード**については、QWERTY配列の英語(US)キーボードと日本語(JIS)キーボードに対応しています。
- 接続されているキーボードタイプは自動的には判別されないため、**オプションメニュー** → **入力設定** → **外部キーボード**で、接続されているキーボードタイプを設定する必要があります。
    - **QWERTY US**でQWERTY配列の英語(US)キーボードとして認識します。カナは入力出来ません。
    - **QWERTY JP**で**一部のサードパーティー製日本語(JIS)キーボード**として認識します。カナが入力出来ます。
    - **Apple JP**で日本語(JIS)キーボードとして認識します。カナが入力出来ます。
- Apple純正のキーボードであれば**QWERTY US**か**Apple JP**に設定します。
- `caps lock`キーは本来の**CapsLock**としては機能しません。アプリ側で入力が取得出来る場合は`control`キーとして動作します。

### 外部キーボードの設定と動作確認状況

|動作|機種|配列|設定|
|:--:|:---|:--:|:---|
|OK|Apple Wireless Keyboard 2011 英語(US)|US|**QWERTY US**|
|OK|Magic Keyboard 日本語(JIS)|JIS|**Apple JP**|
|OK|Anker Ultra-Slim Bluetooth Keyboard (A7726)|US|**QWERTY US**|
|OK|ロジクール K380 マルチデバイス Bluetooth キーボード（日本語配列）|JIS|**QWERTY US**または**QWERTY JP** `※`|
|未確認|その他の英語(US)キーボード|US|**QWERTY US**|
|未確認|その他のApple純正日本語(JIS)キーボード|JIS|**Apple JP**|
|未確認|その他のサードパーティー製日本語(JIS)キーボード|JIS|**QWERTY US**|

- サードパーティー製日本語(JIS)キーボードは基本的に**QWERTY US**に設定することにご注意下さい。
- `※`一部のサードパーティー製日本語(JIS)キーボードについては**QWERTY JS**に設定することにより、キーを刻印どおり入力出来るようアプリ側で対処することができます。ただし、以下につては別のキーで代用して入力します。
    - `\`（バックスラッシュ）は`漢字`キーで入力
    - `_`（アンダースコア）は`Shift+漢字`で入力
    - `|`（パイプ）は`Shift+0`で入力
    - 半角カナの`ﾛ`は`漢字`キーで入力
    - 半角カナの`ｰ`は`Shift+漢字`キーで入力
- `※`サードパーティー製日本語(JIS)キーボードのうち**QWERTY JS**設定での動作確認済み機種は以下の通りです。
    - ロジクール K380 マルチデバイス Bluetooth キーボード（日本語配列）


---

## ショートカットキー

- キーの記号の意味
    - `#`はShiftキーと同時押し
    - `^`はCtrlキーと同時押し
    - `&`はAltキーと同時押し

### Codeエディタ

- **Shiftを押しながら移動系のキーやショートカットを押すと、選択しながら移動出来ます。**

|キー|機能|
|:--:|:---|
|`&Tab`|行をインデント|
|`#Tab`|行をアウトデント|
|`^Tab`|カーソル位置で可能なら補完ポップアップを開く|
|`^Enter`|上に行を挿入|
|`#^Enter`|下に行を挿入|
|`^↑`|ページUp|
|`^↓`|ページDown|
|`^←`|前のワード境界へ|
|`^→`|次のワード境界へ|
|`&↑`|テキスト先頭へ|
|`&↓`|テキスト末尾へ|
|`&←`|行頭へ|
|`&→`|行末へ|
|`^A`|全選択|
|`^C`|コピー|
|`^D`|削除（コピーバッファに追加しない）|
|`^F`|前方検索ポップアップを開く|
|`#^F`|後方検索ポップアップを開く|
|`^&G`|グリフ入力モード|
|`^K`|カーソルから行末まで削除|
|`^&K`|カナ入力モード|
|`^L`|カーソルが画面中央に来るようにスクロール|
|`^&N`|通常入力モード|
|`^V`|貼り付け|
|`#^V`|行頭に貼り付け|
|`^X`|カット（コピーバッファに追加する）|
|`^Z`|アンドゥ|
|`#^Z`|リドゥ|

### Codeエディタの補完ポップアップ

|キー|機能|
|:--:|:---|
|`Enter`|確定して閉じる|
|`Esc`|キャンセルして閉じる|
|`Tab`|次の候補へ|
|`#Tab`|前の候補へ|
|`&Tab`|補完モードとスニペットモードを切り替える|
|`^Tab`|キャンセルして閉じる|

### Codeエディタの検索ウィンドウ

|キー|機能|
|:--:|:---|
|`^F`|次の前方の検索結果へ|
|`#^F`|次の後方の検索結果へ|

