# イラストスタイルガイド

記事用イラストをHiggsfield（`generate_image`、モデル: `nano_banana_pro`）で
生成する際のプロンプトのひな形。今回の試行錯誤で分かった条件をまとめてある。

## 運用ルール

- **生成は都度、人間の確認を得てから実行する。** クレジットを消費するため、
  スキル側で自動的に大量生成はしない
- スキルが行うのは「どんなイラストが必要か」「どんなプロンプトにするか」の
  **提案まで**。生成ボタンを押す判断は人間が行う
- 生成結果はこの環境から直接ダウンロードできない（ネットワークポリシーにより
  `cloudfront.net` 等のCDNへの直接アクセスがブロックされる）。
  人間が画像を保存し、チャットに直接アップロードしたものを記事に組み込む

## 基本トーン

- **配色**：パステルポップ（ソフトピンク、ミントグリーン、ラベンダー、
  ベビーブルー、クリーム）
- **線**：太めで丸みのあるフレンドリーな輪郭線。グラデーション・写実表現は使わない
- **画風**：フラットイラスト。かわいい・親しみやすい雰囲気

## 髪を描くときの注意（重要）

過去に「ゴキブリみたいで気持ち悪い」という指摘を受けた経験から、以下を必ず守る。

- 毛の**断面図・解剖学的な描写は使わない**（NG例：層構造で成分が浸透する図）
- **虫の脚のような分節・セグメント状の形は避ける**
- 「髪」だと一目でわかるように、次の要素を入れる：
  - 頭皮・根元にあたる、丸みのある小さな起点の形
  - そこから流れる**毛束（目安3本）**。房になった状態で表現する
  - 毛先は自然に細くなる（テーパーする）
  - 毛束に沿った**細い筋（ストランドライン）**を入れて質感を出す
  - ツヤを出したい場合は、毛束に沿ったハイライトの線を1本入れる

## Before/After比較図のひな形プロンプト

```
Cute pop-style flat illustration, before/after two-panel comparison,
clearly depicting HAIR (not abstract ribbons). NOT anatomical, no
cross-section, no insect-like or segmented shapes, no legs, no creepy
details. Each panel shows a small soft rounded scalp/root shape at the
top, with a bundle of exactly THREE flowing hair locks hanging down from
it, each lock tapering naturally to a soft pointed tip like real hair.
Draw fine parallel strand lines along each lock so it clearly reads as
hair, not a plain ribbon.
Left panel labeled in Japanese '［Before側のラベル］' shows the three
hair locks looking dull, frizzy and tangled, muted matte color, with
small squiggly frizz lines sticking out near the tips.
Right panel labeled in Japanese '［After側のラベル］' shows the same
three hair locks looking smooth, glossy, and bouncy, vivid pastel color,
with a shiny highlight line along each lock, small sparkle stars, and a
water droplet icon nearby.
Playful pastel color palette (soft pink, mint green, lavender, baby
blue), bold friendly rounded outlines, cute cheerful flat pop
illustration style, high resolution, clean plain background, no
watermark, no extra text besides the two Japanese labels.
```

`aspect_ratio: "16:9"` を指定する。

## アイコンセットのひな形プロンプト（商品カテゴリー等）

```
A set of 4 cute pop-style flat vector icons for ［カテゴリーの説明］,
arranged in a clean 2x2 grid with even spacing: (1) ［アイテム1］,
(2) ［アイテム2］, (3) ［アイテム3］, (4) ［アイテム4］.
Playful pastel color palette (soft pink, mint green, lavender, baby
blue, cream), rounded bubbly shapes, bold friendly outlines, cheerful
cute modern icon design, no gradients, no photorealism, no text or
labels, plain white background, high resolution.
```

`aspect_ratio: "1:1"` を指定する。

## セルフチェック（生成後）

- [ ] 断面図・解剖学的な描写になっていないか
- [ ] 虫・脚のような形に見えないか
- [ ] 「髪」だと一目でわかるか（毛束・毛先・筋・起点があるか）
- [ ] `docs/editorial-policy.md` のコンセプトやトーンと矛盾しないか
