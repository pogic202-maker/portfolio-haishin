# AI Dev Portfolio — 川合 彰

AI ツール(Claude Code / ChatGPT など)を活用して制作した開発成果物のポートフォリオサイト。

- **公開URL**: https://pogic202-maker.github.io/portfolio-haishin/
- **リポジトリ**: https://github.com/pogic202-maker/portfolio-haishin
- **デザインテーマ**: ダーク × サイバーパンクネオン
- **AI 活用プロセス**: [PROMPTS.md](PROMPTS.md) を参照

## 構成

```
portfolio-haishin/
├── index.html      # 単一ページ(Hero / About / Works / Stats / Footer)
├── style.css       # デザイントークン・全スタイル定義
├── image/          # 作品スクリーンショット・生成画像
├── README.md
├── PROMPTS.md      # AI への依頼戦略・改善プロセスの記録
└── .gitignore
```

## 使用技術

- HTML / CSS / Vanilla JavaScript(ビルドツール不使用)
- フォント: Inter / JetBrains Mono(Google Fonts)
- ホスティング: GitHub Pages(`main` ブランチ / ルート)

## 設計判断

| 観点 | 採用 | 理由 |
|---|---|---|
| ビルドレス(単一HTML+CSS+JS) | ✅ | 提出物の検証性・保守性を優先。Node等の依存なしで誰でも開ける |
| ダーク × サイバーパンク | ✅ | "AI開発"のテーマと整合。NanoBanana Pro 生成画像で世界観統一 |
| CSS 変数(`:root`)でトークン化 | ✅ | カラー・余白・フォントを一元管理し、デザイン変更コストを最小化 |
| GitHub Pages 手動アップロード運用 | ✅ | 個人提出物の運用としては最も簡素。1ファイル単位で差し替え可能 |
| `prefers-reduced-motion` 対応 | ✅ | アクセシビリティ配慮。motion sensitive ユーザーへの配慮 |
| `:focus-visible` 強化 | ✅ | キーボード操作時の可読性を確保 |

## 検証

- ローカルプレビューサーバ(`python -m http.server`)上で、
  デスクトップ(1280px) / タブレット(768px) / モバイル(375px) の各幅で表示確認を実施
- ハンバーガーメニューの開閉・キーボード操作(Tab / Esc)・スキップリンクが意図通り動作することを確認
- ブラウザのコンソールエラー・ネットワーク失敗ともに 0 件であることを確認

## 改善履歴

| バージョン | 主な対応 |
|---|---|
| **初級**(2026-05-29) | 初回公開・基本構成(Hero/About/Works/Stats)・NanoBanana Pro 画像導入 |
| **中級**(2026-05-30) | meta description / OGP / Twitter Card / favicon 追加、画像パス整合チェック、ルート重複画像削除、README / .gitignore 追加、Works カードの "クリック誤認" を除去 |
| **上級**(2026-05-30) | ハンバーガーメニュー追加、タブレット用ブレークポイント追加、Hero モバイル背景位置調整、タップ領域 44px 確保、Safe Area 対応、`prefers-reduced-motion` / `:focus-visible` / `skip-link` / `<main>` ランドマーク導入、Works 説明文を機能・工夫主導の文言へ刷新、PROMPTS.md 新設 |

## 今後の改善案

- **画像最適化(WebP化)**: `nanobanana-hero.png`(1.7MB) / `nanobanana-about.png`(1.59MB) を WebP+リサイズで 200〜350 KB目安まで圧縮し、LCP 改善
- **favicon 専用ファイル化**: 現状 `nanobanana-about.png` を流用しており、タブ表示のために毎回 1.6MB ダウンロードが走る。`favicon.ico` / 32×32 PNG への差し替え
- **OGP 画像専用化**: 1200×630 の専用画像を作成し、`og:image:width` / `og:image:height` / `og:image:alt` を明示
- **Lighthouse 計測**: Performance / Accessibility / Best Practices / SEO の 4 指標を計測し、継続的改善
- **作品の追加**: 現状 2 件。新規作品の追加にあわせて Stats の数値を更新
- **構造化データ(JSON-LD)**: `Person` / `WebSite` で Google 検索結果のリッチ表示

## ローカルプレビュー

任意のローカルサーバで `index.html` を開けば動作します。

```powershell
# 例: Python の簡易サーバ
python -m http.server 8000
# → http://localhost:8000/ をブラウザで開く
```

## 更新運用

ファイル更新は **GitHub Web UI からの手動アップロード** で行います。

1. リポジトリページで対象ファイルを開く
2. 鉛筆アイコン(Edit)または「Add file → Upload files」
3. 編集/差し替え後、`Commit changes` でコミット
4. 数十秒〜1分ほどで GitHub Pages に反映

## ライセンス

掲載作品の権利は作者(川合 彰)に帰属します。
