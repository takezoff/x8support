# 17. B.BREAKERの全て

前回までで**B.BREAKER**のプログラムに関する説明は全て完了しました。

あとちょっとだけ補足があります。

---

## B.BREAKERの完全なコード

以下がこれまで部分的に説明してきた**B.BREAKERの完全なコード**です。

```
--B.BREAKER
-- - Ver.1.1
-- - Block breaking game sample
--
--012345678901234567890123456789

SCREEN_W = 128
SCREEN_H = 128

BALL_SIZE = 4
BALL_SPEED = 1.5

RACKET_X = 32
RACKET_Y = 108
RACKET_W = 24
RACKET_H = 4
RACKET_SPEED = 2.0

INFO_Y = 118

block_lines = {
   { 3, 3, 3, 3, 3, 3, 3, 3 },
   { 2, 2, 2, 0, 0, 2, 2, 2 },
   { 2, 2, 2, 0, 0, 2, 2, 2 },
   { 1, 1, 1, 1, 1, 1, 1, 1 },
}

block_colors = { 10, 11, 3 }

top_score = 0

-- Main
function main()
   -- Initialize
   top_score = 0
   -- Game scenes
   while true do
      titleScene()
      playScene()
      gameoverScene()
   end
end

-- Title Scene
function titleScene()
   -- Clear screen
   x8.cls()
   -- Draw title
   x8.fntscale(3, 3)
   local title = "B.BREAKER"
   local tw = x8.fntmeas(title)
   x8.fnt(title, (128 - tw) * 0.5 + 1, 24 + 1, 11) -- Shadow
   x8.fnt(title, (128 - tw) * 0.5, 24, 7)
   -- Draw operating instructions
   x8.fntscale()
   local prst = "Press Ⓐ to start game"
   local prstw = x8.fntmeas(prst)
   x8.fnt(x8.enc("←→"), 16, 70, 6)
   x8.fnt(x8.enc("Ⓐ or Ⓑ"), 16, 80, 6)
   x8.fnt(".. Move Racket", 56, 70, 6)
   x8.fnt(".. Shoot, Quick", 56, 80, 6)
   -- Draw message
   x8.fnt(x8.enc(prst), (128 - prstw) * 0.5, INFO_Y, 7)
   -- Draw top score
   x8.fnt("TOP SCORE", 16, 100, 6)
   x8.fnt(".. "..top_score, 56, 100, 6)
   -- Wait
   while true do
      -- Press A to start game
      if x8.btntrg(4) then break end
      -- Next frame
      x8.wait()
   end
end

-- Game over scene
function gameoverScene()
   -- Clear screen
   x8.cls()
   -- Draw message
   x8.fntscale()
   local message = "GAME OVER"
   local w, h = x8.fntmeas(message)
   local y = 56
   x8.fnt(message, (128 - w) * 0.5, (128 - h) * 0.5, 8)
   -- Wait
   x8.wait(30 * 3)
end

-- Play scene
function playScene()
   local rem_balls = 3 -- Number of remaining balls
   local score = 0
   local racket = { x = RACKET_X, y = RACKET_Y, w = RACKET_W, h = RACKET_H }
   local ball = { x = 0, y = 0, w = BALL_SIZE, h = BALL_SIZE, vx = 0, vy = 0 }

   ::RESET::

   -- Create blocks
   local blocks = {}
   for i = 1, #block_lines do
      local line = block_lines[i]
      for j = 1, #line do
         local n = line[j]
         if n > 0 then
            -- Create a block
            blocks[#blocks + 1]
               = { x = (j - 1) * 16, y = (i - 1) * 8 + 16, w = 16, h = 8, n = n }
         end
      end
   end

   ::RETRY::

   local is_started = false

   -- Use one ball
   rem_balls = rem_balls - 1

   -- Wait to clear input
   x8.wait()

   -- The main loop in the game
   while true do

      -- Only valid blocks
      local new_blocks = {}
      for i = 1, #blocks do
         local block = blocks[i]
         if block.n > 0 then
            new_blocks[#new_blocks + 1] = block
         end
      end
      blocks = new_blocks

      -- If there are no blocks, it's clear
      if #blocks == 0 then break end

      -- Move the racket
      local racket_speed = RACKET_SPEED
      if x8.btnprs(4) or x8.btnprs(5) then -- Ⓐ or Ⓑ
         racket_speed = racket_speed * 3.0
      end
      if x8.btnprs(0) then -- ←
         racket.x = racket.x - racket_speed
      elseif x8.btnprs(1) then -- →
         racket.x = racket.x + racket_speed
      end
      if racket.x < 0 then
         racket.x = 0
      elseif (racket.x + racket.w) > SCREEN_W then
         racket.x = SCREEN_W - racket.w
      end

      -- Shoot the ball
      if not is_started and (x8.btntrg(4) or x8.btntrg(5)) then -- Ⓐ or Ⓑ
         is_started = true
         ball.vx = BALL_SPEED
         ball.vy = -BALL_SPEED
         x8.sfx(0)
      end
      
      -- Move the ball
      if is_started then
         ball.x = ball.x + ball.vx
         ball.y = ball.y + ball.vy
      else
         ball.x = racket.x + (racket.w * 0.5) - (ball.w * 0.5)
         ball.y = racket.y - ball.h
      end

      -- Bounce by the left wall
      if ball.x < 0 then
         ball.x = ball.x - (ball.x * 2)
         ball.vx = -ball.vx
         x8.sfx(0)
      -- Bounce by the right wall
      elseif (ball.x + ball.w) > SCREEN_W then
         ball.x = ball.x - (((ball.x + ball.w) - SCREEN_W) * 2)
         ball.vx = -ball.vx
         x8.sfx(0)
      end
      -- Bounce by the above wall
      if ball.y < 0 then
         ball.y = ball.y - (ball.y * 2)
         ball.vy = -ball.vy
         x8.sfx(0)
      end
      -- Check for mistake
      if ball.y > SCREEN_H then break end

      -- The ball and the racket hit check
      if (ball.vy > 0) and isHit(ball, racket) then
         local rx = (ball.x + (ball.w * 0.5)) - racket.x
         local rate = rx / racket.w
         if ((rate <= 0.25) and (ball.vx > 0))
         or ((rate >= 0.75) and (ball.vx < 0)) then
            ball.vx = -ball.vx
         end
         ball.vy = -ball.vy
         --
         x8.sfx(0)
      end

      -- The Ball and blocks hit check
      for i = 1, #blocks do
         local block = blocks[i]
         if (block.n > 0) and isHit(ball, block) then
            block.n = block.n - 1
            -- Update score
            score = score + 1
            --
            x8.sfx(1)
            local dx = 0
            -- The ball is boring into the block from the left
            if ball.vx > 0 then
               dx = (ball.x + ball.w) - block.x
            -- The ball is boring into the block from the right
            elseif ball.vx < 0 then
               dx = ball.x - (block.x + block.w)
            end
            local dy = 0
            -- The ball was bored into the block from above
            if ball.vy > 0 then
               dy = (ball.y + ball.h) - block.y
            -- The ball was wedged into the block from underneath
            elseif ball.vy < 0 then
               dy = ball.y - (block.y + block.h)
            end
            -- Bouncing the ball
            if math.abs(dx) < math.abs(dy) then
               ball.x = ball.x - (dx * 2)
               ball.vx = -ball.vx
            else
               ball.y = ball.y - (dy * 2)
               ball.vy = -ball.vy
            end
         end
      end

      -- Clear screen
      x8.cls()

      -- Draw blocks
      for i = 1, #blocks do
         local block = blocks[i]
         if block.n > 0 then
            x8.rect(block.x, block.y,
                    block.x + block.w - 1, block.y + block.h - 1,
                    block_colors[block.n])
         end
      end

      -- Draw racket
      x8.rect(racket.x, racket.y,
              racket.x + racket.w - 1, racket.y + racket.h - 1)

      -- Draw ball
      x8.rect(ball.x, ball.y,
              ball.x + ball.w - 1, ball.y + ball.h - 1)

      -- Draw information
      x8.fnt("SCORE:"..score, 4, INFO_Y, 6)
      x8.fnt("BALLS:"..rem_balls, 96, INFO_Y, 6)

      -- Next frame
      x8.wait()
   end

   -- Clear
   if #blocks == 0 then
      -- Draw message
      x8.fntscale()
      local message = "CLEAR!"
      local w, h = x8.fntmeas(message)
      x8.fnt(message, (128 - w) * 0.5, (128 - h) * 0.5, 10)
      -- Wait
      x8.wait(30 * 3)
      -- Reset
      goto RESET
   end

   -- Miss
   do
      -- Draw message
      x8.fntscale()
      local message = "MISS!"
      local w = x8.fntmeas(message)
      x8.fnt(message, (128 - w) * 0.5, 72, 8)
      -- Wait
      x8.wait(30 * 2)
   end

   -- Retry
   if rem_balls > 0 then goto RETRY end

   -- Update top score
   if score > top_score then top_score = score end
end

-- Hit check between objects
function isHit(a, b)
   return (a ~= b)
      and (a.x <= (b.x + b.w - 1)) and (b.x <= (a.x + a.w - 1))
      and (a.y <= (b.y + b.h - 1)) and (b.y <= (a.y + a.h - 1))
end

-- Start the game
main()
```

