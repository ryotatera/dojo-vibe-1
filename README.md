# 当日ページ（受講生が開くページ）

受講生はこのページを開いて、上から順に進めます。
手順・コピー用プロンプト・配布ファイルのダウンロードが1ページに入っています。

```
workshop-page/
├─ index.html      本体（CSS/JS込み・1枚完結）
├─ files/          ダウンロード配布するMD
└─ README.md
```

## 公開前に必ず直すところ

| 場所 | 内容 |
|---|---|
| `index.html` の `REPLACE_TEMPLATE_URL` | **テンプレートリポジトリのURL**に差し替える（STEP1のボタン） |

これだけです。他は差し替え不要。

## GitHub Pages で公開する

1. Public リポジトリを作る
2. `index.html` と `files/` を**ルートに**置いて push
3. Settings → Pages → Deploy from a branch → `main` / `/ (root)`
4. `https://<ユーザー名>.github.io/<リポジトリ名>/` で公開

> ⚠ ダウンロードボタンは**同じ場所に `files/` がある前提**です。`index.html` だけ置くと動きません。

## 受講生に渡すもの（2つだけ）

| # | 渡すもの | 何をする |
|---|---|---|
| 1 | **このページのURL** | 上から順に進める。プロンプトはコピーボタン |
| 2 | **テンプレートリポジトリのURL** | STEP1で `Use this template` する |

テンプレートを複製すれば `CLAUDE.md` も `docs/01_customer.md` も中に入っているので、
**ファイルのダウンロードは必須ではありません。**
ダウンロードは「手元で見たい」「事前に書いておきたい」人向けの補助です。

## 機能

- **3行の入力フォーム（STEP5）** — ページ上で直接書ける
  - 入力すると **`docs/01_customer.md` の完成形がライブでプレビュー**される（入力箇所はオレンジで強調）
  - **「この内容をコピー」** → GitHubの編集画面に貼るだけ（推奨・こちらが速い）
  - **「.md でダウンロード」** → 入力を反映した `01_customer.md` が手元に落ちる
  - 入力内容は `localStorage` に自動保存。リロードしても消えない
- **コピーボタン** — プロンプトをクリップボードへ（HTTP環境でもフォールバックで動作）
- **チェックボックス** — 進捗は `localStorage` に自動保存。リロードしても消えない
- **完了表示** — チェックすると、そのステップが緑色になる
- **2つのゲート** — 実践①の後（4項目）と最後（4項目）。ここで全員をそろえる
- ライト/ダーク両対応、モバイル対応（横スクロールなし）

## 更新のしかた

`files/` の中身は他ディレクトリからのコピーです。元を直したら、コピーし直してください。

```bash
cd dojo-vibe-coding
cp starter-kit/docs/01_customer.md           workshop-page/files/01_customer.md
cp starter-kit/samples/01_customer.sample.md workshop-page/files/01_customer.sample.md
cp starter-kit/CLAUDE.md                     workshop-page/files/CLAUDE.md
cp starter-kit/samples/CLAUDE.sample.md      workshop-page/files/CLAUDE.sample.md
cp WORKSHOP_GUIDE.md                         workshop-page/files/WORKSHOP_GUIDE.md
```
