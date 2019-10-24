# APIリファレンス（x8ライブラリ）

## スレッド

### thrstart(f[,arg1,...])
- Start thread

### thrcancel(hdl)
- Destroy thread

### thrself()
- Get own thread

### thrprio(hdl[,prio])
- Set thread priority

### thralive(hdl)
- Check thread existence

---

## 入力

### btnprs([bit])
- Get button press

### btntrg([bit])
- Get button trigger

---

## ビデオ

### cls([col])
- Clear screen

### clip([x[,y[,w[,h]]]])
- Set draw clip

### camera([x[,y]])
- Set camera position

### color([col])
- Set default draw color

### drwpal([col0[,col1]])
- Set draw palette

### scrpal([col0[,col1]])
- Set screen palette

### colorkey([col[,trs]])
- Set color key

### spr(n,x,y[,w[,h,[,flpx[,flpy]]]])
- Draw sprite

### gfx(sprx,spry,sprw,sprh,x,y[,w[,h[,flpx[,flpy]]]])
- Draw gfx

### map(mapx,mapy,x,y[,mapw[,maph]])
- Draw map

### mapget(mapx,mapy)
- Get map chip id

### mapset(mapx,mapy,val)
- Set map chip id

### atrget(n[,bit])
- Get chip attribute

### atrset(n[,bit][,val])
- Set chip attribute

### scrget(x,y)
- Get screen pixel color

### scrset(x,y,col)
- Set screen pixel color

### gfxget(sprx,spry)
- Get gfx pixel color

### gfxset(sprx,spry,col)
- Set gfx pixel color

### pixel(x,y[,col])
- Draw pixel

### line(x0,y0,x1,y1[,col])
- Draw line

### rectbdr(x0,y0,x1,y1[,col])
- Draw rectangle border

### rect(x0,y0,x1,y1[,col])
- Draw rectangle filled

### circbdr(x,y,r[,col])
- Draw circle border

### circ(x,y,r[,col])
- Draw circle filled

---

## オーディオ

### sfx(n[,spd[,pitch[,start[,len]]]])
- Play sfx

### phr(n[,sp[,pitch[,start[,end]]]])
- Play phrase

### music(n[,spd[,pitch[,start[,end]]]])
- Play music

### hdlstop(hdl)
- Stop audio handle

### sfxstop()
- Stop all sfxs

### phrstop()
- Stop all phrases

### musicstop()
- Stop all music

### sfxch([chmask])
- Set channel for sfxs

### phrch([chmask])
- Set channel for phrases

### musicch([chmask])
- Set channel for music

---

## フォント

### fnt(str,x,y[,col])
- Draw font string

### fntscale([sclx[,scly]])
- Set font scale

### fntspace([spcx[,spcy]])
- Set font spacing

### fntmeas(str) -> size_x,size_y
- Get string drawing size

### enc(str)
- Encode to 8-bit characters

---

## その他

### log(str)
- Log output

### wait([frms])
- Wait for frames

### fps([fps])
- Get and set fps

### peek(addr)
- Read memory

### poke(addr,val)
- Write memory

### memcpy(dstaddr,srcaddr,len)
- Copy memory

### test([..])
- for develop(no effect)
