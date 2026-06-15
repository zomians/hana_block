# ARCHITECTURE — 構造と作り

## 全体構造（意匠軸で束ねる）
```
BRIEF.md  CONTEXT.md  ARCHITECTURE.md  DESIGN.md  README.md
docs/adr/                 個別決定の記録（例: 麻の葉の壁厚決定）
reference/                参考資料
  catalog-250707.pdf
template/                 土台（共通HTML+CSS、部品SVG: marker / 寸法線 / spec表 等）
patterns/                 意匠ごとの成果物
  asanoha/                麻の葉
    asanoha-base.svg              基本設計図（幾何構成。麻の葉は数が少ないので1か所に集約）
    asanoha-390-wall-study.svg   壁厚検討図（ADR の根拠）
    <slug>-<size>.html           製作図（例: asanoha-390.html, asanoha-190.html）
  kumiko/                 組子（新規・これから）
    kumiko-base.svg
    <slug>-<size>.html
```

## 命名規則
`patterns/<slug>/` 配下のファイルは `<slug>-<役割>[-<size>].<拡張子>` とし、単体で開いても何の図か分かる自己説明的な名前にする。
- 基本設計図: `<slug>-base.svg`
- 検討記録: `<slug>-<topic>-study.svg`（例: `asanoha-390-wall-study.svg`）
- 製作図: `<slug>-<size>.html`（例: `asanoha-390.html`）

## 工程
各パターンは **①基本設計図 → ②製作図** の順で起こす。基本設計図で壁厚・開口率など寸法を確定し、それを土台に製作図（メーカー提出用）を作る。

## 軸の選定理由
- **意匠軸**で束ねる：同一意匠が複数サイズに展開されるため（麻の葉 = 390 / 190）。サイズ軸だと同一意匠が散る。
- 麻の葉の基本設計はまとまった量がないので、サイズ別に分けず `patterns/asanoha/` に集約する。

## 作り方（軽量・手作図）
- データ駆動の生成器は作らない。**共有テンプレ（`template/`）＋ 手作図**で進める。
- 真実の源：寸法・壁厚・開口率は docs（BRIEF / DESIGN）に、再利用する作図部品は `template/` の部品SVGに持つ。
- 量産フェーズに入ったら生成パイプライン化を再検討する（現時点ではオーバースペック）。
