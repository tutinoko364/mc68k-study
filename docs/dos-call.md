# Human68kシステムコール

標準出力=通常はプロンプト。リダイレクト可能。
標準入力=通常はキーボード。リダイレクト可能。


## _PUTCHAR 一文字を標準出力

ワードサイズで1文字を受け取り、標準出力に出力する。

sample.s

    _PUTCHAR    equ $ff02
    _EXIT       equ $ff00

        move.w  #'a',-(sp)
        .dc.w   _PUTCHAR
        addq.l  #2,sp

        .dc.w   _EXIT

実行結果

    A>sample
    aA>

## _PRINT 文字列を標準出力

アドレススタックにプッシュされた、ラベルの文字列データを標準出力に出力する。
文字列データの末尾には、終端文字として「0」を用意する必要がある。
サンプル中の「$0d,$0a」は併せて改行文字である。

sample.s

    _PRINT    equ $ff09
    _EXIT       equ $ff00

            pea     mes
            .dc.w   _PRINT
            addq.l  #4,sp

            .dc.w   _EXIT
    mes:    .dc.b   'PRINT TEST',$0d,$0a,0

実行結果

    A>sample
    PRINT TEST
    A>

## _GETC, _GETCHAR, _INKEY 標準入力

標準入力から受け取ったデータを、データレジスタ「d0」に格納する。
_GETCHARは入力内容をエコーバックする。
_INKEYはブレイクチェックが組み込まれており、実行中にBRKキーを押すと正常に終了する。(他の入力処理の場合、「^C」が表示されて終了する。)

sample.s

    _GETC       equ $ff08
    _GETCHAR    equ $ff01
    _INKEY      equ $ff07
    _EXIT       equ $ff00

        .dc.w   _GETC       *_GETCHAR,_INKEYも同様に使用する
        move.w  d0,-(sp)
        .dc.w   _PUTCHAR
        addq.l  #2,sp

        .dc.w   _EXIT

実行結果 _GETC

    A>sample
    aA>

実行結果 _GETCHAR

    A>sample
    aaA>

実行結果 _INKEY

    A>sample
    aA>

