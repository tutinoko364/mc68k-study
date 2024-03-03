## プロンプトにカレントパスを表示する

human68kのプロンプトは、デフォルトではドライブ名のみ表示されている。

    A>

以下のコマンドを入力すると、プロンプトにカレントパス全文が表示される。

    A>prompt $p$g
    A:\>

起動直後、自動的に設定するためにAUTOEXEC.batにコマンドを記載する。
「PATH」次行にコマンドを追記する。

    ECHO OFF
    PATH A:\;A:\SYS;A:\BIN;A:\BASIC2;A:\ETC;
    (略)


    ECHO OFF
    PATH A:\;A:\SYS;A:\BIN;A:\BASIC2;A:\ETC;
    PROMPT $P$G
    (略)