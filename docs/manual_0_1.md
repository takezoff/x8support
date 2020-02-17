# マニュアル（ver. 0.1：開発段階の古いもの）

## Home

![](imgs_0_1/manual/x8_doc_home_desc.png "Home/sample")

- **プロジェクト情報**には、ファイルリストで選択されたプロジェクトファイルの情報が表示されます。
    - **スクリーンショット**は、Debugモードで撮影されたスクリーンショットです。
    - **コメント**は、コード先頭に記述された、プロジェクトに関するコメントです。
- **新規作成**ボタンを押すと、空のプロジェクトを作成してStudioに遷移します。
- **フォルダタブ**で、ファイルリストを表示するフォルダを選択します。
    - **sample**フォルダは、アプリに同梱されているサンプルファイルが入っているフォルダです。ファイルをセーブしたり削除したりすることは出来ません。サンプルファイルのカスタマイズは可能ですが、セーブはprojectフォルダで行われます。
    - **project**フォルダは、ユーザー作成のプロジェクトが保存されるフォルダです。ファイルをセーブしたり削除することが出来ます。
- **ファイルリスト**には、フォルダタブで選択されているフォルダのファイルが表示されます。ファイルを選択して、行いたい操作を**ファイル操作**で選択します。

---

## Studio共通のUIと操作

![](imgs_0_1/manual/x8_doc_studio_desc.png "Studio Common")

### トップバーとボトムバー
トップバーとボトムバーは、全てのエディタで共通のUIです。

- **ヒントメッセージ**には、タッチしているUIのヒントや、一時的な通知などが表示されます。
- **ステータスメッセージ**には、現在の状態に関連する情報が表示されます。
- **プロジェクト名**には、現在エディット中のプロジェクト名が表示されます。
- <img src="imgs/icons/ui_icon_00.png" width="18"> **x8メニュー**
- <img src="imgs/icons/ui_icon_01.png" width="18"> **ファイルメニュー**
- <img src="imgs/icons/ui_icon_02.png" width="18"> **エディットメニュー**
- <img src="imgs/icons/ui_icon_03.png" width="18"> **オプションメニュー**
- <img src="imgs/icons/ui_icon_59.png" width="18"> **Debugモード**
- <img src="imgs/icons/ui_icon_04.png" width="18"> **Codeエディタ**
- <img src="imgs/icons/ui_icon_05.png" width="18"> **Gfxエディタ**
- <img src="imgs/icons/ui_icon_06.png" width="18"> **Mapエディタ**
- <img src="imgs/icons/ui_icon_07.png" width="18"> **Sfxエディタ**
- <img src="imgs/icons/ui_icon_08.png" width="18"> **Phraseエディタ**
- <img src="imgs/icons/ui_icon_09.png" width="18"> **Musicエディタ**
- <img src="imgs/icons/ui_icon_60.png" width="18"> **Runモード**
- <img src="imgs/icons/ui_icon_61.png" width="18"> **チートシート**
- <img src="imgs/icons/ui_icon_14.png" width="18"> **Undo**（もとに戻す）
- <img src="imgs/icons/ui_icon_15.png" width="18"> **Redo**（やり直す）

### ポップアップメニュー
ポップアップメニューは、ボタンをタッチしている間だけ現れるメニューです。タッチしたまま選択したい項目に移動し、タッチを放すことで確定されます。

![](imgs_0_1/manual/x8_doc_popup_menu.gif "Popup Menu")

### <img src="imgs/icons/ui_icon_28.png" width="30"> タッチカーソル
**タッチカーソル**は、指でのタッチでは難しい細かい作業を行う場合に利用します。

- ボタン以外の部分をドラッグすると、タッチカーソルを移動できます。
- ボタンを押すと、タッチカーソルのポインタ（タッチカーソル上方の点）の位置をタッチができます。
- ボタンを押しながら移動すると、タッチカーソルのポインタの位置でラッグができます。

