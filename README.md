### QGISプラグイン日本語化メモ  
 QGISのユーザーインターフェイスは　Qt　で作成されている。  
 とりあえず，現在翻訳作業で座礁した
 　[Instant Print plugin for QGIS](https://github.com/sourcepole/qgis-instantprint-plugin)  
 　を例に日本語化のメモを残す！  
 
 このプラグインは Pythonで作成されている。  
 
#### 0 .環境構築  
##### 0-1.　ユーザーインターフェイスがQtなので，とりあえず [Qt]([https://www.qt.io/ja-jp/product/development-tools](https://www.qt.io/ja-jp/download-open-source))をインストール。 
 私は，趣味+オープンソースなので，「Qtオープンソース版」を選択。
 ![image](https://user-images.githubusercontent.com/86514652/179387559-5d1dee7a-26d8-492f-aebc-91234476bd5a.png)  
 
##### 0-2.翻訳用のアプリ　[Qt Linguist](https://download.qt.io/linguist_releases/)　をインストール。  
![image](https://user-images.githubusercontent.com/86514652/179392618-a91e69d8-7e3d-4f6c-9b3e-0e63995316f7.png)  

#### 1..proファイルの編集
　[Qt Linguist　マニュアル](https://doc.qt.io/qt-6/linguist-programmers.html)  によると， .pro ファイルを作れと書いてある！  
　今回は，既存のファイルに日本語指定を行うので _ja.ts を追加，ついでに　.ui も追加した。  

結果は「instantprint_ts.pro」の内容は  
![image](https://user-images.githubusercontent.com/86514652/179388037-a12a24e7-4766-4345-bd39-5d55f8ec398e.png)

.py の中で翻訳対象は　tr("QGIS-plugin-Japaneseization-memo")　と tr("") 　で翻訳対象を明示する必要がある  
.ui　は　QT　で作成された本体  こちらは勝手に翻訳対象となる


#### 2.日本語用の　.ts ファイルを作成する。  
　lupdate  を使って，作成する。
![image](https://user-images.githubusercontent.com/86514652/179388068-ea9163dd-8a45-416a-a42e-2df8737b10fb.png)

#### 3.翻訳作業
 作成された.tsファイルをLinguistで翻訳  
 

#### 4..qmファイルに変換する。  
　lrelease    を使って，作成する。

#### 5.実際に動くようにする。  
　たぶんここでコケている？  
