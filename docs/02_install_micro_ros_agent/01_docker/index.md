# Docker

AMD64 (x86-64)環境ではdockerを使用する方が早いです。

<br>

## 要件

- 管理者権限不要で実行できる Docker server
- x86-64環境

<br>

## インストール

> Dockerは事前にインストールが終わっているものとします。

次のコマンドを実行してudevルールを適用します。

```bash
# udevルールの適用を行い、sudoなしでも読み書き権限を付与する
curl -s https://raw.githubusercontent.com/NITKK-ROS-Team/udev_rules/main/install.bash | sudo bash
```

<br>

## 実行方法

次のコマンドを入力します。(接続先が`/dev/ttyUSB0`かつボーレートが`115200`の場合)

```bash
docker run -it --rm -v /dev:/dev --privileged --net=host microros/micro-ros-agent:galactic serial --dev /dev/ttyUSB0 --baud 115200
```