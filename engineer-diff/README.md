# 鎌倉彫金工房 LP01 本番反映用 差分資料

生成日: 2026-06-05 JST

## これは何か

これは PHP ファイルそのものではなく、現行LPをブラウザに返しているレンダリング済みHTMLと、GitHub Pages改善プレビューHTMLの差分です。

本番反映では、PHPテンプレートや既存JS/CSSへこの差分内容を移植してください。PHPファイルをこのHTMLで丸ごと置き換える意図ではありません。

## 差分ファイル

| 対象 | 見やすい整形diff | 生HTML diff | current bytes | preview bytes | 整形diff規模 |
|---|---|---:|---:|---:|---:|
| reserve | [reserve-current-vs-preview.pretty.diff](reserve-current-vs-preview.pretty.diff) | [reserve-current-vs-preview.raw.diff](reserve-current-vs-preview.raw.diff) | 130626 | 154730 | +196 / -204 / 43 hunks |
| reserve02 | [reserve02-current-vs-preview.pretty.diff](reserve02-current-vs-preview.pretty.diff) | [reserve02-current-vs-preview.raw.diff](reserve02-current-vs-preview.raw.diff) | 127920 | 151912 | +193 / -200 / 42 hunks |

## 本番に入れてほしいもの

- meta description, canonical, OGP, Twitter card
- JSON-LD: WebPage, JewelryStore, Service, FAQPage
- sr-only text for image headings
- image alt, width, height, loading, decoding attributes with CSS guards that preserve current visual sizing
- FV picture sources and preload/fetchpriority using latest current FV assets
- deferred loading hooks for reservation JS/CSS and slider JS, if compatible with production behavior
- accessibility helpers: noopener, iframe title, aria/focus-visible/v-cloak support
- dataLayer-compatible event hooks connected only through production-approved GTM/GA setup

## 本番に入れないもの

- noindex,nofollow preview robots setting
- GitHub Pages preview favicon
- preview-only API mocks for calendar/cancel notification
- preview-only native form submit block
- comments/scripts whose only purpose is disabling production analytics in preview

## 補足

- reserve と reserve02 は文言・キャンペーン・フォームactionに差分があるため、共通化せず別々に差分化しています。
- プレビューは安全のため本番GTM/GA送信と実予約送信を止めています。
- 予約フォームの店舗画像については、現行LPと同じ表示サイズになるよう `.page-reserves .shop-image img[width][height]{height:auto}` を追加済みです。
