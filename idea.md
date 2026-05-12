# claude-website-generator

**GitHubリポジトリ：** https://github.com/Cyberdog-AI-Lab/claude-website-generator
**ステータス：** 開発中（SKILL.md サンプル作成済み・未検証）

## なぜ作るか

非エンジニア（営業・総務・フリーランサー・学生）が、コード・CSS・専門用語を一切知らなくても、
Claude に話しかけるだけでプロ品質のウェブサイトを公開できることを証明する。

既存のノーコードツール（Wix・STUDIO）との違いは「対話で決まる」点。
「温かみがある感じで」「お問い合わせフォームも欲しい」という言葉が、
そのままデザインと機能に変換される。

## 含めたい機能・構成

- **2スキル構成：** claude-website-generator（メイン）＋ claude-design-system（外部スキル）
- **Phase 0：** OS 判定 → GitHub/Vercel セットアップ → Vercel CLI ログイン（スキルが自動実行）
- **Phase 1：** 6ステップのヒアリング（目的 → ページ → コンテンツ → デザイン → 機能 → 画像）
- **Phase 2：** Next.js + Tailwind + shadcn/ui プロジェクト自動生成
- **Phase 3：** プレビュー自動起動 → 自然言語で修正 → ホットリロード反映
- **Phase 4：** ビルドエラー自動修正 → GitHub push → Vercel デプロイ
- **Phase 5：** カスタムドメイン案内（ドメインの概念説明から DNS 設定まで）

## 議論・経緯ログ

- 2026-05-05：テーマ立ち上げ。対象ユーザー・技術スタック・2スキル構成を決定
- 2026-05-05：ラフスキル設計書を作成（`research/claude-website-generator/skill-design-draft.md`）
- 2026-05-08：Phase 別の詳細設計を決定（OS分岐・ヒアリング順番・コマンド一式・エラー自動修正方針）
- 2026-05-08：SKILL.md サンプルを `oss/claude-website-generator/` に作成
