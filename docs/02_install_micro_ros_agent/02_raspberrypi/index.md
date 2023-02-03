# RaspberryPiへのインストール

ここでは、RaspberryPiにmicro-ROS-agentをインストールする方法を示します。

x86_64(amd64)を対象にしていません。

<br>

## 動作確認リスト

| Distro | チェック | 補足 |
| --- | --- | --- |
| Foxy | ✅ | Ubuntu20のみ |
| Galactic | ✅ | Ubuntu20のみ |
| Humble | TODO | Ubuntu22のみ |
| Humble | ✅ | RaspberryPi OSのみ |


| OS | ターゲット | チェック |
| --- | --- | --- |
| Ubuntu20.04 | RaspberryPi4 | ✅ |
| Ubuntu20.04 | RaspberryPi4 | TODO |
| RaspberryPi OS | RaspberryPi4 | ✅ |

<br>

## 要件

いずれの環境も `ros-<distro>-ros-base` 以上をインストールする必要があります。その他の依存パッケージは自動で解消できます。

<br>

## インストール

1.【共通】次のコマンドを実行してudevルールを適用します。

```bash
# udevルールの適用を行い、sudoなしでも読み書き権限を付与する
curl -s https://raw.githubusercontent.com/NITKK-ROS-Team/udev_rules/main/install.bash | sudo bash
```

<br>

2．それぞれの環境に応じてdpkgをダウンロードします。

### RaspberryPi OS (ROS-Humble)

```bash
wget https://s3.ap-northeast-1.wasabisys.com/download-raw/dpkg/ros2-desktop/debian/bullseye/ros-humble-micro-ros-agent-0.0.1_arm64.deb -O ./uros.deb
```

### Ubuntu20 (ROS-Foxy)

```bash
wget https://s3.ap-northeast-1.wasabisys.com/download-raw/dpkg/ros2-desktop/ubuntu/focal/ros-foxy-micro-ros-agent-0.0.1_20230203_arm64.deb -O ./uros.deb
```

### Ubuntu20 (ROS-Galactic)

```bash
wget https://s3.ap-northeast-1.wasabisys.com/download-raw/dpkg/ros2-desktop/ubuntu/focal/ros-galactic-micro-ros-agent-0.0.1_20230203_arm64.deb -O ./uros.deb
```

3．インストールします。

```bash
sudo apt install ./uros.deb
rm ./uros.deb
```

<br>

## 実行方法

次のコマンドを入力します。(接続先が`/dev/ttyUSB0`かつボーレートが`115200`の場合)

```bash
source /opt/micro_ros_agent/setup.bash
ros2 run micro_ros_agent micro_ros_agent serial --dev /dev/ttyUSB0 --baud 115200
```

<br>