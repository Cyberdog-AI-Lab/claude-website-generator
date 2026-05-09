# claude-website-generator

> 話すだけで、ウェブサイトが公開される

「どんなサイトを作りたいか」を Claude に話すだけで、Next.js × Vercel のウェブサイトが公開される Claude Code スキルです。

コード・CSS・専門用語の知識は一切不要。
環境セットアップからデプロイ・ドメイン設定まで、すべてをスキルが担います。

---

## デモ

```
あなた：「カフェの紹介サイトを作りたい。温かみのある雰囲気で。」

Claude：「どんなページが必要ですか？」
         ↓（6ステップのヒアリング）
Claude：「プレビューを確認してください。」
         ↓（修正ループ）
Claude：「公開できました！🎉
         https://cafe-haru.vercel.app」
```

---

## インストール

```bash
git clone https://github.com/Cyberdog-AI-Lab/claude-website-generator
cd claude-website-generator
```

Claude Code でこのフォルダを開くと、スキルが自動的に認識されます。

---

## 前提条件

- [Claude Code](https://claude.ai/code) がインストール済みであること

Node.js・GitHub・Vercel のセットアップはスキルが案内します。

---

## 使い方

Claude Code で以下のように話しかけるだけです：

```
「ホームページを作りたい」
「ポートフォリオサイトを作って」
「お店の紹介ページが欲しい」
「自己紹介サイトを作りたい」
```

スキルが 5 フェーズのガイドを開始します。

---

## フェーズの流れ

| フェーズ | 内容 |
|--------|------|
| 0. 環境セットアップ | OS確認・Node.js / GitHub / Vercel の準備（スキルが案内） |
| 1. ヒアリング | 目的・ページ構成・コンテンツ・デザイン・機能・画像を対話で収集 |
| 2. 設計・生成 | デザイントークン決定・Next.js プロジェクト自動生成 |
| 3. プレビュー確認 | ローカルサーバー自動起動・自然言語で修正 |
| 4. デプロイ | ビルドエラー自動修正・GitHub push・Vercel 公開 |
| 5. カスタムドメイン | ドメイン取得案内・DNS 設定まで一気通貫（オプション） |

---

## 生成されるサイトの技術スタック

| 役割 | 技術 |
|------|------|
| フレームワーク | Next.js 15（App Router） |
| スタイリング | Tailwind CSS v4 |
| UI コンポーネント | shadcn/ui |
| アイコン | Lucide React |
| アニメーション | Framer Motion（必要な場合） |
| フォーム | Formspree + React Hook Form |
| デプロイ | Vercel |

---

## ディレクトリ構成

```
claude-website-generator/
├── README.md
└── .claude/
    └── skills/
        └── claude-website-generator/
            └── SKILL.md   ← Claude スキル本体
```

---

## 開発・研究

[Cyberdog AI Lab](https://github.com/Cyberdog-AI-Lab) が研究・開発しています。

> AIパラダイムシフトを自ら体現し、次世代エンジニアの新しい働き方を創出する

---

## ライセンス

MIT
