# Reference Manual

## In the beginning

### Color Number

In x8, colors are represented by a color number from 0 to 15. Also, a set of 16 color numbers is called a palette.

### Drawing State

The x8 has the following drawing states that affect video-related instructions

- **Drawing Coordinate Offset**
    - All drawing instructions draw the position by this offset.
- **Drawing Clip Rectangle**
    - All drawing instructions reflect the result of the drawing only within this rectangle.
- **Drawing Palette**
    - All drawing instructions replace the color to be drawn with this palette.
- **Blank Color Information**
    - All drawing instructions do not draw colors that are left out of this information.
- **Default Drawing Color**
    - If a color is not specified in the drawing instruction, this color will be used.
- **Font Scale**
    - The font drawing instruction draws to reflect this scale.
- **Font Spacing**
    - The font drawing instruction draws each character with this interval between them.
- **Screen Palette**
    - The screen image of the result of the drawing will be displayed, with the colors eventually replaced by this palette.

### Screen Image

All drawing instructions draw in an area called the screen image. The screen image of the drawing result is displayed on the display after replacing the colors in the screen palette.

### Chip, Chip Number, and Chip Attributes

- A chip is a unit of image in which the Gfx region is divided by 8x8 pixels.
- The chip number is the number (0-255) shaken to the chip in order from the top left of the Gfx area (in order of address).
- The chip attribute is the 1 byte of information corresponding to the chip and can be edited bit by bit in the Gfx editor.

### Sprite.

In the X8, a direct drawing of the chip is called a sprite.

### Map

In x8, a drawing of a group of chips arranged in a map area is called a map.

### Fonts

The x8 comes with several built-in fonts and their APIs. Strings including katakana and special characters should be converted to 8bit code with `x8.enc()` before they are handled by API etc.

```
x8.fnt(x8.enc("ｶﾀｶﾅ ﾄｶ ←→↑↓ ﾄｶ ｶﾞ ﾊｲｯﾃｲﾙ ﾓｼﾞﾚﾂ ﾊ enc()ﾃﾞ 8bit ｺｰﾄﾞ ﾆ ﾍﾝｶﾝ ｽﾍﾞｼ"))
str_len = string.len(x8.enc("ｶﾀｶﾅ ﾄｶ ⒶⒷⒸⒹ ﾄｶ ｱｯﾃﾓ stringﾗｲﾌﾞﾗﾘ ﾊ ｿﾉﾏﾏ ﾂｶｴﾏｽ"))
```

### Thread

In x8 it refers to Lua's threads (cooperative multithreading), which are unrelated to general OS threads. Calling `x8.wait()` in each thread returns the processing to the system, and the next thread processing or frame update processing is done.

### Audio Handle

The audio-related playback API returns a handle for a unit of playback processing called an audio handle. This handle can be used to stop each playback process unit.

### Audio Channels

The x8 can emit sound from up to four channels at the same time. The system automatically distributes the channels in order to produce as much sound as possible.

---

## Video Related

`x8.cls([col])`

- Clear the screen with the color `col`.
- It is affected by the drawing palette, but it is not affected by the drawing offset, drawing clip, or extract color information.
- default value of argument : `col=0`.

`x8.clip([x[,y[,w[,h]]]])`

- Set the position `x,y` and the size `w,h` of the drawing clip rectangle. Calling it without a trigger resets it.
- All drawing instructions reflect the result of the drawing only within this rectangle.
- Default argument value : `x=0`,`y=0`,`w=128`,`h=128`.

`x8.camera([x[,y]])`

- Set the offset of the drawing coordinate to `x,y`. Calling it without a trigger resets it.
- All drawing instructions draw the position by this offset.
- Default value of argument : `x=0`,`y=0`.

`x8.color([col])`

- Set the default drawing color to `col`.
- If a color is not specified in the drawing instruction, this color will be used.
- Default value of argument : `col=7`.

`x8.drwpal([col0[,col1]])`

- Set the color `col0` to be replaced by `col1` in the drawing palette. Calling it without a trigger resets it.
- All drawing instructions replace the color to be drawn with this palette.
- Default value of argument : `col0=0`,`col1=col1`.

`x8.scrpal([col0[,col1]])`

- Set the color `col0` to be replaced by `col1` in the screen palette. Calling it without a trigger resets it.
- The screen image of the result of the drawing will be displayed, with the colors eventually replaced by this palette.
- Default value of argument : `col0=0`,`col1=col1`.

`x8.colorkey([col[,trs]])`

- Set the `trs`(boolean) value to suppress the color `col` or not. Calling it without a trigger resets it.
- All drawing instructions do not draw colors that are left out of this information.
- Default value of argument : `col=0`,`trs=true`.

`x8.spr(n,x,y[,w[,h,[,flpx[,flpy]]]]`

- Draw the `n` chip at position `x,y`. Size `w,h` is in chips. You can use `flpx` to flip left and right, and `flpy` to flip up and down.
- It is affected by the drawing state.
- Default argument value : `w=1`,`h=1`,`flpx=false`,`flpy=false`.

`x8.gfx(gx,gy,gw,gh,x,y[,w[,h[,flpx[,flpy]]])`

- Draw a rectangle of size `gx,gy` and size `gw,gh` at the position `x,y` of the screen in Gfx. You can specify the drawing size with `w,h`. All are in pixels. You can use `flpx` to flip left and right, and `flpy` to flip up and down.
- It is affected by the drawing state.
- Default argument value : `w=gw`,`h=gh`,`flpx=false`,`flpy=false`.

