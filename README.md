# hana_block

花ブロック（コンクリート製装飾ブロック）を **メーカーに custom オーダー製作してもらうための設計図** を作るリポジトリ。図面は HTML + SVG で作図し、A4 landscape で印刷してメーカーに渡す。

## このリポジトリは何か
- 詳しい目的・スコープ・成功基準は [BRIEF.md](./BRIEF.md)
- 用語は [CONTEXT.md](./CONTEXT.md)
- 構造と作り方は [ARCHITECTURE.md](./ARCHITECTURE.md)
- 意匠カタログ・図面の見せ方は [DESIGN.md](./DESIGN.md)

## 構成
```
reference/   参考資料（製品カタログ等）
template/    共通HTML+CSS・部品SVG（作図の土台）
patterns/    意匠ごとの成果物（基本設計図 → 製作図）
```

## 使い方
- 製作図 HTML をブラウザで開き、A4 landscape で印刷してメーカーに渡す。
- 新しい意匠を追加するときは `patterns/<slug>/` を作り、**基本設計図 → 製作図** の順で起こす（slug と命名は DESIGN.md で確定させる）。
