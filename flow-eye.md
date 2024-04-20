# FlowEyeの使い方

## はじめに
FlowEyeはValve Index DIY アイトラッカー用のIRイルミネーターとカメラマウントのセットです。アイトラッカーとして動かすためにはいくつかの追加部品と作業が必要になります。基本的にはEyeTrackVRと互換性があるため、詳しい作業内容や必要部品については[公式ドキュメント](https://docs.eyetrackvr.dev/)をご覧ください。以下はFlowEyeを使う上での特記事項及び個人的な注意事項をまとめたものです。

## カメラの選定とIRフィルタの除去
FlowEyeは **OV2640-130°カメラモジュール** 向けに設計を行っています。
AliExpressでOV2640と検索し、130°レンズがついた物を購入してください。
また、130°レンズはIRフィルタ実装済みの商品しか出回っていないため、ご自身で[IRフィルタの除去](https://www.youtube.com/watch?v=QYH-FWvDbDc)を行っていただく必要があります。
※フィルタ直下にレンズがあるため、レンズを傷つけないよう十分注意して作業する必要があります(>_<)

## 赤外線LEDの安全性
FlowEyeはEyeTrackVR V3と同様に各LED(XL-3216HIRC-850)を **3.2[mA]** で駆動しています。安全性についての概算は[公式ドキュメント](https://docs.eyetrackvr.dev/getting_started/led_safety)をご覧ください。
また、実際の駆動電流を知りたい場合は裏面のテストポイントにおいて、5V-P1間及び5V-P2間の電位差を680[Ω]に対して十分に内部抵抗の大きい電圧計で計測し、2.2[V]程度であることを確認してください。   
$2.2[V]/680[Ω]=0.0032[A]$

## Flow Eyeへの給電
IRイルミネーターの駆動電圧は **5[V]** のため、USBのVBUSやESP32開発ボードの5V出力ピンで駆動させることができます。左右の電源は必ず並列に接続してください。

## USBハブの選定
有線モードのOpenIrisとVive Facial Trackerを同時に使用する場合、MTTのUSBハブを使用する必要があります。国内で安価かつ入手性の良いMTTのハブとして「Anker 4-Port Ultra-Slim USB 3.0 Hub」がお勧めです。

## BOM
|部品|必要個数|入手元|単価(円)|
|----|----:|----|----:|
|FlowEye|2|booth|1000|
|OV2640-130|2|AliExpress|750|
|Seeed Studio Xiao ESP32S3 Sense|2|AliExpress|2,000|
|Extra|
|FPCケーブル(24pin,0.5mm,25cm,A-Type)|2|AliExpress|150|
|FPC中継コネクタ(24pin,0.5mm)|2|AliExpress|20|
|Anker 4-Port Ultra-Slim USB 3.0 Hub|1|Amazon|1,300|
|Type-Cブレイクアウトボード|1|AliExpress|50|
