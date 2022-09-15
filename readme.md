# 「Rust」 × 「ジュリア集合」

次世代システムプログラミング言語、Rustでジュリア集合を描写します。  
フラクタル図形といえば、「マンデルブロ集合♪」みていな認識もありますが、ジュリア集合もとってもキレイですよ～♪


# 環境情報

| 機能 | バージョン |
| ---- | ---- |
| Linux / Ubuntu| 20.04 |
| Rust | 1.63.0 |



# 環境構築


```bash
# イロイロ最新に
sudo apt update
sudo apt upgrade
```

## Rust インストール

```bash
curl https://sh.rustup.rs -sSf | sh
# インストール設定はデフォルト(1)で!!!
# 次に環境変数(PATH)を設定します。
export PATH="$HOME/.cargo/bin:$PATH"
# 最後に正しくインストール、パスの設定がされたか、以下のコマンドで確認します。
cargo --version
# -> cargo 1.63.0
rustc 1.63.0
# -> rustc 1.63.0
rustdoc --version
# -> rustdoc 1.63.0
```

## Ruby インストール

```bash
sudo apt install rbenv
rbenv init
eval "$(rbenv init -)"
curl -fsSL https://github.com/rbenv/rbenv-installer/raw/main/bin/rbenv-doctor | bash

gem install rubinius-melbourne -v '3.9'

# インストール可能なRuby一覧を取得して
rbenv install --list

# 最新のバージョンをインストール
rbenv install <バージョン>
```

