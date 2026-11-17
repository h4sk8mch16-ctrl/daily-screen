# DAILY SCREEN — 自分用サイト（試作）

DAILY SCREENの記事を蓄積・公開するための静的サイトです。ビルドツール不要の素のHTML/CSSだけで作られているので、GitHub Pagesに置くだけでそのまま動きます。

## フォルダ構成

```
daily-screen-site/
├── index.html                  トップページ（記事一覧カード）
├── style.css                   全ページ共通スタイル
├── articles/
│   ├── illo.html               特集：illo（2026-11-17）
│   └── goo-choki-par.html      特集・創刊号：GOO CHOKI PAR（2026-11-17）
└── assets/                     記事で使う画像（相対パスで参照）
```

## GitHub Pagesで公開する手順

1. **リポジトリを作成する**
   GitHubにログインし、右上の「＋」→「New repository」。リポジトリ名は例えば `daily-screen`。Publicにして「Create repository」。

2. **ファイル一式をアップロードする**
   - 方法A（ブラウザ）：リポジトリ画面で「uploading an existing file」を選び、このフォルダの中身（`index.html`、`style.css`、`articles/`、`assets/`、`README.md`）をドラッグ＆ドロップしてコミットする。フォルダごとドラッグすれば階層も保持されます。
   - 方法B（gitコマンド）：このフォルダで `git init` → `git add .` → `git commit -m "init"` → リポジトリをリモートに設定して `git push`。

3. **Pagesを有効にする**
   リポジトリの **Settings → Pages** を開き、Build and deployment の Source を「Deploy from a branch」、Branch を `main` / `(root)` にして Save。1〜2分で公開されます。

4. **公開URL**
   `https://ユーザー名.github.io/リポジトリ名/`
   （例：ユーザー名が `sekiya`、リポジトリ名が `daily-screen` なら `https://sekiya.github.io/daily-screen/`）

## 毎日の記事追加の流れ

1. 新しい記事を `articles/` に1ファイル追加する（既存記事のHTMLをコピーして中身を差し替えるのが早い）。
2. 記事で使う画像は `assets/` に入れ、HTMLからは `../assets/ファイル名` の相対パスで参照する。
3. `index.html` のカード一覧に、新記事へのカードを1つ追加する（サムネイル画像・タイトル・日付・コーナー名）。
4. 変更をコミット／push（またはブラウザからアップロード）すれば、数分で自動的にサイトへ反映されます。

## デザインについて

亀倉雄策の日本モダニズム（平色・余白・限定色＝クリーム地／朱／黒／金、強いタイポグラフィ）を基調に、安田昂弘のミニマルな情報整理（グリッド感）を重ねたスタイルです。本文幅は最大700px、スマホでも読みやすいレスポンシブ対応です。
