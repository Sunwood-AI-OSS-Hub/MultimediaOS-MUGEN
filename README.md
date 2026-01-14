<div align="center">

<img src="assets/header.svg" alt="fal-ai-multimedia-workspace Header" width="800"/>

### fal.ai APIを使ったマルチメディア制作ワークスペース

[![License: MIT](https://img.shields.io/badge/License-MIT-blue.svg)](LICENSE)
[![GitHub](https://img.shields.io/badge/GitHub-View-success?style=flat-square&logo=github)](https://github.com/Sunwood-ai-labs/fal-ai-multimedia-workspace)
[![TypeScript](https://img.shields.io/badge/TypeScript-5.0-blue?style=flat-square&logo=typescript)](https://www.typescriptlang.org/)
[![fal.ai](https://img.shields.io/badge/fal.ai-API-purple?style=flat-square)](https://fal.ai)

画像生成・動画制作・画像編集をClaude Codeとfal.ai APIで行うマルチメディア制作ワークスペース。

</div>

---

## ✨ 概要

`fal-ai-multimedia-workspace` は、fal.ai APIを使ったマルチメディア制作を効率的に行うためのClaude Codeワークスペースです。

- **画像生成**: Qwen Image 2512で高品質な画像を生成
- **動画制作**: LTX-2で画像から動画を作成
- **画像編集**: Qwen Image Editで既存の画像を編集

Claude Code Skillsと組み合わせることで、自然言語で指示を出すだけでプロフェッショナルなマルチメディアコンテンツを作成できます。

---

## 📦 特徴

<div align="center">

| 機能 | 説明 |
|:------:|------|
| **画像生成** | テキストプロンプトから高品質な画像を生成 |
| **動画制作** | 画像から動画を自動生成 |
| **画像編集** | 既存の画像を自然言語で編集 |
| **Claude Code統合** | スラッシュコマンドで操作可能 |

</div>

---

## 🚀 セットアップ

### 要件

- Node.js 20+
- pnpm
- fal.ai APIキー

### インストール

1. リポジトリをクローン

```bash
git clone https://github.com/Sunwood-ai-labs/fal-ai-multimedia-workspace.git
cd fal-ai-multimedia-workspace
```

2. Claude Code Skillsのセットアップ

```bash
# Skillsディレクトリにfal-aiスキルを作成
mkdir -p .claude/skills/fal-ai
```

3. 環境変数の設定

```bash
# .envファイルを作成
cp .env.example .env

# .envファイルにAPIキーを設定
# FAL_KEY=your_api_key_here
```

4. 依存関係のインストール

```bash
# Skillsスクリプト用の依存関係をインストール
cd .claude/skills/fal-ai/scripts
pnpm install
```

---

## 📁 構造

```
fal-ai-multimedia-workspace/
├── .claude/
│   └── skills/
│       └── fal-ai/              # fal.aiスキル
│           ├── SKILL.md
│           ├── references/
│           └── scripts/
├── assets/                      # ヘッダー画像等
├── outputs/                     # 生成物の保存場所
│   ├── images/                 # 生成画像
│   └── videos/                 # 生成動画
├── projects/                    # プロジェクト別の作業ディレクトリ
├── .env.example                 # 環境変数テンプレート
├── .gitignore
├── README.md
└── LICENSE
```

---

## 📖 使用法

### Claude Codeで実行

```bash
# 画像生成
/fal-ai generate-image "A beautiful sunset over mountains" --size landscape_16_9

# 画像編集
/fal-ai edit-image photo.jpg "Make the sky blue and cloudy"

# 動画生成
/fal-ai image-to-video photo.jpg --duration 5 --fps 24
```

### スクリプト直接実行

```bash
# 画像生成
node .claude/skills/fal-ai/scripts/generate-image.ts "A beautiful sunset" --size landscape_16_9

# 画像編集
node .claude/skills/fal-ai/scripts/edit-image.ts photo.jpg "Make the sky blue"

# 動画生成
node .claude/skills/fal-ai/scripts/image-to-video.ts photo.jpg --duration 5
```

---

## 🎨 プロジェクト構成

### outputs/

生成された画像や動画を保存するディレクトリです。

```
outputs/
├── images/
│   ├── generated/              # 生成された画像
│   └── edited/                 # 編集された画像
└── videos/
    └── generated/              # 生成された動画
```

### projects/

プロジェクト別に作業ディレクトリを管理できます。

```
projects/
└── my-project/
    ├── inputs/                 # 入力画像
    ├── outputs/                # 出力ファイル
    └── prompts/                # プロンプトの記録
```

---

## 🔧 fal.ai モデル

### Qwen Image 2512 (画像生成)

- モデルID: `fal-ai/qwen-image-2512/lora`
- LoRA推論エンドポイント
- 高品質なテキスト描画、リアルなテクスチャ生成

### Qwen Image Edit 2511 (画像編集)

- モデルID: `fal-ai/qwen-image-edit-2511/lora`
- 自然言語で画像を編集
- 編集の強さを調整可能

### LTX-2 (動画生成)

- モデルID: `fal-ai/ltx-2/image-to-video/fast`
- 画像から動画を高速生成
- カスタムの動きをプロンプトで指定可能

---

## 🤝 貢献

貢献を歓迎します！

1. リポジトリをフォーク
2. ブランチを作成 (`git checkout -b feature/amazing-feature`)
3. コミット (`git commit -m 'Add amazing feature'`)
4. プッシュ (`git push origin feature/amazing-feature`)
5. プルリクエストを作成

---

## 📄 ライセンス

MIT License - see the [LICENSE](LICENSE) file for details.

---

## 🙏 謝辞

- [fal.ai](https://fal.ai) - API提供
- [Claude Code](https://claude.com/claude-code) - コーディングアシスタント

---

<div align="center">

Made with ❤️ by [Sunwood-ai-labs](https://github.com/Sunwood-ai-labs)

</div>
