# Install


```bash
sudo apt install -y ros-humble-image-transport

# optional
sudo apt install -y ros-humble-compressed-image-transport ros-humble-theora-image-transport  ros-humble-image-transport-plugins
```


### Bazel

```bash
sudo apt install apt-transport-https curl gnupg -y
curl -fsSL https://bazel.build/bazel-release.pub.gpg | gpg --dearmor >bazel-archive-keyring.gpg
sudo mv bazel-archive-keyring.gpg /usr/share/keyrings
echo "deb [arch=amd64 signed-by=/usr/share/keyrings/bazel-archive-keyring.gpg] https://storage.googleapis.com/bazel-apt stable jdk1.8" | sudo tee /etc/apt/sources.list.d/bazel.list

sudo apt update && sudo apt install bazel
sudo apt update && sudo apt full-upgrade

```



```bash
sudo apt update
sudo apt install -y jq
# mediapipe 0.8.9.1
pip install --upgrade pip
pip install mediapipe
pip install protobuf==3.20.*
```


### mediapipe

```bash
sudo apt update
sudo apt install -y \
    libopencv-core-dev \
    libopencv-highgui-dev \
    libopencv-calib3d-dev \
    libopencv-features2d-dev \
    libopencv-imgproc-dev \
    libopencv-video-dev
cd $HOME
git clone --depth 1 https://github.com/google/mediapipe.git

# Change directory into MediaPipe root directory
cd mediapipe
```

Defaulting to user installation because normal site-packages is not writeable
ERROR: Could not find a version that satisfies the requirement mediapipe (from versions: none)
ERROR: No matching distribution found for mediapipe


## 使用しているソフトウェア

| Software Name     | Package manager | 仕様している理由                   | Notes.                                                |
| ----------------- | --------------- | ---------------------------------- | ----------------------------------------------------- |
| jq                | apt             | bash で config.json を処理するため |                                                       |
| mediapipe         | pip             | 顔認識プログラムを動作させるため   | [pypi-mediapipe](https://pypi.org/project/mediapipe/) |
| python3-cv-bridge | apt             |                                    |                                                       |



### ROS2 node

| Software Name                                | Unit      | 仕様している理由                   | Notes. |
| -------------------------------------------- | --------- | ---------------------------------- | ------ |
| ros-${ROS_DISTRO}-image-transport            | Head Unit | カメラ描画を取得するため           |        |
| ros-${ROS_DISTRO}-compressed-image-transport | Head Unit | 圧縮されたカメラ描画を取得するため |        |
| ros-${ROS_DISTRO}-theora-image-transport     | Head Unit | カメラ描画をライブ配信をする       |        |
| ros-${ROS_DISTRO}-image-transport-plugins    | Head Unit |                                    |        |
| ros-${ROS_DISTRO}-cv-bridge                  |           |                                    |        |
|                                              |           |                                    |        |
|                                              |           |                                    |        |


## インスール手順

* フォルダ```/opt/MaidRobotSystem```にショートカットリンクを作成します。
上記のフォルダにあることが前提で作成してますが、もし別の場所にインストールしたい場合は、
[Configuration](01_02_Configuration.md)にしたがって設定を変更してください。


### ROSのインストール手順

```bash
/opt/MaidRobotSystem/src/planetary_module/ros/script/build.sh build release
```

build.sh <build | rebuild | clean> <debug | release> [select_package] [cmake_argument]


## VS Code用のソフトウェア設定

```bash
sudo apt update

## Markdown Preview Enhanced
sudo apt install -y openjdk-17-jdk
## C/C++ code format
sudo apt install -y llvm clang clang-format

```


## その他


### サポートツール

* powertop


```bash
sudo apt install -y powertop

```


