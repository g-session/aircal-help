# aircal-help

[aircal](https://github.com/g-session/aircal) のヘルプ・FAQ・スクリーンショット公開用リポジトリ。

## 中身

- `images/`
  - 使い方ガイド用のスクリーンショット。jsDelivr CDN 経由で
    アプリと Web ヘルプの両方から参照される。
  - 配信元: `https://cdn.jsdelivr.net/gh/g-session/aircal-help@main/images/...`
- `{lang}/index.html`, `{lang}/{guide|faq}/{slug}/index.html`
  - GitHub Pages で公開される使い方ガイド / FAQ の Web 版。
  - 内容は aircal の `lib/assets/l10n/intl_*.arb` を元にスクリプトで自動生成しているため、
    このリポジトリの HTML ファイルを直接編集しないこと。

## 公開URL

### 入口 / 言語選択

https://g-session.github.io/aircal-help/

### 言語別 TOC（使い方ガイド + FAQ 一覧）

| 言語 | URL |
|---|---|
| 日本語 | https://g-session.github.io/aircal-help/ja/ |
| English | https://g-session.github.io/aircal-help/en/ |
| 한국어 | https://g-session.github.io/aircal-help/ko/ |
| 简体中文 | https://g-session.github.io/aircal-help/zh/ |
| 繁體中文 | https://g-session.github.io/aircal-help/zh-Hant/ |
| Español | https://g-session.github.io/aircal-help/es/ |
| Português | https://g-session.github.io/aircal-help/pt/ |
| Français | https://g-session.github.io/aircal-help/fr/ |
| Deutsch | https://g-session.github.io/aircal-help/de/ |
| Bahasa Indonesia | https://g-session.github.io/aircal-help/id/ |
| Italiano | https://g-session.github.io/aircal-help/it/ |
| Tiếng Việt | https://g-session.github.io/aircal-help/vi/ |
| Русский | https://g-session.github.io/aircal-help/ru/ |
| ไทย | https://g-session.github.io/aircal-help/th/ |
| Polski | https://g-session.github.io/aircal-help/pl/ |
| Nederlands | https://g-session.github.io/aircal-help/nl/ |
| Svenska | https://g-session.github.io/aircal-help/sv/ |
| Čeština | https://g-session.github.io/aircal-help/cs/ |
| Norsk bokmål | https://g-session.github.io/aircal-help/nb/ |
| Magyar | https://g-session.github.io/aircal-help/hu/ |
| Bahasa Melayu | https://g-session.github.io/aircal-help/ms/ |

英語の地域変種 (en_GB / en_AU / en_CA) は専用 ARB を持たず、共通の `en` (US) にフォールバックする。

### 個別ページ

各 TOC から辿れるほか、以下のパスで直接アクセスできる:

- 使い方ガイド: `https://g-session.github.io/aircal-help/{lang}/guide/{slug}/`
- FAQ: `https://g-session.github.io/aircal-help/{lang}/faq/{slug}/`

slug の一覧は `resources/generate_help_docs.py` の `GUIDE_PAGES` / `FAQ_PAGES` を参照。

## Native と Web の差異

Native ヘルプにある以下の遷移は Web では実装できないため、トルツメまたは
Web 版の対応ページへのリンクに置き換えている:

- 「サブスクリプションの解除方法」リンク → `/{lang}/faq/cancel-subscription/` へ
- 「プライバシーポリシー」リンク → `g-session.github.io/aircal-privacy/privacy/{lang}/` へ
- 「カラーテーマ」「予定の初期設定」「CarPlay設定」等の設定画面リンク → リンクは外し、ラベル名をそのまま本文に埋め込み
- 「Pro 課金画面」リンク → 完全に削除
- 「フィードバック」リンク → 完全に削除

## 更新方法

aircal リポジトリ側で:

```bash
# ARB を編集後
python3 resources/generate_help_docs.py
```

スクリプトが本リポジトリを clone / pull → 言語ディレクトリを再生成 →
差分があれば commit & push する。`images/` ディレクトリは触らない。
