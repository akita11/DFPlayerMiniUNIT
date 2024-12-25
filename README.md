# DFPlayerMiniUNIT

<img src="https://github.com/akita11/DFPlayerMiniUNIT/blob/main/DFPlayerMiniUNIT.jpg" width="240px">

<img src="https://github.com/akita11/DFPlayerMiniUNIT/blob/main/DFPlayerMiniUNIT_with_Mini.jpg" width="240px">

DFRobotの音声プレーヤモジュール[DFPlayer(DFPlayerMini)](https://www.switch-science.com/products/4291)をGrove端子を接続して制御できるモジュールです。Grove端子からシリアル(UART)通信で音声再生などを制御することができます。（UIFlow(v1)用のブロックも用意する予定）

※DFPlayerMiniは付属していません


## 使い方

以下のようにスピーカやアンプを接続し、Grove端子からの制御で音声を再生します。


### アンプ付きスピーカに接続する場合

3.5mmジャック（ステレオ：上部中央）に3.5mmステレオケーブル等でアンプに接続します。


### スピーカを直接接続する場合

基板中央部の1.25mmピッチコネクタ(Molex 53047-0210用)にスピーカを接続します。市販の小型スピーカ（M5Stack本体に使われているものなど。AliExpressやTaobaoでも同等品があります）を接続することができます。


### 3.5mmジャックに直接スピーカを接続する方法

3.5mmジャックに直接スピーカを接続することもできます。その場合は、基板裏面のハンダジャンパを以下のように修正してください。

<img src="https://github.com/akita11/DFPlayerMiniUNIT/blob/main/DFPlayerMiniUNIT_back.jpg" width="240px">

- JP1をカット
- JP2・JP3の中央と△マーク側をカットし、中央と反対側（△マークがない側）をショート


## Author

Junichi Akita (@akita11) / akita@ifdl.jp
