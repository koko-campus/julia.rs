# 「Rust」 × 「ジュリア集合」

次世代システムプログラミング言語、Rustでジュリア集合を描写します。  
フラクタル図形といえば、「マンデルブロ集合♪」みていな認識もありますが、ジュリア集合もとってもキレイですよ～♪


# 環境情報

| 機能 | バージョン |
| ---- | ---- |
| Linux / Ubuntu| 20.04 |
| Rust | 1.63.0 |
| Ruby | 2.4.1 |


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
# 「rbx」とか「ree」とかではない数字だけのバージョンね♪
rbenv install <バージョン>

# インストールが成功しているか確認
rbenv versions

# インストールしたバージョンに変更
rbenv global <バージョン>
```


## ffmpeg インストール

複数の画像ファイルからひとつの動画ファイルを生成するためのコマンドです。  

```bash
sudo apt install ffmpeg
```


# 実行方法


```bash
# コンパイルして、、、
cargo build --release

# 実行!!!
./target/release/julia_rs

# バックグラウンド実行、かつログイン後も実行したい場合には
nohup ./target/release/julia_rs &
```


# 動画ファイルの作成


```bash
ffmpeg -r 30 -i seeds/★★★/%08d.png -vcodec libx264 -pix_fmt yuv420p -r 60 ./fruits/★★★.mp4
```

