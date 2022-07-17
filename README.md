### QGISプラグイン日本語化メモ  
 QGISのユーザーインターフェイスは　Qt　で作成されている。  
 とりあえず，現在翻訳作業で座礁した
 　[Instant Print plugin for QGIS](https://github.com/sourcepole/qgis-instantprint-plugin)  
 　を例に日本語化のメモを残す！  
 
 このプラグインは Pythonで作成されている。  
 
#### 0 .環境構築  
##### 0-1.　ユーザーインターフェイスがQtなので，とりあえず [Qt](https://www.qt.io/ja-jp/download-open-source)をインストール。 
 私は，趣味+オープンソースなので，[Qtオープンソース版](https://www.qt.io/ja-jp/download-open-source)を選択。
 ![image](https://user-images.githubusercontent.com/86514652/179387559-5d1dee7a-26d8-492f-aebc-91234476bd5a.png)  
 実際に使うのは　Qt　Design　Studio　のほう  
 ![image](https://user-images.githubusercontent.com/86514652/179393788-22a16f02-0776-4f24-b07a-af8a03bec9de.png)

 
##### 0-2.翻訳用のアプリ　[Qt Linguist](https://download.qt.io/linguist_releases/)　をインストール。  
![image](https://user-images.githubusercontent.com/86514652/179392618-a91e69d8-7e3d-4f6c-9b3e-0e63995316f7.png)  

#### 1..proファイルの編集
　[Qt Linguist　マニュアル](https://doc.qt.io/qt-6/linguist-programmers.html)  によると， .pro ファイルを作れと書いてある！  
　今回は，既存のファイルに日本語指定を行うので _ja.ts を追加，ついでに　.ui も追加した。  

結果は「instantprint_ts.pro」の内容は  
![image](https://user-images.githubusercontent.com/86514652/179394298-96992633-390a-42d7-bda3-e22bfc84641e.png)

.py の中で翻訳対象は　tr("QGIS-plugin-Japaneseization-memo")　と tr("") 　で翻訳対象を明示する必要がある  
.ui　は　QT　で作成された本体  こちらは勝手に翻訳対象となる

#### 2.日本語用の　.ts ファイルを作成する。  
　lupdate  を使って，作成する。  
 が，Qt5ではうまく動作しない・・・これが問題か？
 なので，とりあえずQt6を選択！
 ![image](https://user-images.githubusercontent.com/86514652/179393972-4f460f7c-e45b-4560-8c4a-1dbcda31471b.png)
　そして，変換実行
![image](https://user-images.githubusercontent.com/86514652/179394332-bc7e2850-6c65-4007-9b10-a9a95a8df156.png)

#### 3.翻訳作業
 作成された.tsファイルをLinguistで翻訳  
 

#### 4..qmファイルに変換する。  
　lrelease    を使って，作成する。

#### 5.実際に動くようにする。  
　たぶんここでコケている？  
