## windrvXM.SYS-Windowsとのファイルやり取り

以下からダウンロード可能

[http://coexe.web.fc2.com/WindrvXM.html](http://coexe.web.fc2.com/WindrvXM.html)

# X68k側の使用準備

ディスクイメージ「WindrvXM.XDG」をマウントし、ドライバ「WindrvXM.SYS」をHDDにコピーする。

    A>copy b:*.SYS a:

ドライバが読み込まれるように、config.sysを編集する。

    A> ED config.sys

末尾に以下を追記してセーブする。(ESCキー押下後、Eキー押下でセーブ)

    DEVICE = \WindrvXM.SYS

プロンプトから以下を実行することで、config.sysの内容がダンプされる。
問題なく追記されているか確認すること。

    type config.sys

# Windows側の準備

XM6の「ツール」タブから、「オプション」を選択する。
オプションウインドウの「Windrv」タブを選択する。

「WindrvXMとWINDRVを使用する」にチェックを入れる。

「ドライブ数」を１以上にする

下リストをクリックし、共有を行うWindows側のフォルダパスを設定する。

# 準備完了後

XM6をリセットすると、WindrvXM.SYSが読み込まれるようになっている。

共有フォルダは、XM6のDドライブ(FDD二基、HDD一基の場合?)にマウントされる。

    ドライブD:を登録しました