# 開発環境のセットアップ方法
本書のOSを開発するための環境構築について記載する。

## 開発環境
- 自作サーバー
- OS：Ubuntu Desktop 24.04.3 LTS

## 基本パッケージのインストール
```
apt install -y curl vim lv git
apt install -y build-essential
apt install -y python3-venv
apt install -y ninja-build meson pkg-config libglib2.0-dev libpixman-1-dev libfdt-dev libnfs-dev libiscsi-dev zlib1g-dev
apt install -y flex bison
```

## Rustのセットアップ
ユーザー(ktaki8ra)で実行
```
curl --proto '=https' --tlsv1.2 -sSf https://sh.rustup.rs | sh
```

## QEMUのインストール
本書のバージョンに合わせて、v9をインストールすることにする。   
gitlabからダウンロードし、指定のバージョンを管理しているブランチに移動。その後コンパイルする。
```
git clone https://gitlab.com/qemu-project/qemu.git
cd qemu
git checkout -t origin/stable-9.2
./configure
make
make install
```
