# uma-design-system

ウマ娘関連ツール（レースエミュレータ、F-13、ローテーション最適化）の共通デザイン。
各リポジトリに git submodule（design-system/）として取り込んで使う。

## 編集のルール
- 編集はこのリポジトリを単独で clone したフォルダでのみ行う。各リポジトリの design-system/ の中では編集しない
- 変更後は push し、各リポジトリで git -C design-system pull → 同期スクリプトの実行 → コミットの順に反映する

## ファイル

| ファイル | 中身 |
| --- | --- |
| `DESIGN.md` | 決めたことと、その理由。未決定事項は 8 節にある |
| `tokens.css` | 色・角丸・書体の CSS 変数（接頭辞は `--uma-`）。値はレースエミュレータの実装から移したもの |

## tokens.css の使い方

`tokens.css` は素の CSS 変数だけを持つ。Tailwind の `@theme` は書かない。
取り込む側が Tailwind とは限らないためである。

暗い表示は `<html data-theme="dark">` で切り替える。属性が無ければ明るい表示になる。

- Tailwind v4 の側（レースエミュレータ）：自分の CSS から `@import` し、`@theme inline` で
  `--color-*` に橋渡しする。コピーも生成もしない
- 素の CSS の側（F-13）：`<link>` か `@import` で読み、`var(--uma-…)` を直接使う
