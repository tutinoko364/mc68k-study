# ED.X-テキストエディタ

Human68kに付属する標準テキストエディタ。

プロンプトに以下を入力して実行すると、「(ファイル名).S」がED.Xで開かれる。
存在しないファイル名を指定した場合、新しく「(ファイル名).S」が作成され、

    A> ED (ファイル名).S
    
* Human68kでは、アセンブリソースファイルの拡張子を「.S」としている。

編集中に、「ESCキー」を押すと、「ESC」モードに移る。
「ESC」モード中に「Eキー」を押すことで、ファイルのセーブ後プロンプトに戻る。