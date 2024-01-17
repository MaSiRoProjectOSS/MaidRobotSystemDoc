## Docker for WindowsでUSBを使う方法

WSL経由でUSBと接続します。

### 1. WSLの初期設定

管理者画面にて行ってください。

```bash
# アプリをインストール
winget install --interactive --exact dorssel.usbipd-win
# カーネルをアップデート
wsl --update
# Ubuntu-22.04を追加
wsl --install --distribution Ubuntu-22.04
```

### 2. WSL内の設定

コマンド"```wsl```"でツールの設定を行う。

```bash
sudo apt update
sudo apt install -y linux-tools-generic-hwe-22.04 linux-cloud-tools-generic-hwe-22.04 hwdata
sudo update-alternatives --install /usr/local/bin/usbip usbip /usr/lib/linux-tools-5.15.0-53/usbip 20
# sudo adduser $USER video
exit
```

### 3. 設定したいUSBデバイスを設定する

管理者権限でコマンドプロンプトを実行してデバイスを接続する

```bash
# リストを確認する
usbipd wsl list
# 接続したいデバイスを確認してattachする。
#   ex : usbipd wsl attach --busid 1-2
usbipd wsl attach --busid <no>
usbipd wsl attach --busid 1-2
```

