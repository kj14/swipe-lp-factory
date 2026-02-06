# LIF-74 SEO/Index 方針調査メモ（ローカル雛形）

- Linear: https://linear.app/tnmrkj/issue/LIF-74
- Title: [Swipe-LP] SEO/Index方針調査（単一URL vs 分割、クローラビリティ、構造化）
- GeneratedAt: 2026-02-06T03:19:59+00:00

## 目的 / Decision
- 単一URL（1ページ内でスワイプ） vs 分割（複数URL）どちらを採るか
- index方針（index/noindex）、canonical、パラメータ方針
- クローラビリティ（JS依存度、SSR/SSG、内部リンク）
- 構造化データ（FAQ/HowTo/Product等）を入れるか

## 調査観点（チェックリスト）
- [ ] Googleのレンダリング/インデックス要件（JS/SPAの注意点）
- [ ] 1URL内で状態が変わるUI（carousel/swipe）をどう解釈するか
- [ ] 分割する場合の情報設計（URL設計、パンくず、内部リンク）
- [ ] canonical/alternate（可能なら）
- [ ] 構造化データ: 必須/任意、誤実装リスク
- [ ] CWV/パフォーマンス観点（LCP/INP/CLS）

## 追加で確認したい質問
1) 検索流入の主要クエリは？（意図は比較/購入/口コミ/機能？）
2) LPはどこまでコンテンツを持つ？（FAQ、料金、事例など）
3) 多言語/地域対応はある？（hreflang必要？）
4) 動的要素はSSR/プリレンダで対応できる？

## 結論（仮）
- （ここに方針を1-2行で書く）

## 次アクション（ローカル）
- [ ] 方針のDecision matrixを作る（単一URL/分割のPros/Cons）
- [ ] 実装上のガードレール（index/canonical/構造化）を箇条書きで定義
