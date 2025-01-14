# DFPlayerMiniUNIT

<img src="https://github.com/akita11/DFPlayerMiniUNIT/blob/main/DFPlayerMiniUNIT.jpg" width="240px">

<img src="https://github.com/akita11/DFPlayerMiniUNIT/blob/main/DFPlayerMiniUNIT_w_Mini.jpg" width="240px">

※当初掲載していた"DFPlayerMini"をとりつけた状態の写真で、DFPlayerMiniの向きが逆になっていました。こちらの写真が正しいです。

DFRobotの音声プレーヤモジュール[DFPlayer(DFPlayerMini)](https://www.switch-science.com/products/4291)をGrove端子を接続して制御できるモジュールです。Grove端子からシリアル(UART)通信で音声再生などを制御することができます。UIFlow(v1)用のブロックもあります。

※DFPlayerMiniは付属していません


## 使い方（接続方法）

以下のようにスピーカやアンプを接続し、Grove端子からの制御で音声を再生します。


### アンプ付きスピーカに接続する場合

3.5mmジャック（ステレオ：上部中央）に3.5mmステレオケーブル等でアンプに接続します。


### スピーカを直接接続する場合

<img src="https://github.com/akita11/DFPlayerMiniUNIT/blob/main/DFPlayerMiniUNIT_spk.jpg" width="240px">

<img src="https://github.com/akita11/DFPlayerMiniUNIT/blob/main/DFPlayerMiniUNIT_spk_w_Mini.jpg" width="240px">

基板中央部の1.25mmピッチコネクタ(Molex 53047-0210用)にスピーカを接続します。市販の小型スピーカ（M5Stack本体に使われているものなど。AliExpressやTaobaoでも同等品があります）を接続することができます。

※こちらの2つめのスピーカつき写真では、DFPlayerMiniの向きが逆になっています。写真は近日中に差し替えます。申し訳ありません。


### 3.5mmジャックに直接スピーカを接続する方法

3.5mmジャックに直接スピーカを接続することもできます。その場合は、基板裏面のハンダジャンパを以下のように修正してください。

<img src="https://github.com/akita11/DFPlayerMiniUNIT/blob/main/DFPlayerMiniUNIT_back.jpg" width="240px">

- JP1をカット
- JP2・JP3の中央と△マーク側をカットし、中央と反対側（△マークがない側）をショート


## 使い方（ソフトウエア）

あらかじめ、microSDカードに使用する音声データ（*.mp3等）をコピーしておき、それをDFPlayerMiniにさしておきます。（このときコピーした順番が、再生時に使用する「曲番号」になります）

### UIFlow(v1)での使い方

「DFPlayerMini.m5b」をダウンロードし、UIFlow(v1)の"Custom"の"Open *.m5b"からこのファイルを指定すると、Init、Play、Volume、Stopの4つのブロックを使用できます。

<img src="https://github.com/akita11/DFPlayerMiniUNIT/blob/main/DFPlayerMini_Block.png" width="240px">

- DFPlayerMini_Init : 初期化。最初に1回だけ読み出します。"TX"と"RX"には、使用するGroveポート・マイコン本体にあわせて、使用するピン番号を指定します。例えば、M5StackBasicのPortA（本体の赤いコネクタ）の場合は、上図のようにTX=21、RX=22を指定します。M5StackCore2のPortAの場合は、TX=32、RX=33となります。
- DFPlayerMini_Play : numに指定した「曲番号」の音声を再生します。
- DFPlayerMini_Volume : volに指定した音量に設定します。
- DFPlayerMini_Stop : 再生中の音声を停止します。


### その他のソフトウエアでの使い方

Arduino用にはライブラリがあるようなので、そちらを使ってもOKです。
あるいは、DFPlayerMiniのデータシート等を参考に、制御コマンドを送信して使用してください。

## Author

Junichi Akita (@akita11) / akita@ifdl.jp