このコードは、既に説明した[プレイシーン以外の全て](tutorial_01_06.md)と[プレイシーンの全て](tutorial_01_16.md)を組み合わせただけです。プログラムについて説明が必要な部分はもうありません。

ここではプログラム以外でちょっとだけ補足します。

---

## プロジェクトコメント

コード先頭にあるこの部分を見てください。

```
--B.BREAKER
-- - Ver.1.1
-- - Block breaking game sample
--
--012345678901234567890123456789
```

このうち上から4行が**プロジェクトコメント**です。

**プロジェクトコメント**は**x8**独自の機能で、[Home画面のプロジェクト情報](../manual.md#Home画面)のところに表示されるテキストを設定できます。もちろん設定しなくても大丈夫です。

コードの先頭から**最大4行**の`--`コメントがプロジェクトコメントとして認識されます。**各行は`--`で始まらなければいけません。**

行頭が`--`でない行（改行だけの行も）が現れると、それ以降はプロジェクトコメントとして認識されません。

5行目の`--012345678901234567890123456789`はプロジェクトコメントではなく、文字数の目安としての単なるコメントです。プロジェクト情報として表示可能な**1行の文字数は最大30文字**です。

---

以上です。


![](../imgs/tutorial_01/x8_bbreaker.gif)
 
#### これで **B.BREAKERの全て** の説明はおしまいです。

#### そして **チュートリアル #01** も完了です！！お疲れさまでした！！

[このチュートリアルのトップへ](tutorial_01.md)
