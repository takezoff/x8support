# Manual

## Home_Screen

You can play the included sample games and manage user-generated files.

![](imgs/manual/x8_doc_home_desc.png "Home/sample")

- The information of the project file selected in the file list is displayed in **Project Information**.
    - **Screenshot** is a screenshot taken in Debug mode.
    - **Project comment** is a comment written at the beginning of the code. Up to four lines of comments will be displayed here, starting with the first line of code with a `--`.
- The **Folder tab** selects the folder to display the file list.
    - <img src="imgs/icons/ui_icon_76.png" width="18"> **Sample folder** is the folder that contains the sample files bundled with the app. You can open the file, but the save is done in the project folder. The file cannot be deleted.
    - <img src="imgs/icons/ui_icon_75.png" width="18"> **Project folder** is the folder where user-created projects are stored. **Saving the project is always done here**.
    - <img src="imgs/icons/ui_icon_77.png" width="18"> **Import folder** is the folder where the imported files are stored. You can open the file, but the save is done in the project folder. Please note that **importing a file with the same name as an existing file will overwrite it**.
- The **file list** shows the files in the folder selected on the Folder tab. Select a file and then select the operation you want to perform with **file operation**.
- The **file operation** manipulates the selected file. The button may be found in the <img src="imgs/icons/ui_icon_86.png" width="18"> menu.
    - <img src="imgs/icons/ui_icon_74.png" width="18"> Open the selected project and go to Studio.
    - <img src="imgs/icons/ui_icon_60.png" width="18"> Start the selected project directly in Run mode.
    - <img src="imgs/icons/ui_icon_71.png" width="18"> Deletes the selected file.
    - <img src="imgs/icons/ui_icon_78.png" width="18"> You can export the selected file outside of this application. **If you don't have an export destination, you can't export.** We recommend using iCloud Drive as a backup for projects you have created with iCloud Drive enabled.
- In the <img src="imgs/icons/ui_icon_75.png" width="18"> **project folder**, press the <img src="imgs/icons/ui_icon_80.png" width="18"> **New Project** button to create an empty project and transition to Studio.
- In the <img src="imgs/icons/ui_icon_77.png" width="18"> **import folder**, press the <img src="imgs/icons/ui_icon_77.png" width="18"> **Import** button to import x8studio project files from outside of this application.

---

## Studio_Common_UI

Here you can create a game using various editors and Debug mode.

![](imgs/manual/x8_doc_studio_desc.png "Studio Common")

### UI around the top and bottom bars
The UI around the top and bottom bars is the same for all editors.

- **Hint** show hints about the UI you're touching, temporary notifications, etc.
- The **Status** displays information related to the current status.
- **Project name** shows the name of the project that is currently being edited.
- The **Project Status** shows the status of the project (`-` no change, `*` with change).
- **Menus**
    - <img src="imgs/icons/ui_icon_00.png" width="18"> **x8 Menu**
        - Information on this application and links to support pages, etc.
    - <img src="imgs/icons/ui_icon_01.png" width="18"> **File Menu**
        - Project save, reference load, and close operations
    - <img src="imgs/icons/ui_icon_02.png" width="18"> **Edit Menu**
        - Input settings, copy and paste for the current editor, etc.
- **Editor**
    - <img src="imgs/icons/ui_icon_04.png" width="18"> **Code Editor**
    - <img src="imgs/icons/ui_icon_05.png" width="18"> **Gfx Editor**
    - <img src="imgs/icons/ui_icon_06.png" width="18"> **Map Editor**
    - <img src="imgs/icons/ui_icon_07.png" width="18"> **Sfx Editor**
    - <img src="imgs/icons/ui_icon_59.png" width="18"> **Debug Mode**
- Run mode**
    - <img src="imgs/icons/ui_icon_60.png" width="18"> **Run Mode**.
- **Undo/Redo**
    - <img src="imgs/icons/ui_icon_14.png" width="18"> **Undo** (undo)
    - <img src="imgs/icons/ui_icon_15.png" width="18"> **Redo** (redo)
- **Project Switch**
    - <img src="imgs/icons/ui_icon_63.png" width="18"> **Project Switch**
        - Switch between an edit project and a reference project.

