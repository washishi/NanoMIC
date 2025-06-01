# NanoMIC  
## M5Stackシリーズ のGroveポート内に取り付けることのできる超小型のPDMマイク基板です
<img src="docs/images/NanoMIC.jpg" width="300px" height="280px"><img src="docs/images/IMG20250531031034.jpg" width="300px" height="280px"><br>

- 取り付けることによりPDMマイクの利用が可能です  
- 純正の[PDMマイクユニット](https://docs.m5stack.com/ja/unit/pdm)と互換性がありますので置き換えて利用可能です  
- Groveポート内に入ってしまう超小型サイズの為ケース外に出っ張りません
### なお本基板は完成品をBOOTH[ わしししょっぷ ](https://washishi.booth.pm/)で頒布予定です
<br>


## 使い方(取り付け、取り外し方)
- 取り付け方  
  - 写真の向きでGroveコネクタのピンの上にNanoMIC基板を斜めに差し込みます  
    (基板の角がコネクタのピンとケースの隙間に入るように)  
<img src="docs/images/IMG20250601211758.jpg" width="300px" height="280px"><img src="docs/images/IMG20250601211259.jpg" width="300px" height="280px"><br>
  - NanoMIC基板を水平に起こします  
<img src="docs/images/IMG20250601211350.jpg" width="300px" height="280px"><img src="docs/images/IMG20250601211336.jpg" width="300px" height="280px"><br>
  - NanoMIC基板をGroveコネクタに押し込んで完了です  
    左側の様に押し込むのを基板の切り欠けが見える状態までにしておくと取り外しが楽です  
    さらに押し込むと右側の様に完全に入れることモ出来ます  
<img src="docs/images/IMG20250601211458.jpg" width="300px" height="280px"><img src="docs/images/IMG20250601211526.jpg" width="300px" height="280px">
- 取り外し方
  - ※完全に押し込んでいない場合は次のステップへ進んでください  
    NanoMIC基板のマイク(銀色の四角部分)に爪をかけて右側の様に基板の切り欠けが見えるまで少し引き出します  
    (あまり力を掛けると外れて飛んでいく可能性がありますで注意してください)  
<img src="docs/images/IMG20250601212205.jpg" width="300px" height="280px"><img src="docs/images/IMG20250601211458.jpg" width="300px" height="280px">
  - 基板の切り欠け部分に爪をかけて完全に引き抜いて取り外し完了です  
<img src="docs/images/IMG20250601211618.jpg" width="300px" height="280px"><img src="docs/images/IMG20250602065909.jpg" width="300px" height="280px">

## ソフトウエアでの利用について
M5Stackの[PDMマイクユニット](https://docs.m5stack.com/ja/unit/pdm)と同様に利用できます  
またサンプルプログラムとしてAtomS3/S3Rで動くAvater(ｽﾀｯｸﾁｬﾝ)が音に合わせて口パクするプログラムを
M5Burnerに上げています  
(NanoMICを利用する場合は右上の選択で 「1.2 PDM_Unit」を選択してダウンロード、書き込みを行って下さい)
<img src="docs/images/SampleProgram.png" width="700px" height="180px">

## 基板イメージ
<img src="docs/images/3d-top.png" width="300px" height="280px"><img src="docs/images/3d-bottom.png" width="300px" height="280px">  
<img src="docs/images/top_pattern.png" width="300px" height="280px"><img src="docs/images/bottom_pattern.png" width="300px" height="280px">

## 回路図
M5StackのPDMマイクユニットとは利用している部品が異なるだけでほぼ同じ回路です  
本リポジトリ schematics の下に KiCad(Ver9)で作成したデータ一式があります  
<img src="docs/images/schematic.png" width="300px">  

## BOM(使用部品リスト)
|番号|名称|仕様/型番|メーカー|個数|備考|備考購入先|  
|:--|:--|:--|:-:|:-:|:-:|:-:|  
|-|基板|NanoMIC基板|-|1||[JLCPCB](https://jlcpcb.com/JPV)へ発注|
|MIC1|PDMマイク|SPH0641LM4H-1|Knowles→Syntiant|1||[マルツ](https://www.marutsu.co.jp/pc/i/48871354/)(DigiKey在庫品)|  
|U1|LDO|NCP171AMX330325TCG|onsemi|1||[マルツ](https://www.marutsu.co.jp/pc/i/1803216/)(海外取り寄せ品)|  
|C1,C3|チップ積層セラミックコンデンサ|1uF 1005(mm)サイズ|-|2|耐圧6.3V以上|[秋月電子](https://akizukidenshi.com/catalog/g/g113377/)(100個セット)|
|C2|チップ積層セラミックコンデンサ|0.1uF 1005(mm)サイズ|-|1|耐圧4V以上|[秋月電子](https://akizukidenshi.com/catalog/g/g113377/)(25個セット)|

## 部品について
- 基板  
  本リポジトリの schematics\production にJLCPCB向けのガーバデータ一式 (NanoMic.zip) がありますので発注して入手してください
- PDMマイク  
[SPH0641LM4H-1](https://mm.digikey.com/Volume0/opasdata/d220001/medias/docus/1290/SPH0641LM4H-1.pdf) を利用しています Knowles社の製品だったのですがKnowles社のコンシューマ部門が
Syntiant社に買収された為そちらからの販売となっています  
- LDO(低ドロップアウト リニア電圧レギュレータ)  
  onsemi社 [NCP171シリーズ](https://www.onsemi.com/download/data-sheet/pdf/ncp171-d.pdf) 3.3V出力品NCP171AMX330325TCGを利用しています   
  この超小型(1.2mm四方)のLDOのおかけでGroveコネクタ内に収めることができました  
  GrovePortの電源が5Vでマイクの電源電圧が3.6V以下の為これで電圧を3.3Vに下げています  
  マルツで[海外取り寄せ品](https://www.marutsu.co.jp/pc/i/1803216/)として扱っていますが少量購入だと単価がかなり高いです([Digikey在庫品](https://www.marutsu.co.jp/pc/i/33030236/)もありますがさらに高いです)
## 制作について
- 背面にしか端子のないマイク,LDOがある為リフローが必須です  
- コンデンサは手はんだでの取り付けも可能ですが小さくて困難な為こちらもリフローしたほうがいいと思います  
また真ん中が1uFでマイク側が0.1uF、LDO側が1uFとなります(端のコンデンサは距離がないのでおそらく逆でも動きます)
- 私は下記の方法で両面リフローしました  
  - まずコンデンサの面を普通のクリームはんだ(融点183℃)でリフロー
  - 次にマイクの面を低温はんだ(融点138℃)で183℃未満の温度で  
    先に付けたコンデンサごと過熱してリフロー