![](imgs_0_1/manual/x8_doc_touch_cursor.gif "Touch Cursor")

### <img src="imgs/icons/ui_icon_62.png" width="30"> スクリーンキーボード
**スクリーンキーボード**は、ハードウエアキーボードを使わずに、文字入力を行う場合に利用します。**Shift**、**Ctrl**、**Alt**の修飾キーはON/OFFのトグルです。**Off**キーを押すと全ての修飾キーがOFFになります。**Mode**キーで、通常文字 → 特殊文字 → カナ、の順に入力モードが切り替わります。（USキーボードではカナはありません）

![](imgs_0_1/manual/x8_doc_screen_keyboard.gif "Screen Keyboard")

---

## Codeエディタ

![](imgs_0_1/manual/x8_doc_code_desc.png "Code Editor")

- **コードエリア**には、プログラムコードが表示されます。ここでプログラミングを行います。
- <img src="imgs/icons/ui_icon_63.png" width="18"> **コード切り替え**は、編集するコードを、直前に編集していたコードと切り替えます。
- **コード選択**は、編集するコードを選択します。

### コード補完とコードスニペット
コードエリアに文字を入力すると、補完候補があれば補完ポップアップが表示されます。

![](imgs_0_1/manual/x8_doc_completion_popup.gif "Completion Popup")

- そのまま文字入力を続けると、候補が絞られます。
- 上下キーで候補を選択して、Enterキーで確定出来ます。
- Escキーを押すかカーソル移動操作を行うと、ポップアップは消えます。
- 補完中にTabキーを押すと、補完候補に対応するコードスニペットを入力できます。

---

## Gfxエディタ

![](imgs_0_1/manual/x8_doc_gfx_desc.png "Gfx Editor")

- **エディットビュー**では、Gfxビューで選択されたエリアをエディットします。
- **Gfxビュー**では、エディットするGfxエリアを選択します。
- **スタンプビュー**には、キャプチャされたスタンプデータが表示されます。
- <img src="imgs/icons/ui_icon_31.png" width="18"> **抜き設定**は、スタンプデータの`color:0`の抜き設定を切り替えます。
- **カラーパレット**は、描画ツールで参照されるカラーを選択します。
- **描画ツール**
    - <img src="imgs/icons/ui_icon_33.png" width="18"> ペン1
    - <img src="imgs/icons/ui_icon_34.png" width="18"> ペン2
    - <img src="imgs/icons/ui_icon_35.png" width="18"> ペン3
    - <img src="imgs/icons/ui_icon_40.png" width="18"> スタンプデータを描画する
    - <img src="imgs/icons/ui_icon_64.png" width="18"> スタンプデータをキャプチャする
- <img src="imgs/icons/ui_icon_32.png" width="18"> **選択ツール**は、エディットビューでエリアを選択します。
- **エディットエリア選択**
    - <img src="imgs/icons/ui_icon_67.png" width="18"> 選択エリアに関係なくエディットを可能にします。
    - <img src="imgs/icons/ui_icon_65.png" width="18"> 選択エリアの内側だけをエディットを可能にします。
    - <img src="imgs/icons/ui_icon_66.png" width="18"> 選択エリアの外側だけをエディットを可能にします。
- <img src="imgs/icons/ui_icon_68.png" width="18"> グリッドを表示します。
- <img src="imgs/icons/ui_icon_38.png" width="18"> エディットするGfxエリアの形とサイズを固定します。

![](imgs_0_1/manual/x8_doc_gfx_attr_desc.png "Gfx Editor")

- <img src="imgs/icons/ui_icon_02.png" width="18"> **チップ属性エディット**
    - チップ(8x8)に対応する1byte(8bit)の属性データをエディットします。
    - 8色のカラーパレットで、エディットする属性のビットを選択出来ます。

---

## Mapエディタ

![](imgs_0_1/manual/x8_doc_map_desc.png "Map Editor")