### <img src="imgs/icons/ui_icon_63.png" width="30">Project_Switch
The **Project Switch** toggles between **Edit Project** and **Reference Project**.

- **Edit Project** is a project opened in the Home screen that is currently under development.
- **Reference Project** is a project that can be used to reference other projects, and can be edited and executed, but **cannot be saved**. There will always be one, and you can read other projects with **Reference Load** in the file menu.
- You can also copy and paste between the edit project and the reference project.
- You can see which project is currently displayed in the background of the editor.
    - If the background is **bright**, it is a **edit project**.
    - If the background is **dark**, it is a **reference project**.

![](imgs/manual/x8_doc_ref_proj.gif "Project Switch")

### <img src="imgs/icons/ui_icon_28.png" width="30">Touch Cursor
The **touch cursor** is used to perform detailed operations that are difficult to perform with a finger.

- You can move the touch cursor by dragging any part of it except the buttons.
- When you press the button, you can touch the position of the pointer of the touch cursor (the point above the touch cursor).
- If you hold down a button and move it, you can drag it at the position of the pointer of the touch cursor.

![](imgs/manual/x8_doc_touch_cursor.gif "Touch Cursor")

### <img src="imgs/icons/ui_icon_62.png" width="30">Screen Keyboard
**On-screen keyboard** is used for text input without using an external keyboard. The `Shift`, `Ctrl`, and `Alt` modifier toggles have a locking toggle to the left of them, and if not locked, modifiers are turned off after one character input. Press the `Mode` key to switch the input mode from **normal characters** to **special characters** to **katakana**. (The kana is only for JP keyboard.)

![](imgs/manual/x8_doc_screen_keyboard.gif "Screen Keyboard")

---

## Code_Editor

- You can program in **Lua language (Lua 5.3)**. x8's own API and Lua's standard libraries (except for some) are available.
- Please note that **only ASCII code (half-width alphanumeric symbols) and some characters (kana and special symbols)** are supported by the Code Editor.

![](imgs/manual/x8_doc_code_desc.png "Code Editor")

- The program code is displayed in the **Code area**. This is where the programming comes in.
- **Code selection**
    - <img src="imgs/icons/ui_icon_63.png" width="18"> **Switching the Code** switches the code to be edited with the code you have just edited.
    - <img src="imgs/icons/ui_icon_04.png" width="18"> **Code Selection** selects the code to be edited.
- **Editing tools**
    - <img src="imgs/icons/ui_icon_02.png" width="18"> **Edit Menu** is the menu for editing functions such as copy and paste.
    - <img src="imgs/icons/ui_icon_90.png" width="18"> **Movement Menu** is a menu for moving the cursor, such as moving the page or moving to the top of the line.
    - <img src="imgs/icons/ui_icon_91.png" width="18"> **Search Menu** is the menu for the search function.
    - <img src="imgs/icons/ui_icon_92.png" width="18"> **Input Mode Menu** is a menu to switch the input mode.
- <img src="imgs/icons/ui_icon_02.png" width="18"> **Edit Menu**
    - **Copy** copies the currently selected code. Please note that this is a code by code copy, **not a string by string**.
    - Replace the currently selected code in **Paste** with the one you have already copied. If there is no pre-copied code, it doesn't do anything.

### Lua_Materials

