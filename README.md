# ifqoi.sph - QOI Susie Plugin

QOI (Quite OK Image Format) 形式の画像ファイルを Susie 対応画像ビューアで表示するための 64bit プラグインです。

## 概要

このプラグインは、高速でロスレスな画像圧縮フォーマットである QOI 形式のファイルをデコードし、「あふｗ」などの Susie 対応ビューアで表示できるようにします。

## 機能

- QOI 形式 (*.qoi) の画像ファイルの読み込み
- RGB および RGBA カラーモードに対応
- 64bit (x64) 環境に対応
- 高速なデコード処理

## ビルド方法

### 必要な環境

- Visual Studio 2022 以降
- CMake 3.15 以降
- Windows 10/11 (64bit)

### ビルド手順

1. リポジトリをクローン
```bash
git clone https://github.com/yourusername/ifqoi.git
cd ifqoi
```

2. ビルドディレクトリを作成
```bash
mkdir build
cd build
```

3. CMake を実行
```bash
cmake .. -G "Visual Studio 17 2022" -A x64
```

4. コンパイル
```bash
cmake --build . --config Release
```

完成後、`Release` ディレクトリに `ifqoi.sph` が生成されます。

## インストール方法

1. ビルドされた `ifqoi.sph` を Susie 対応ビューア (例: あふｗ) のプラグインフォルダにコピーします
2. ビューアを再起動します
3. QOI 形式の画像ファイルが開けるようになります

## 対応フォーマット

- **拡張子**: .qoi
- **カラーモード**: RGB (3チャンネル), RGBA (4チャンネル)
- **カラースペース**: sRGB, Linear
- **最大画像サイズ**: 4億ピクセル

## QOI フォーマットについて

QOI (Quite OK Image Format) は以下の特徴を持つ画像フォーマットです：

- PNG と同等の圧縮率
- PNG より 20～50倍高速なエンコード
- PNG より 3～4倍高速なデコード
- シンプルな仕様で実装が容易

詳細は公式サイトをご覧ください: https://qoiformat.org/

## 参考

- [QOI 公式リポジトリ](https://github.com/phoboslab/qoi)
- [Susie プラグイン仕様](https://toro.d.dooo.jp/dlsphapi.html)
- [参考実装 (ifdcm)](https://github.com/mtkhs/ifdcm)

## ライセンス

MIT License

## 作者

2025年作成