- **エディットビュー**では、Mapエリア選択ビューで選択されたエリアをエディットします。
- **Gfxビュー**では、エディットビューに設定するチップ矩形を選択します。
- **スタンプビュー**には、キャプチャされたスタンプデータが表示されます。
- **Mapエリア選択ビュー**では、エディットするMapエリアを選択します。
- **Mapエリア選択カーソル**は、Mapエリア選択ビューの選択矩形を移動します。
- **描画ツール**
    - <img src="imgs/icons/ui_icon_05.png" width="18"> Gfxビューで選択されているチップを配置する
    - <img src="imgs/icons/ui_icon_40.png" width="18"> スタンプデータを配置する
    - <img src="imgs/icons/ui_icon_64.png" width="18"> スタンプデータをキャプチャする
- <img src="imgs/icons/ui_icon_32.png" width="18"> **選択ツール**は、エディットビューでエリアを選択します。
- **エディットエリア選択**
    - <img src="imgs/icons/ui_icon_67.png" width="18"> 選択エリアに関係なくエディットを可能にします。
    - <img src="imgs/icons/ui_icon_65.png" width="18"> 選択エリアの内側だけをエディットを可能にします。
    - <img src="imgs/icons/ui_icon_66.png" width="18"> 選択エリアの外側だけをエディットを可能にします。
- <img src="imgs/icons/ui_icon_68.png" width="18"> グリッドを表示します。
- <img src="imgs/icons/ui_icon_38.png" width="18"> Gfxビューで選択されたチップ矩形の形とサイズを固定します。

---

## Sfxエディタ

![](imgs_0_1/manual/x8_doc_sfx_desc.png "Sfx Editor")

- **エディットビュー**では、Sfxを構成する16個のノートを、タッチでエディット出来ます。
    - **ノート**の表示は、水平の線と付随する数値が波形とピッチオフセットを、緑のブロックがボリューム値を表しています。
    - エディットビュー下部の<img src="imgs/icons/ui_icon_42.png" width="18">マークをドラッグして、ループ位置を設定できます。
- <img src="imgs/icons/ui_icon_07.png" width="18"> エディットするSfxを選択します。
- <img src="imgs/icons/ui_icon_52.png" width="18"> Sfxの有効／無効を切り替えます。
- <img src="imgs/icons/ui_icon_53.png" width="18"> 他のSfxからコピーして設定します。
- <img src="imgs/icons/ui_icon_54.png" width="18"> 再生スピードを設定します。数値が小さいほど速くなります。
- <img src="imgs/icons/ui_icon_42.png" width="18"> ループの有効／無効を切り替えます。有効な場合は、エディットビューでループ位置を設定できます。
- **ピッチツール**
    - <img src="imgs/icons/ui_icon_50.png" width="18"> **ピッチエディット**
        - MIDIキーボードで、選択中のノートのピッチを変更出来ます。
        - エディットビューをタッチして、ノートのピッチを変更出来ます。
    - <img src="imgs/icons/ui_icon_49.png" width="18"> **ピッチペン**
        - MIDIキーボードでピッチを選択した後、エディットビューをタッチすることで、ノートにそのピッチを設定出来ます。
- <img src="imgs/icons/ui_icon_51.png" width="18"> **ボリュームツール**は、エディットビューをタッチして、ノートのボリュームを設定出来ます。
- **波形ツール**は、エディットビューをタッチして、ノートの波形を設定出来ます。
    - <img src="imgs/icons/ui_gfx_icon_08.png" width="18"> サイン波
    - <img src="imgs/icons/ui_gfx_icon_09.png" width="18"> 矩形波
    - <img src="imgs/icons/ui_gfx_icon_10.png" width="18"> のこぎり波
    - <img src="imgs/icons/ui_gfx_icon_11.png" width="18"> 三角波
    - <img src="imgs/icons/ui_gfx_icon_12.png" width="18"> ノイズ
