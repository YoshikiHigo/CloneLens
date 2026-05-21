# CloneLens

CloneLens is a browser-based local code clone detection tool for Java and Python source files. It runs entirely in the browser, so selected files are not uploaded to any server.

日本語版は下にあります。

## Features

- Detects similar code fragments in Java (`.java`) and Python (`.py`) files.
- Accepts individual source files, ZIP archives, and folders.
- Processes ZIP archives locally in the browser.
- Uses tokenization, k-grams, fingerprinting, and winnowing to find clone candidates.
- Can normalize identifiers to make renamed-variable clones easier to find.
- Shows summary statistics, per-file statistics, clone candidate pairs, and side-by-side code snippets.
- Highlights clone ranges and token-level differences.

## How to Use

1. Open `clonelens.html` in a modern web browser.
2. Select source files, a ZIP file, a folder, or any combination of them.
3. Choose target languages: Java, Python, or both.
4. Adjust detection settings if needed.
5. Click `検出する` to start clone detection.
6. Review the statistics, file list, and detected clone candidates.

No build step, package installation, or server is required.

## Input Support

- Source files: `.java`, `.py`
- ZIP files containing Java or Python files
- Folders selected through the browser's folder picker

For ZIP files, CloneLens supports the `store` and `deflate` compression methods.

## Detection Settings

- `k-gram size`: Number of consecutive tokens used to create each token sequence.
- `winnowing window size`: Window size used to select representative fingerprints.
- `minimum matched tokens`: Minimum token length required for a clone candidate.
- `identifier normalization`: Replaces many identifiers with a common token so renamed code can still be matched.

## Privacy

CloneLens uses browser APIs such as the File API and Web Workers. The selected files are read and analyzed locally in the browser. They are not transmitted to a server by this tool.

Some browsers may show a word such as "Upload" in the file or folder selection dialog. This is browser UI text; CloneLens itself does not upload the selected files.

## Limitations

- CloneLens is a heuristic detection tool, not a semantic equivalence checker.
- It is good at finding copied or lightly edited code, but it may miss code that implements the same idea in a very different structure.
- ZIP support is intentionally minimal and does not cover every ZIP variant.
- Folder selection support depends on browser compatibility.

## License

This project is licensed under the MIT License. See `LICENSE` for details.

---

# CloneLens 日本語版

CloneLens は、Java と Python のソースコードを対象にした、ブラウザ上で動作するローカル実行型のコードクローン検出ツールです。選択したファイルはサーバへ送信されず、解析はブラウザ内で完結します。

## 主な機能

- Java (`.java`) と Python (`.py`) の類似コード片を検出します。
- 通常のソースファイル、ZIP ファイル、フォルダを入力として指定できます。
- ZIP ファイルをブラウザ内で展開して解析します。
- トークン化、k-gram、fingerprint、winnowing に基づいてクローン候補を探索します。
- 識別子を正規化することで、変数名などが変更されたコードも見つけやすくできます。
- 全体統計、ファイル別統計、クローン候補ペア、コード断片の横並び表示を提供します。
- クローン範囲と字句単位の差分をハイライトします。

## 使い方

1. `clonelens.html` をモダンな Web ブラウザで開きます。
2. ソースファイル、ZIP ファイル、フォルダ、またはそれらの組み合わせを選択します。
3. 対象言語として Java、Python、または両方を選択します。
4. 必要に応じて検出設定を調整します。
5. `検出する` ボタンを押して解析を開始します。
6. 統計情報、ファイル一覧、検出されたクローン候補を確認します。

ビルド、パッケージのインストール、サーバの起動は不要です。

## 入力形式

- ソースファイル: `.java`, `.py`
- Java または Python ファイルを含む ZIP ファイル
- ブラウザのフォルダ選択機能で指定したフォルダ

ZIP ファイルについては、`store` と `deflate` の圧縮方式に対応しています。

## 検出設定

- `k-gram サイズ`: 連続する何個のトークンをひとまとまりとして扱うかを指定します。
- `winnowing window サイズ`: 代表 fingerprint を選ぶための窓幅を指定します。
- `最小一致トークン数`: クローン候補として扱うために必要な最小トークン数を指定します。
- `識別子の正規化`: 変数名などの識別子を共通のトークンに置き換え、名前変更に強くします。

## プライバシー

CloneLens は File API や Web Worker などのブラウザ機能を使って、選択されたファイルをローカルで読み込み、解析します。このツールがファイルをサーバへ送信することはありません。

ブラウザによっては、ファイルやフォルダの選択ダイアログに「アップロード」と表示される場合があります。これはブラウザ側の表示であり、CloneLens が実際にファイルをアップロードするわけではありません。

## 制限事項

- CloneLens はヒューリスティックな検出ツールであり、プログラムの意味的な同値性を判定するものではありません。
- コピーされたコードや軽微に編集されたコードは見つけやすい一方、同じ考え方を大きく異なる構造で実装したコードは見つけにくい場合があります。
- ZIP 対応は最小限の実装であり、すべての ZIP 形式を扱えるわけではありません。
- フォルダ選択機能の利用可否はブラウザの対応状況に依存します。

## ライセンス

このプロジェクトは MIT License のもとで公開されています。詳細は `LICENSE` を参照してください。