- Lua's official website is [here](https://www.lua.org/home.html).
- The official **Lua 5.3 Reference Manual** is [here](https://www.lua.org/manual/5.3/).
- **The Japanese translation of the Lua 5.3 Reference Manual (unofficial)** is [here](http://milkpot.sakura.ne.jp/lua/lua53_manual_ja.html). (Thank you for linking to it!)

### Lua Standard Library

The following **Lua Standard Libraries** are available for x8studio.

|Is it available?|Library|Table|Unavailable Functions|
|:--:|:---|:---|:---|
|**YES**|basic library||collectgarbage, dofile, loadfile, load, print|
|**YES**|coroutine library|`coroutine`|-|
|NO|package library|`package`|-|
|**YES**|string manipulation|`string`|dump, pack, packsize, unpack|
|NO|basic UTF-8 support|`utf8`|-|
|**YES**|table manipulation|`table`|-|
|**YES**|mathematical functions|`math`|-|
|NO|input and output|`io` `file`|-|
|NO|operating system facilities|`os`|-|
|NO|debug facilities|`debug`|-|

### Code Completion and Code Snippets
When you type a character in the code area, a completion pop-up will open if there is a potential completion. You can also open the word with `Alt+Tab` (if there is a candidate completion) by hovering the cursor over the end of the word.

![](imgs/manual/x8_doc_completion_popup.gif "Completion Popup")

- Keep typing to narrow down the list.
- You can select a candidate with `Tab`,`Shift+Tab` and confirm it with `Enter`.
- Pressing `Ctrl+Tab` or `Esc` or moving the cursor will close the pop-up.
- During completion, you can use `Alt+Tab` to enter a code snippet corresponding to the completion candidate.

---

## Gfx_Editor

You can create image data to be used for sprites and maps.

![](imgs/manual/x8_doc_gfx_desc.png "Gfx Editor")

- In **Editing view**, the area selected in the Gfx view will be edited.
- In **Gfx view**, select the Gfx area to be edited.
- The **Stamp view** shows the captured stamp data.
    - <img src="imgs/icons/ui_icon_31.png" width="18"> toggles the setting of `color:0` for stamp data.
- The **Color palette** selects the color referenced by the drawing tool.
    - <img src="imgs/icons/ui_icon_97.png" width="18"> toggles the setting of the drawing tool **Toggle Mode**. In **Toggle Mode**, two colors can be selected. If the starting color is not either color, the color with the mark in the upper left is set, and if the starting color is either color, the other color is set. It does not affect drawing with stamps.
- **Drawing tools**
    - <img src="imgs/icons/ui_icon_33.png" width="18"> Drawing with a pen (touch and select, release to confirm)
        - <img src="imgs/icons/ui_icon_33.png" width="18"> Pixel Pen
        - <img src="imgs/icons/ui_icon_34.png" width="18"> square pen
        - <img src="imgs/icons/ui_icon_35.png" width="18"> Round pen
    - <img src="imgs/icons/ui_icon_40.png" width="18"> Draw the stamp data.
    - <img src="imgs/icons/ui_icon_64.png" width="18"> Capture the stamp data
    - <img src="imgs/icons/ui_icon_02.png" width="18">Editing chip attributes
    - <img src="imgs/icons/ui_icon_32.png" width="18"> Select an area in the edit view.
    - <img src="imgs/icons/ui_icon_67.png" width="18"> Choose the effect for the selected area
        - <img src="imgs/icons/ui_icon_67.png" width="18"> Allows you to edit regardless of the selected area.
        - <img src="imgs/icons/ui_icon_65.png" width="18"> Allows you to edit only the inside of the selected area.
        - <img src="imgs/icons/ui_icon_66.png" width="18"> Allows you to edit only outside of the selection area.
    - <img src="imgs/icons/ui_icon_68.png" width="18"> Display the grid.
- **Gfx Selection Tool**
    - <img src="imgs/icons/ui_icon_38.png" width="18"> Fix the shape and size of the Gfx selection area to be edited.
    - <img src="imgs/icons/ui_icon_68.png" width="18"> Display the grid.
- <img src="imgs/icons/ui_icon_02.png" width="18"> **Edit Menu**
    - Copy the Gfx data of the currently selected Gfx area with **Copy**.
    - Paste the copied Gfx data to the currently selected Gfx area with **Paste**. If there is no pre-copied Gfx data, it does nothing.

![](imgs/manual/x8_doc_gfx_attr_desc.png "Gfx Editor")

- <img src="imgs/icons/ui_icon_02.png" width="18"> **Chip attribute edit**
    - 1 byte (8bit) attribute data corresponding to chip (8x8) is edited.
    - The eight color palettes correspond to the bit positions of the attribute data to be edited.
    - You can turn on the corresponding bit by painting in the edit view.
- <img src="imgs/icons/ui_icon_02.png" width="18"> **Edit Menu**
    - Copy the attribute data of the currently selected attribute area with **Copy**.
    - Pastes the copied attribute data to the currently selected attribute area with **Paste**. If there is no copied attribute data, it does nothing.

---

## Map_Editor

Image data created with the Gfx editor can be lined up as chips to create larger image data.

![](imgs/manual/x8_doc_map_desc.png "Map Editor")

- In **Editing view**, you can edit the area selected in the Map Selection view.
- In **Gfx view**, select the tip rectangle to be set in the edit view.
- **Chip number: 0** will not be drawn in the Map Editor or in the actual map drawing (no chip). As a sprite, it is drawn without distinguishing it from other areas.
- The **Stamp view** shows the captured stamp data.
- In **Map selection view**, you can select the map area to be edited by touch.
- **Map cursor keys** manipulate the selection rectangle of the map selection view.
    - <img src="imgs/icons/ui_icon_18.png" width="18"> <img src="imgs/icons/ui_icon_19.png" width="18"> <img src="imgs/icons/ui_icon_16.png" width="18"> <img src="imgs/icons/ui_icon_17.png" width="18"> Move the selection area.
    - <img src="imgs/icons/ui_icon_93.png" width="18"> Reset the selection area to the top left.
    - <img src="imgs/icons/ui_icon_94.png" width="18"> Fix the top left of the current selection area. You can change the size of the area by moving the cursor while it is fixed.
- **Placement tools**
    - <img src="imgs/icons/ui_icon_05.png" width="18"> Place the selected chip in the Gfx view
    - <img src="imgs/icons/ui_icon_40.png" width="18"> Placing the stamp data
    - <img src="imgs/icons/ui_icon_64.png" width="18"> Capture the stamp data
    - <img src="imgs/icons/ui_icon_32.png" width="18"> Select an area in the edit view.
    - <img src="imgs/icons/ui_icon_67.png" width="18"> Choose the effect for the selected area
        - <img src="imgs/icons/ui_icon_67.png" width="18"> Allows you to edit regardless of the selected area.
        - <img src="imgs/icons/ui_icon_65.png" width="18"> Allows you to edit only the inside of the selected area.
        - <img src="imgs/icons/ui_icon_66.png" width="18"> Allows you to edit only outside of the selection area.
    - <img src="imgs/icons/ui_icon_68.png" width="18"> Display the grid.
- **Gfx Selection Tool**
    - <img src="imgs/icons/ui_icon_97.png" width="18"> toggles the placement tool's **Toggle Mode** setting. In **Toggle Mode**, if the chip at the start position is different from the chip to be placed, it is set to **0**, if the chip at the start position is the same as the chip to be placed. If there is more than one chip to be placed, the top left is referenced. It does not affect the placement with stamps.
    - <img src="imgs/icons/ui_icon_38.png" width="18"> Fix the shape and size of the Gfx selection area to be edited.
    - <img src="imgs/icons/ui_icon_68.png" width="18"> Display the grid.
- <img src="imgs/icons/ui_icon_02.png" width="18"> **Edit Menu**
    - Copy the map data of the currently selected map area in **Copy**.
    - Pastes the copied map data to the currently selected map area with **Paste**. If there is no pre-copied Map data, it does nothing.
    - Copying and pasting in the Map Editor is **for Map data only**. Please note that **Gfx data will not be changed** by this operation if you are running across projects.

---

## Sfx_Editor

It is possible to create short sound data such as sound effects.

![](imgs/manual/x8_doc_sfx_desc.png "Sfx Editor")

- The **editing view** allows you to edit the 16 notes that make up Sfx with a touch.
    - In the display of **notes**, the wavy line and associated numbers represent the waveform and pitch offset, and the green block represents the volume value.
- **Edit tool**.
    - <img src="imgs/icons/ui_icon_07.png" width="18"> Select the Sfx you want to edit.
    - <img src="imgs/icons/ui_icon_52.png" width="18"> Enable/disable Sfx.
    - <img src="imgs/icons/ui_icon_53.png" width="18"> Copy and set from other Sfx.
    - <img src="imgs/icons/ui_icon_54.png" width="18"> Set the playback speed. The smaller the number, the faster it will be.
    - <img src="imgs/icons/ui_icon_42.png" width="18"> Enable/disable the loop. When enabled, you can drag <img src="imgs/icons/ui_icon_42.png" width="18"> under the edit view to set the loop position.
    - <img src="imgs/icons/ui_icon_49.png" width="18"> You can set the pitch by touching the note. You can also set the pitch with the adjustment keys.
    - <img src="imgs/icons/ui_icon_50.png" width="18"> You can set the pitch of the selected note by touch on the keyboard. The selected position will automatically move to the right. You can also set the pitch with the adjustment keys.
    - <img src="imgs/icons/ui_icon_51.png" width="18"> You can set the volume of a note by touching it. You can also set the volume with the adjustment keys.
    - <img src="imgs/icons/ui_gfx_icon_08.png" width="18"> You can set the waveform of the note by touching it. (Select with touch, release and fix)
        - <img src="imgs/icons/ui_gfx_icon_08.png" width="18"> Sine Wave
        - <img src="imgs/icons/ui_gfx_icon_09.png" width="18"> Square Wave(1:1)
        - <img src="imgs/icons/ui_gfx_icon_10.png" width="18"> square Wave(1:3)
        - <img src="imgs/icons/ui_gfx_icon_11.png" width="18"> Square Wave(1:7)
        - <img src="imgs/icons/ui_gfx_icon_12.png" width="18"> Sawtooth Wave (1:7)
        - <img src="imgs/icons/ui_gfx_icon_13.png" width="18"> Triangular Wave
        - <img src="imgs/icons/ui_gfx_icon_14.png" width="18"> White Noise
        - <img src="imgs/icons/ui_gfx_icon_15.png" width="18"> Noise (with pitch)
    - <img src="imgs/icons/ui_icon_10.png" width="18"> You can specify the pitch offset on the keyboard to play a trial tune.
- **Playback tool**
    - <img src="imgs/icons/ui_icon_11.png" width="18"> Play Sfx.
    - <img src="imgs/icons/ui_icon_39.png" width="18"> Stop playing Sfx.
- **Keyboards**.
    - The yellow frame represents the `pitch offset:0`.
- <img src="imgs/icons/ui_icon_02.png" width="18"> **Edit Menu**
    - **Copy** copies the currently selected Sfx data.
    - Replace the currently selected Sfx data in **Paste** with the previously copied Sfx data. If you don't have the copied Sfx data, you don't do anything.

---

## Debug_Mode

In this mode, you can run and test a game under development.

![](imgs/manual/x8_doc_debug_desc.png "Debug Mode")

- **Debug Tools**
    - <img src="imgs/icons/ui_icon_59.png" width="18"> Starts/stops the debugging process.
    - <img src="imgs/icons/ui_icon_12.png" width="18"> Pause/unpause the debugging execution.
    - <img src="imgs/icons/ui_icon_13.png" width="18"> Reset the virtual machine.
    - <img src="imgs/icons/ui_icon_70.png" width="18"> Toggles between showing and hiding the log view.
    - <img src="imgs/icons/ui_icon_71.png" width="18"> Clear the log.
    - <img src="imgs/icons/ui_icon_69.png" width="18"> Take a screenshot of the project information on the Home screen.
- **Log View**
    - <img src="imgs/icons/ui_icon_70.png" width="18"> When Log View is ON, the first line of each log will be displayed on the game screen. When you select a log by touch, the log details view will show the details of that log.
    - Touch the **Log Detail View** to open the **Log Detail Window**.
- **Log Detail Window**
    - When the error part is displayed in the log, it is possible to move to the error position in the Code editor by pushing the `Go to Error` button.
- **Volume**
    - You can change the volume of the virtual machine. If the virtual machine is paused for any reason, it is automatically set to 0.
- **Gamepad Buttons**
    - These are the buttons of the gamepad of the virtual machine. The red number indicates the bit position of the button information to be retrieved by the API.

---

## Run_Mode

This is the mode of playing the completed game.

![](imgs/manual/x8_doc_run_desc.png "Run Mode")

- Pressing the **menu button** will open a menu where you can perform a **restart** or **quit** of the virtual machine.

---

## Screen_Keyboard

The app has its own built-in screen keyboard.

- You can select a screen keyboard from the following in **Input Settings** in <img src="imgs/icons/ui_icon_02.png" width="18"> **Edit Menu**.
    - **QWERTY JP** makes it a Japanese keyboard. You can enter **kana**.
    - **QWERTY US** for the English keyboard. You cannot type **kana**.

---

## External_Keyboard

External keyboard input is supported.

- For **external keyboards**, English (US) and Japanese (JIS) keyboards in QWERTY arrangement are supported.
- Since the connected keyboard type is not automatically determined, it is necessary to set the connected keyboard type in **Edit Menu** → **Input Settings** → **External Keyboard**.
    - **QWERTY US** recognizes it as an English (US) keyboard with a QWERTY array. Kana cannot be entered.
    - **QWERTY JP** recognizes **some third party Japanese (JIS) keyboards**. You can enter kana.
    - It is recognized as a Japanese (JIS) keyboard by **Apple JP**. You can enter kana.
- If it's a genuine Apple keyboard, set it to **QWERTY US** or **Apple JP**.
- The `caps lock` key does not work as a **CapsLock**. It works as `control` key if the input can be obtained by the application side.

### External Keyboard Settings and Operation Check Status

|Status|Model|Arrangement|Setting|
|:--:|:---|:--:|:---|
|OK|Apple Wireless Keyboard 2011 English(US)|US|**QWERTY US**|
|OK|Magic Keyboard Japanese(JIS)|JIS|**Apple JP**|
|OK|Anker Ultra-Slim Bluetooth Keyboard (A7726)|US|**QWERTY US**|
|OK|Logicool K380 Multi-Device Bluetooth Keyboard (Japanese layout)|JIS|**QWERTY US** or **QWERTY JP** `*`|
|Unchecked|Other English(US) keyboards|US|**QWERTY US**|
|Unchecked|Other Apple Japanese(JIS) keyboards|JIS|**Apple JP**|
|Unchecked|Other Third Party Keyboards|JIS|**QWERTY US**|

- Please note that third party Japanese (JIS) keyboards are basically set to **QWERTY US**.
- `*` Some third party Japanese (JIS) keyboards can be set to **QWERTY JS**, so that you can input keys as marked. However, for the following, use a different key instead.
    - Type `\` (backslash) with the `kanji` key.
    - Type `_` (underscore) with `Shift+Kanji`.
    - Type `|` (pipe) with `Shift+0`.
    - Enter a half-width kana character `ﾛ` with the `Kanji` key.
    - Enter a half-width kana character `ｰ` with `Shift+Kanji`.
- `*` The following models have been confirmed to work with **QWERTY JS** setting among the Japanese (JIS) keyboards made by a third party.
    - Logicool K380 Multi-Device Bluetooth Keyboard (Japanese Array)


---

## Shortcut_Keys

Both the screen keyboard and the external keyboard support the same shortcut keys.

- The meaning of the key symbol
    - `#` means to press the Shift key at the same time.
    - `^` means to press the Ctrl key at the same time.
    - `&` means to press the Alt key at the same time.

### Code Editor

- **You can move while selecting a key or shortcut while holding down the Shift key.**

|Key|Function|
|:--:|:---|
|`&Tab`|indent a line|
|`#Tab`|outdent a line|
|`^Tab`|Open the completion popup if possible at the cursor position|
|`^Enter`|Insert line at the top|
|`#^Enter`|Insert line underneath|
|`^↑`|PageUp|
|`^↓`|PageDown|
|`^←`|To the previous word boundary|
|`^→`|To the next word boundary|
|`&↑`|Go to top of text|
|`&↓`|to the end of the text|
|`&←`|to the top of the line|
|`&→`| end of line|
|`^A`|All selections|
|`^C`|Copy|
|`^D`|delete (not add to copy buffer)|
|`^F`|Open the forward search pop-up|
|`#^F`|Open the backward search pop-up|
|`^&G`|Glyph input mode|
|`^K`|Delete from the cursor to the end of the line|
|`^&K`|Katakana input mode|
|`^L`|Scroll so that the cursor is at the center of the screen|
|`^&N`|Normal Input Mode|
|`^V`|Paste|
|`#^V`|Paste at the beginning of the line|
|`^X`|Cut (add to copy buffer)|
|`^Z`|Ando|
|`#^Z`|Redo|

### Code Editor Completion Popup

|Key|Function|
|:--:|:---|
|`Enter`|Conclude and close|
|`Esc`|Cancel and close|
|`Tab`|Go to the next candidate|
|`#Tab`|To the previous candidate|
|`&Tab`|Switch between completion mode and snippet mode|
|`^Tab`|Cancel and close|

### Code Editor Search Window

|Key|Function|
|:--:|:---|
|`^F`|Go to the next forward search result|
|`#^F`|Go to the next backward search result|