- <img src="imgs/icons/ui_icon_11.png" width="18"> Sfxを再生します。
- <img src="imgs/icons/ui_icon_39.png" width="18"> Sfxの再生を停止します。
- <img src="imgs/icons/ui_icon_10.png" width="18"> MIDIキーボードでピッチオフセットを指定して、試し弾きが出来ます。
- **MIDIキーボード**
    - 黄色い枠は、`ピッチオフセット:0`を表しています。
    - オレンジ色のマークは、選択されているピッチ（<img src="imgs/icons/ui_icon_49.png" width="18">**ピッチペン**で参照される）を表しています。

---

## Phraseエディタ

![](imgs_0_1/manual/x8_doc_phrase_desc.png "Phrase Editor")

- **エディットビュー**では、Phraseを構成する16個のSfxトリガーx4トラックを、タッチでエディット出来ます。
    - **Sfxトリガー**の表示は上から、オクターブ＋ピッチ、Sfx番号、ボリューム、を表しています。
    - エディットビュー下部の<img src="imgs/icons/ui_icon_39.png" width="18">マークをドラッグして、Phraseの長さを設定できます。
    - エディットビュー下部の<img src="imgs/icons/ui_icon_10.png" width="18">マークをドラッグして、試し弾き時の再生開始位置を設定できます。
- **トラックボリューム**では、各トラックのボリュームを設定できます。
- <img src="imgs/icons/ui_icon_08.png" width="18"> エディットするPhraseを選択します。
- <img src="imgs/icons/ui_icon_52.png" width="18"> Phraseの有効／無効を切り替えます。
- <img src="imgs/icons/ui_icon_53.png" width="18"> 他のPhraseからコピーして設定します。
- <img src="imgs/icons/ui_icon_41.png" width="18"> 再生スピードを設定します。単位はBPMです。
- **ピッチツール**
    - <img src="imgs/icons/ui_icon_50.png" width="18"> **ピッチエディット**
        - MIDIキーボードで、選択中のトリガーのピッチを変更出来ます。
        - エディットビューをタッチして、トリガーのピッチを変更出来ます。
    - <img src="imgs/icons/ui_icon_49.png" width="18"> **ピッチペン**
        - MIDIキーボードでピッチを選択した後、エディットビューをタッチすることで、トリガーにそのピッチを設定出来ます。
- **ボリュームツール**は、エディットビューをタッチして、トリガーのボリュームを設定出来ます。
    - <img src="imgs/icons/ui_gfx_icon_00.png" width="18"> 無音（＝トリガーなし）
    - <img src="imgs/icons/ui_gfx_icon_01.png" width="18"> <img src="imgs/icons/ui_gfx_icon_02.png" width="18"> <img src="imgs/icons/ui_gfx_icon_03.png" width="18"> <img src="imgs/icons/ui_gfx_icon_04.png" width="18"> <img src="imgs/icons/ui_gfx_icon_05.png" width="18"> <img src="imgs/icons/ui_gfx_icon_06.png" width="18"> <img src="imgs/icons/ui_gfx_icon_07.png" width="18"> ボリューム:1〜7
- <img src="imgs/icons/ui_icon_07.png" width="18"> **Sfxツール**は、エディットビューをタッチして、トリガーのSfx番号を設定出来ます。
- **エフェクトツール**
    - <img src="imgs/icons/ui_icon_56.png" width="18"> **Tie**は、次のトリガーとの間に自動で無音部分を挟む処理を禁止します。
    - <img src="imgs/icons/ui_icon_58.png" width="18"> **Mute**は、トリガーが無音の場合、無音を再生します（音を止めます）。
- <img src="imgs/icons/ui_icon_11.png" width="18"> Phraseを再生します。
- <img src="imgs/icons/ui_icon_39.png" width="18"> Phraseの再生を停止します。
- <img src="imgs/icons/ui_icon_10.png" width="18"> MIDIキーボードでピッチオフセットを指定して、試し弾きが出来ます。
- **MIDIキーボード**
    - 黄色い枠は、`ピッチオフセット:0`を表しています。
    - オレンジ色のマークは、選択されているピッチ（<img src="imgs/icons/ui_icon_49.png" width="18">**ピッチペン**で参照される）を表しています。

