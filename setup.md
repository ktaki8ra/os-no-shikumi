# 開発環境のセットアップ方法
本書のOSを開発するための環境構築について記載する。

## 開発環境
- 自作サーバー
- OS：Ubuntu Desktop 24.04.3 LTS

## 基本パッケージのインストール
- 基本パッケージ
```
apt install -y curl
apt install -y build-essential
apt install -y python3-venv
apt install -y ninja-build meson pkg-config libglib2.0-dev libpixman-1-dev libfdt-dev libnfs-dev libiscsi-dev zlib1g-dev
apt install -y flex bison
apt install -y netcat-openbsd
```
- 便利なパッケージ   
滝原がよく使う便利なパッケージも入れておく。
```
apt install -y vim lv tree
```

## Rustのセットアップ
ユーザー(ktaki8ra)で実行
```
curl --proto '=https' --tlsv1.2 -sSf https://sh.rustup.rs | sh
```
- バージョン確認
```
$ cargo --version
cargo 1.89.0 (c24e10642 2025-06-23)
$ rustc --version
rustc 1.89.0 (29483883e 2025-08-04)
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
- バージョン確認
```
$ qemu-system-x86_64 --version
QEMU emulator version 9.2.4 (v9.2.4)
Copyright (c) 2003-2024 Fabrice Bellard and the QEMU Project developers
```
