# アプリのパスを通す

AUTOEXEC.batの「PATH」の末尾に、通したいパスを追記する。
ひとつのパスの末尾は「\」無し。

    ECHO OFF
    PATH A:\;A:\SYS;A:\BIN;A:\BASIC2;A:\ETC;
    (略)


    ECHO OFF
    PATH A:\;A:\SYS;A:\BIN;A:\BASIC2;A:\ETC;A:\XC\BIN
    (略)