---

## Musicエディタ

![](imgs_0_1/manual/x8_doc_music_desc.png "Music Editor")

- **エディットビュー**では、Musicを構成する32個のPhraseトリガーを、タッチで選択出来ます。
    - **Phraseトリガー**の表示は上から、Phrase番号、<img src="imgs/icons/ui_icon_46.png" width="18">ジャンプ先、ジャンプ回数、を表しています。
    - Phraseトリガー上部の<img src="imgs/icons/ui_icon_46.png" width="18">マークをドラッグして、選択中のPhraseトリガーのジャンプ先を設定できます。
    - Phraseトリガー下部の<img src="imgs/icons/ui_icon_39.png" width="18">マークをドラッグして、Musicの長さを設定できます。
    - Phraseトリガー下部の<img src="imgs/icons/ui_icon_10.png" width="18">マークをドラッグして、試し弾き時の再生開始位置を設定できます。
- <img src="imgs/icons/ui_icon_09.png" width="18"> エディットするMusicを選択します。
- <img src="imgs/icons/ui_icon_52.png" width="18"> Musicの有効／無効を切り替えます
- <img src="imgs/icons/ui_icon_53.png" width="18"> 他のMusicからコピーして設定します。
- <img src="imgs/icons/ui_icon_41.png" width="18"> 再生スピードを設定します。単位はBPMです。
- <img src="imgs/icons/ui_icon_37.png" width="18"> **エディットツール**は、選択中のPhraseトリガーの内容をエディットします。
    - <img src="imgs/icons/ui_icon_08.png" width="18"> 選択中のPhraseトリガーのPhrase番号を設定します。
    - <img src="imgs/icons/ui_icon_46.png" width="18"> 選択中のPhraseトリガー再生後にジャンプする回数を設定します。1回以上ジャンプする場合は、エディットビューでジャンプ先を設定できます。
- <img src="imgs/icons/ui_icon_11.png" width="18"> Musicを再生します。
- <img src="imgs/icons/ui_icon_39.png" width="18"> Musicの再生を停止します。
- <img src="imgs/icons/ui_icon_10.png" width="18"> MIDIキーボードでピッチオフセットを指定して、試し弾きが出来ます。
- **MIDIキーボード**
    - 黄色い枠は、ピッチオフセット:0を表しています。

---

## Debugモード

![](imgs_0_1/manual/x8_doc_debug_desc.png "Debug Mode")

- **ディスプレイ**には、ゲーム画面が表示されます。
    - <img src="imgs/icons/ui_icon_70.png" width="18"> **ログ表示**がONの場合、ゲーム画面上に各ログの１行目が表示されます。タッチでログを選択すると、下部のウィンドウにそのログの詳細が表示されます。
    - **プログラムが停止した際は、ログでエラーの内容を確認してください。**
- <img src="imgs/icons/ui_icon_59.png" width="18"> デバッグ実行をスタート／ストップします。
- <img src="imgs/icons/ui_icon_12.png" width="18"> デバッグ実行をポーズ／再開します。
- <img src="imgs/icons/ui_icon_13.png" width="18"> x8マシンをリセットします。
- <img src="imgs/icons/ui_icon_69.png" width="18"> Home画面のプロジェクト情報に表示されるスクリーンショットを撮影します。
- <img src="imgs/icons/ui_icon_70.png" width="18"> ログの表示／非表示を切り替えます。
- <img src="imgs/icons/ui_icon_71.png" width="18"> ログをクリアします。

---

## Runモード

![](imgs_0_1/manual/x8_doc_run_desc.png "Run Mode")

- **電源スイッチ**は、x8マシンの電源をON/OFFするスライドスイッチです。左右にスライドで切り替えます。
- **戻るボタン**は、Runモードに遷移する直前の画面に戻ります。**電源スイッチがOFFの場合だけ有効です。**

