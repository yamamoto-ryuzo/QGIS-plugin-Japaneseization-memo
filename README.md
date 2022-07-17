### QGISプラグイン日本語化メモ  
　とにかく，Qt Linguistを使っておこなうらしい。  
 
#### 全体の流れ  
1.Qt Linguistで作業を行う。  
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

2.日本語用の　.ts ファイルを作成する。  
　lupdate  
3. .qmファイルに変換する。  
　lrelease  
