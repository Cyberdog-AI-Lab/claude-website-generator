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

## 実際の利用例 — エステサロンのホームページ

非エンジニアのエステサロンオーナーが、コードを一切書かずにサイトを公開した実際の会話例です。

> 公開済みサイト：[https://luce-salon.vercel.app](https://luce-salon.vercel.app)
> ソースコード：[https://github.com/hayukataishi/luce-salon](https://github.com/hayukataishi/luce-salon)

---

### Phase 0 — 環境セットアップ

まずOSとNode.jsを自動確認。Mac・Node.js v25.9.0が検出されたため、インストール案内はスキップ。

```
Claude：「GitHubというサービスのアカウントはお持ちですか？
         サイトのデータを保存する場所として使います。」

オーナー：「GitHubって聞いたことないです…持ってないと思います。」

Claude：「https://github.com にアクセスして『Sign up』から登録してください。
         メールアドレス・パスワード・ユーザー名を入力するだけです。
         確認メールのリンクをクリックしたら完了です。」

オーナー：「終わりました！」

Claude：「次に Vercel のアカウントはありますか？
         作ったサイトをインターネット上に公開するために使います。」

オーナー：「それも持ってないです〜」

Claude：「https://vercel.com にアクセスして
         『Sign Up』→『Continue with GitHub』をクリックしてください。
         GitHubと連携するだけで登録完了です。」

オーナー：「できました！」
```

GitHub・Vercel の準備完了後、スキルが Vercel CLI を自動インストール。

```bash
# スキルが自動実行
npm install -g vercel   # → Vercel CLI 53.3.2 インストール完了
```

---

### Phase 1 — ヒアリング（全6問）

**① サイトの目的**

```
Claude：「どんなサイトを作りたいですか？」

オーナー：「私、恵比寿でエステサロンをやっていて。
           フェイシャルと小顔矯正が専門なんです。
           インスタはやってるんですけど、ちゃんとしたホームページがなくて…
           お客様に料金とかメニューを見やすく伝えたいんです。
           あと新規のお客様にも来てもらいたくて。」

Claude：「『恵比寿のエステサロンの紹介・集客サイト』ですね。承知しました！」
```

**② ページ構成**

```
Claude：「どんなページが必要か一緒に考えましょう。
         ・トップページ（最初に開くページ）
         ・メニュー・料金ページ
         ・サービス紹介
         ・サロンについて（プロフィール・こだわり）
         ・アクセス・予約
         ・お問い合わせ
         必要そうなものを教えてください。」

オーナー：「トップページと、メニュー・料金、あとサロンのこだわりを伝えるページ、
           アクセスとお問い合わせは欲しいです。5ページくらいかな。」
```

**③ コンテンツ（テキスト）**

```
Claude：「各ページに載せたい内容・文章を教えてください。」

オーナー：「サロン名は『Luce（ルーチェ）』です。イタリア語で『光』って意味で。
           メニューはフェイシャルコース60分15,000円、小顔矯正45分12,000円、
           ハンドトリートメント30分6,000円の3つ。
           こだわりは『素肌のきれいさを引き出す』をテーマにしてます。
           刺激の少ない天然成分のコスメだけ使ってて、
           完全予約制で1日4名限定なんです。
           住所は恵比寿で、予約はInstagramのDMで受け付けてます。」
```

**④ デザイン・雰囲気**

```
Claude：「サイトの雰囲気はどんなイメージですか？
         ・温かみがある、やさしい感じ
         ・クール、スタイリッシュ
         ・シンプル、清潔感がある
         ・ポップ、明るい、元気な感じ
         ・ナチュラル、オーガニック」

オーナー：「シンプルで清潔感があって、でも温かみもあるといいな。
           色はベージュとかオフホワイト系が好きです。」
```

**⑤ 機能要望**

```
Claude：「サイトに組み込みたい機能はありますか？
         ・問い合わせを受け付けたい（メール）
         ・SNS（Instagram・X）へのリンクを置きたい
         ・Googleマップで場所を見せたい
         ・写真・作品をきれいに並べて表示したい
         ・動きやアニメーションをつけたい」

オーナー：「インスタへのリンクは絶対欲しいです！
           あと地図も。問い合わせフォームもあったら嬉しいです。」
```

**⑥ 画像素材**

```
Claude：「サイトに使いたい写真や画像はありますか？」

オーナー：「今日は持ってないです…フリー素材でいいです！」
```

**確認サマリー**

```
Claude：「ありがとうございます。以下の内容でサイトを作り始めます。確認してください。

         ・目的：恵比寿エステサロン「Luce」の紹介・集客サイト
         ・ページ：トップ・メニュー料金・サロンのこだわり・アクセス・お問い合わせ（5P）
         ・デザイン：シンプル＋温かみ、ベージュ・オフホワイト系
         ・機能：Instagramリンク・Googleマップ・お問い合わせフォーム
         ・画像：フリー素材を使用

         よければ『OK』と言ってください。」

オーナー：「OK！お願いします！」
```

---

### Phase 2 — 設計・生成

**デザイントークン決定**

「シンプル×温かみ＋ベージュ」のキーワードから warm/neutral ミックストーンを選定。

| 項目 | 設定値 |
|------|--------|
| カラートーン | ベージュ・オフホワイト系（oklch ベース） |
| プライマリカラー | `oklch(0.55 0.06 60)`（ウォームブラウン） |
| 背景色 | `oklch(0.99 0.005 80)`（オフホワイト） |
| 見出しフォント | Noto Serif JP |
| 本文フォント | Noto Sans JP |
| 角丸 | 0.5rem（控えめ） |

**プロジェクトスラッグ**：`luce-salon`

**スキルが自動実行したコマンド**

```bash
npx create-next-app@latest luce-salon \
  --typescript --tailwind --eslint --app --src-dir --no-git

cd luce-salon
npx shadcn@latest init --defaults
npx shadcn@latest add button card accordion form input textarea
npm install lucide-react framer-motion react-hook-form @hookform/resolvers zod
```

**生成したファイル構成**

```
src/
├── app/
│   ├── layout.tsx          # Noto フォント設定・メタデータ
│   ├── page.tsx            # トップ（ヒーロー・3つのこだわり・CTAバナー）
│   ├── menu/page.tsx       # メニュー・料金（3メニューカード）
│   ├── concept/page.tsx    # サロンのこだわり（交互レイアウト）
│   ├── access/page.tsx     # アクセス（住所・営業時間・Google Maps）
│   └── contact/page.tsx    # お問い合わせフォーム（zod バリデーション）
├── components/
│   ├── layout/
│   │   ├── Header.tsx      # ナビゲーション（ハンバーガーメニュー付き）
│   │   └── Footer.tsx      # フッター・SNSリンク
│   └── ui/
│       └── InstagramIcon.tsx  # カスタムSVGアイコン（後述）
└── app/globals.css         # デザイントークン（CSS変数）
```

---

### Phase 3 — プレビュー確認

スキルが dev サーバーを自動起動してブラウザを開く。

```bash
npm run dev -- --port 3001   # ポート競合のため 3001 で起動
open http://localhost:3001
```

```
Claude：「サイトのプレビューが表示されました。
         どこかを変えたい場合は自由に教えてください。
         問題なければ『OK』と言っていただければデプロイに進みます。」

オーナー：「わあ、すごい！思ったよりちゃんとしてる！じゃあこのままOKです！」
```

---

### Phase 4 — デプロイ

**ビルドエラーの自動検出・修正**

`npm run build` 実行時に3種のエラーが検出され、スキルが自動修正した。

| エラー | 原因 | 修正内容 |
|--------|------|----------|
| `Export Instagram doesn't exist` | インストール済み lucide-react のバージョンに `Instagram` アイコンが未収録 | カスタム SVG コンポーネント `InstagramIcon.tsx` を作成して差し替え |
| `Type error: ease: string is not assignable` | framer-motion の `ease` プロパティに文字列リテラルを渡していた | `ease: "easeOut"` の指定を削除（デフォルト値を使用） |
| `Property 'asChild' does not exist` | shadcn init が生成した Button が base-ui ベースで `asChild` 非対応 | `buttonVariants()` を `<a>` / `<Link>` に直接適用する方式に変更 |

3回のビルド試行で全エラーを解消。

**GitHubリポジトリの作成**

```
Claude：「リポジトリとは、サイトのデータをまとめて保存する『フォルダ』のようなものです。
         GitHubというサービスの中に作ります。

         ① GitHub にログイン
         ② 右上の『＋』ボタン →『New repository』をクリック
         ③ Repository name に『luce-salon』と入力、Public を選ぶ
         ④ 『Create repository』ボタンを押す

         作成完了したら画面に表示される URL を教えてください！」

オーナー：「作りました。これであってますか？
           https://github.com/hayukataishi/luce-salon」

Claude：「バッチリです！リポジトリが確認できました。
         次はサイトのデータをそこに送り込みます。そのままお待ちください！」
```

スキルが URL を検証（HTTP 200 を確認）した上で push を実行。

```bash
git remote add origin https://github.com/hayukataishi/luce-salon.git
git add .
git commit -m "Initial commit: Luce salon website"
git branch -M main
git push -u origin main
# → 20 files changed, 4693 insertions
```

**Vercel デプロイ**

初回は認証トークン切れのため `vercel login` を実行。ブラウザで GitHub 連携を承認後、自動でデプロイ。

```bash
vercel login    # ブラウザでGitHub認証
vercel --prod --yes
```

```
Building: ✓ Compiled successfully in 10.0s
Building: ✓ Generating static pages (8/8)
Aliased: https://luce-salon.vercel.app
```

**完了**

```
Claude：「公開できました！🎉

         あなたのサイトのURLはこちらです：
         https://luce-salon.vercel.app

         このURLをそのままご利用いただけます。
         自分だけのドメイン（例：luce-salon.com）を使いたい場合は、
         追加の設定ができます。使いたいですか？」
```

**所要時間**：ヒアリング〜公開まで約30分（GitHub・Vercel アカウント作成含む）

---

## 開発・研究

[Cyberdog AI Lab](https://github.com/Cyberdog-AI-Lab) が研究・開発しています。

> AIパラダイムシフトを自ら体現し、次世代エンジニアの新しい働き方を創出する

---

## ライセンス

MIT