`x8.map(mapx,mapy,x,y[,mapw[,maph]])`

- Draws a chip at the position `mapx,mapy` in a map at the position `x,y` of the screen. size of the map can be specified by `mapw,maph` in chips.
- It is affected by the drawing state.
- Default value of argument : `mapw=1`,`maph=1`.

`x8.mapget(mapx,mapy)`

- Gets and returns the chip number of a position `mapx,mapy` in a map.

`x8.mapset(mapx,mapy,val)`

- Set the chip number of the position `mapx,mapy` in the map to `val`.

`x8.atget(n[,bit])`

- Get and return the chip attribute of the `n` number. If it is `bit`, the value of the bit is returned with boolan, otherwise, the chip attribute is returned as is.

`x8.atrset(n[,bit][,val])`

- Set the chip attribute of the `n` number to `val`. If there is a `bit`, set `val` as a boolean value, otherwise set `val` as a chip attribute value.
- Default value of argument : `val=false` if `bit` is given.

`x8.scrget(x,y)`

- Gets and returns the color of a pixel at the position `x,y` of the screen.

`x8.scrset(x,y,col)`

- Set the color `col` to the pixels of the screen position `x,y`.
- Since it is not a drawing instruction, it is not affected by the drawing state.

`x8.gfxget(gx,gy)`

- Get and return the color of a pixel at a position `x,y` in Gfx.

`x8.gfxset(gx,gy,col)`

- Set the color `col` to the pixels at position `x,y` in Gfx.
- Since it is not a drawing instruction, it is not affected by the drawing state.

`x8.pixel(x,y[,col])`

- Draw a pixel at the position `x,y` of the screen. You can specify a color with `col`.
- It is affected by the drawing state.
- default value of the argument: `col=default drawing color`.

`x8.line(x0,y0,x1,y1[,col])`

- Draws a line with a starting point `x0,y0` and an ending point `x1,y1` on the screen. You can specify a color with `col`.
- It is affected by the drawing state.
- default value of the argument: `col=default drawing color`.

`x8.rectbdr(x0,y0,x1,y1[,col])`

- Draw a rectangle of `x0,y0` at the top left and `x1,y1` at the bottom right. You can specify a color with `col`.
- It is affected by the drawing state.
- default value of the argument: `col=default drawing color`.

`x8.rect(x0,y0,x1,y1[,col])`

- Draws a filled rectangle with `x0,y0` top left and `x1,y1` bottom right on the screen. You can specify a color with `col`.
- It is affected by the drawing state.
- default value of the argument: `col=default drawing color`.

`x8.circbdr(x,y,r[,col])`

- Draw a circle with a center point `x,y` radius `r` on the screen. You can specify a color with `col`.
- It is affected by the drawing state.
- default value of the argument: `col=default drawing color`.

`x8.circ(x,y,r[,col])`

- Draws a filled circle with a center point `x,y` radius `r` on the screen. You can specify a color with `col`.
- It is affected by the drawing state.
- default value of the argument: `col=default drawing color`.

---

## Audio related

`x8.sfx(n[,spd[,pitch[,start[,len]]])`

- Play the `n` number Sfx and return the audio handle. You can specify the following to play.
    - `spd`: Magnification of the playback speed (real number).
    - `pitch`: Offset for pitch (integer).
    - `start`: Start position of playback (integer).
    - `len`: number of replayed notes (integer)
- Default argument value: `spd=1.0`,`pitch=0`,`start=0`,`len=length of Sfx`.

`x8.hdlstop(hdl)`

- Stops the sound being played as specified by the audio handle `hdl`.

`x8.sfxstop()`

- Stops all Sfx during playback.

---

## Font-related

`x8.fnt(str,x,y[,col])`

- Draws a string `str` at the position `x,y` of the screen. You can specify a color with `col`.
- It is affected by the drawing state.
- default value of the argument: `col=default drawing color`.

`x8.fntscale([sclx[,scly]])`

- Sets the scale value reflected when the font is drawn.
- Default argument: `sclx=1.0`,`scly=1.0`

`x8.fntspace([spcx[,spcy]])`

- Sets the character spacing that is reflected when the font is drawn.
- Default value of argument : `spcx=0`,`spcy=0`.

`x8.fntmeas(str) -> size_x,size_y`

- Returns the size of the string `str` when it is drawn, taking into account the drawing state and each character size, as an integer `w,h` in pixels.

`x8.enc(str)`

- All katakana and special character codes in the string `str` are converted to 8-bit codes and the resulting string is returned.

---

## Input-related

`x8.btnprs([bit])`

- Returns the information on pressing the button in the current frame. If it is `bit`, the bit value is returned as a boolean, otherwise the bit mask of all buttons is returned as an integer.

`x8.btntrg([bit])`

- Returns the trigger information of the button (whether it changed from OFF to ON) in the current frame. If it is `bit`, the bit value is returned as a boolean, otherwise the bit mask of all buttons is returned as an integer.

---

## Others

`x8.log(str)`

- Output the string `str` to the log.

`x8.wait([frms])`

- Waits for `frms` frames with this function. Calling this returns processing to the system and the frame progresses. If you don't call this with more than `1` arguments in any thread, the program will stop with a timeout error after a certain amount of time.
- default value of argument : `frms=1`.

`x8.clock()`

- Returns the elapsed time in seconds since the program execution started.
