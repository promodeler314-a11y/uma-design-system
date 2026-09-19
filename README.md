# uma-design-system

ウマ娘関連ツール（レースエミュレータ、F-13、ローテーション最適化）の共通デザイン。
各リポジトリに git submodule（design-system/）として取り込んで使う。

## 編集のルール
- 編集はこのリポジトリを単独で clone したフォルダでのみ行う。各リポジトリの design-system/ の中では編集しない
- 変更後は push し、各リポジトリで git -C design-system pull → 同期スクリプトの実行 → コミットの順に反映する
