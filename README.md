# 日本古代史 LLM Wiki

Karpathy の「LLM Wiki」パターンを用いて、日本の古代史の理解を深めるための個人ナレッジベースです。
資料を `raw/` に置き、Claude Code に取り込みを依頼すると、Claude が `wiki/` 以下の相互リンクされた Markdown ページを作成・更新します。

## 構成

| パス | 役割 | 書き手 |
|------|------|--------|
| `raw/` | 一次資料（記事・論文・書籍メモ・画像）。変更しない。著作権保護のため Git にはコミットせず、ローカルにのみ保存する | ユーザー |
| `notes/` | Claude が Web 調査で作成した資料メモ（URL・要点・短い引用） | Claude |
| `wiki/` | 要約・人物・遺跡・出来事・論点などの Wiki ページ | Claude |
| `CLAUDE.md` | Wiki の構造・規約・ワークフローを定めるスキーマ | ユーザーと Claude の共同 |

## 使い方

1. 資料を `raw/` に置く（Obsidian Web Clipper を使うと Web 記事を Markdown で保存できます）。
2. Claude Code で「`raw/xxx.md` を取り込んで」と依頼する（Ingest）。
3. 「邪馬台国はどこにあったと考えられている？」のように質問する（Query）。良い回答は `wiki/analyses/` に保存できます。
4. 「古墳時代について調査して」のように依頼すると、Claude が Web 上の資料を集めて `notes/` にメモを作り、Wiki に反映します（Research）。
5. 時々「Wiki を Lint して」と依頼し、矛盾や孤立ページを点検する（Lint）。

## Obsidian での閲覧

このリポジトリのルートを Obsidian の Vault として開いてください。添付ファイルの保存先は `raw/assets/` に設定済みです。
グラフビューで Wiki の全体像を、Dataview プラグインで frontmatter の集計を確認できます。
