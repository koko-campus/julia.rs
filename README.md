# 「Rust」 × 「ジュリア集合」

次世代システムプログラミング言語、Rustでジュリア集合を描写します。  
フラクタル図形といえば、「マンデルブロ集合♪」みていな認識もありますが、ジュリア集合もとってもキレイですよ～♪  

![成果物](./fruits/0000.png)  

## 環境情報

| 機能 | バージョン |
| ---- | ---- |
| Linux / Ubuntu| 20.04 |
| Rust | 1.63.0 |
| Ruby | 2.4.1 |

## 環境構築

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

## ffmpeg インストール

複数の画像ファイルからひとつの動画ファイルを生成するためのコマンドです。  

```bash
sudo apt install ffmpeg
```

## 実行方法

.envファイルを作成。  
テンプレートは`./seeds`ディレクトリ内にあります。  

```.env
TARGET_DIRECTORY=☆出力先ディレクトリ☆

START=☆何枚目から☆
UPTO=☆何枚目まで☆
# 途中でフリーズした時用

ASPECT_RATIO=☆縦横比☆
SHRINK_RATIO = ☆縮小比率☆
FILESIZE_HEIGHT=☆画像ファイルの高さ☆

START_X = ☆実軸の開始座標☆
START_Y = ☆虚軸の開始座標☆
DEFAULT_WIDTH = ☆デフォルトの横幅☆
DEFAULT_HEIGHT = ☆デフォルトの高さ☆
C_REAL=☆C点のX座標☆
C_IMAG=☆C点のY座標☆
```

```bash
# デバグ実行
cargo run

# コンパイルして、、、
cargo build --release

# 実行!!!
./target/release/julia_rs

# バックグラウンド実行、かつログイン後も実行したい場合には
nohup ./target/release/julia_rs &
```

## 動画ファイルの作成

```bash
ffmpeg -r 30 -i seeds/★★★/%08d.png -vcodec libx264 -pix_fmt yuv420p -r 60 ./fruits/★★★.mp4
```

## その他

- [YouTube](https://youtu.be/ObCuSCKdFTE)
