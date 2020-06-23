# Lua 5.3 チートシート （工事中）

    ・動的型付け
    ・数値
        ・整数と少数に区別なし
    ・文字列
        ・'〜' もしくは "〜"、エスケープは '¥'
        ・[[〜]] エスケープされない（ソース中で改行しながら記述できるね）
    ・関数は第一級オブジェクト
    ・テーブル
        x = { a=3, b=5 }
    ・bool
        true false
    ※define や enum 的なものはないので通常全て変数で行う
    ・変数とnil
        ・変数にnilを代入すると破棄される
        ・未定義の変数を参照するとnilが返る
    ・スレッド
        ・コルーチン
    ・ユーザーデータ
        ・C言語側のデータ構造をLua側で扱う
        ・Luaから直接は操作できない
    ・ライトユーザーデータ
        ・C言語側のポインタを表す
        ・直接操作は出来ないが一致のみチェック出来る
            ==
            ~=
    ・変数のスコープ
        ・デフォルトはグローバル
        ・local を付けるとローカルになる
            ・ブロック内のみ
            ・定義以後のみ
        ※グローバル変数は _G という名前のテーブルとして参照可能
    ・制御構文
        ・for
            for i=a, b, c do 〜 end             … Lua（cを省略すると1）
            for(int i=a; i<=b; i+=c){〜}    … C
        ・while
            while condition do 〜 end
        ・repeat
            repeat 〜 until condition
        ※break 文はあるが continue 文はない
        ※break 及び return はブロックの最後でしか実行できない、やりたければ…
            do break end
        　とかやるらい…
        ・if
            if condition then 〜 elseif 〜 else 〜 end
    ・演算子（Cと違うもの）
        and or not      論理演算
        ~=              不一致
        #               テーブルの配列部のサイズ（c=#t とか）
        ..              文字列の連結
    ・コメント
        --              行末までコメント
        --[[〜]]        ブロックコメント
        --[==[〜]==]    ブロックコメントを含むブロックコメント
                        = の数は前後で一致していればいくつでもいい
    ・テーブル
        ・連想配列
        ・キーが数値の場合は配列と同じ
        ・配列の添字は 1 始まり（0以下も指定出来てしまうらしいが…）
        ・配列として使う
            t = {}
            t[1] = "hoge"
            t[2] = "fuga"
            t[3] = "piyo"
            ---- ↑と↓は同じ ----
            t = { "hoge", "fuga", "piyo" }
            ---- ↑と↓は同じ ----
            t = {}
            table.insert(t, "hoge")
            table.insert(t, "fuga")
            table.insert(t, "piyo")
            ---- アクセス ----
            print(t[1]..t[2]..t[3])
            ---- forでループその１ ----
            for i, v in ipairs(t) do
                print(i.." : "..v)
            end
            ---- forでループその２ ----
            for i, #t do
                print(i.." : "..t[i])
            end
        ※配列の途中にnilで穴を開けると動作は不定
        ・連想配列として使う
            t = {}
            t["name"] = "hoge"
            t["country"] = "fuga"
            ---- ↑と↓は同じ ----
            t = { ["name"] = "hoge", ["country"] = "fuga" }
            ---- ↑と↓は同じ（キーがアルファベット始まりの場合のみ可） ----
            t = { name = "hoge", country = "fuga" }
            ---- ↑と↓は同じ（キーがアルファベット始まりの場合のみ可） ----
            t = {}
            t.name = "hoge"
            t.country = "fuga"
            ---- アクセス ----
            print("name is "..t.name..", country is "..t.country)
            ---- forでループその１ ----
            for i, v in pairs(t) do
                print(i.." : "..v)
            end
        ※テーブルのキーと値にはnilを除く全ての値が指定可能（関数、テーブル..）
        ※テーブルのループ中にキーを追加するとダメー（削除は無問題）
    ・関数
        ・定義
            function 関数名(引数１, 引数２..)
                〜
            end
        ・引数の数が違っても無問題
            ・実引数    ≧ 仮引数   … 関数側では無視される
            ・実引数 ≦ 仮引数  … 足りない引数は nil が渡される
        ・可変長引数の受け取り
            function f(...)
                local t = {...}         -- テーブルに引数を配列として設定
                for i, v ipairs(t) do
                    print(i, ":", v)
                end
            end
        ※戻り値は複数返せる
            function f()
                return 100, 200, 300
            end
            ---- ↑↓呼び出し ----
            local a, b, c = f()
        ・定義方法あれこれ
            ・以下は同じ意味
                function f() 〜 end
                f = function() 〜 end
            ・以下は同じ意味
                local function f() 〜 end
                local f; f = function() 〜 end
            ・以下は同じ意味（クラス風）
                function t:f() 〜 end       … それ以外ならこっち
                function t.f(self) 〜 end   … クラス風呼び出すならこっち
            ※t:f()の形で呼び出すとselfにtが自動的に束縛される





