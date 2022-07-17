### QGISプラグイン日本語化メモ  
 QGISのユーザーインターフェイスは　Qt　で作成されている。  
 とりあえず，現在翻訳作業で座礁した
 　[Instant Print plugin for QGIS](https://github.com/sourcepole/qgis-instantprint-plugin)  
 　を例に日本語化のメモを残す！  
 
まじめに， Pythonで作成されたQGI　Pluginである。  
 
#### 全体の流れ  
0.環境構築  
　[Qt]([https://www.qt.io/ja-jp/product/development-tools](https://www.qt.io/ja-jp/download-open-source))を手に入れる必要がある。 
 私は，趣味+オープンソースなので，「Qtオープンソース版」を選択。
 ![image](https://user-images.githubusercontent.com/86514652/179387559-5d1dee7a-26d8-492f-aebc-91234476bd5a.png)


1.日本語用の　.ts ファイルを作成する。  
　lupdate  

2.Qt Linguistで作業を行う。  
　[Qt Linguist　マニュアル](https://doc.qt.io/qt-6/linguist-programmers.html)  によると， .pro ファイルを作れと書いてある！
.pro　ファイルの中身はPythonで作成されたQGI　Pluginの場合はこんな感じ

>SOURCES = main-dlg.py \  
>　　　　　 options-dlg.py \  
>　　　　　 main.py  
>FORMS           = search-dlg.ui  
>TRANSLATIONS    = superapp_dk.ts \  
>　　　　　　　　 superapp_fi.ts \  
>　　　　　　　　 superapp_no.ts \  
>　　　　　　　　 superapp_se.ts  

.py の中で翻訳対象は　tr("QGIS-plugin-Japaneseization-memo")　と tr("") 　で翻訳対象を明示する必要がある  
.ui　は　QT　で作成された本体  こちらは勝手に翻訳対象となる

と書いてあるようだ。  

3..qmファイルに変換する。  
　lrelease  

4.実際に動くようにする。  
　たぶんここでコケている？  
