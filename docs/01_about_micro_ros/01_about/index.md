## micro-ROSとは？

ロボットを作成する上でマイコンは欠かせない要素です。micro-ROSを使うことでマイコンをあたかも一つのROS2ノードのように振る舞わせることができます。

<br>

micro-ROSはrclc-client libraryをベースにしてさまざまなミドルウェアを統合したライブラリです。マイコンによるUDP・TCPを使ったDDS通信をサポートするMicroXRCE-DDSや、POSIXベースのRTOSに対応しています。

micro-ROSのURLは[こちら](https://micro.ros.org/)から。

![](https://micro.ros.org/img/micro-ROS_architecture.png)

[micro.ros.org](https://micro.ros.org)より

## micro-ROS-Arduinoとは？

micro-ROS-Arduinoは、Arduino向けに作成されたmicro-ROS向けライブラリです。
Arduinoは2005年にリリースされたIDE（統合開発環境）であり、人気に火をつけたArduino UNOをはじめ、ESP32、STM32などの様々なマイコンの開発プラットフォームとなっています。

## PlatformIOとは？

ここで扱うIDE「PlatformIO」は、先程説明したArduinoにとどまらず様々なIDEを吸収した高機能IDEです。VSCode上で動作し、ライブラリのインポートも自動で行ってくれます。