# ifqoi.sph - QOI Susie Plugin

QOI (Quite OK Image Format) 形式の画像ファイルを Susie 対応画像ビューアで表示するための 64bit プラグインです。

## 概要

QOI 形式の画像をデコードし、Susie 対応ビューア (例: あふｗ) で表示します。QOI デコーダを内包しており、外部ライブラリには依存しません。

## 機能

- QOI 形式 (*.qoi) の画像ファイルの読み込み
- RGB/RGBA 入力に対応し、出力は 32bit (BGRA) で提供
- 透過は背景色 (RGB 224,224,224) に合成
- 64bit (x64) 環境に対応
- 軽量なデコード実装

## ビルド方法

### 必要な環境

- Visual Studio 2022 以降
- CMake 3.15 以降
- Windows 10/11 (64bit)

### ビルド手順

1. リポジトリを取得
```bash
git clone <このリポジトリのURL>
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

完成後、`build/Release` ディレクトリに `ifqoi.sph` が生成されます。

## インストール方法

1. ビルドされた `ifqoi.sph` を Susie 対応ビューア (例: あふｗ) のプラグインフォルダにコピーします
2. ビューアを再起動します
3. QOI 形式の画像ファイルが開けるようになります

## 対応フォーマット

- **拡張子**: .qoi
