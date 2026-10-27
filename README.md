# Teapot Router（ティーポットルーター）

**開発者向け AI モデル API ゲートウェイ** — 1つのキーで、Claude Code と OpenAI SDK の両方を1つのエンドポイントへ。

公式サイト: <https://teapotrouter.com/ja>

## できること

- **デュアルプロトコル**: Anthropic Messages（Claude Code 互換）と OpenAI Chat Completions（`/v1`）を同一キーで利用可能
- **従量課金・価格全公開**: モデル単価を全公開。免ログインの JSON 価格 API（`/api/pricing`）も提供
- **リクエスト単位のコスト履歴**: モデル・トークン数・金額を毎回記録。API 利用コストが透明に
- **組織キー発行と監査ログ**: チームでキー発行権限と利用記録を分離管理
- **マルチアップストリーム自動フェイルオーバー**: 上流障害時に自動切り替え

## クイックスタート（Claude Code）

```bash
export ANTHROPIC_BASE_URL=https://api.teapotrouter.com
export ANTHROPIC_AUTH_TOKEN=sk-xxxx
claude
```

## クイックスタート（OpenAI SDK / Codex CLI）

```bash
export OPENAI_BASE_URL=https://api.teapotrouter.com/v1
export OPENAI_API_KEY=sk-xxxx
```

既存の OpenAI 互換 SDK は `base_url` を差し替えるだけでそのまま動きます。

## 料金

従量課金（プリペイド制、$1 からチャージ可能）。
価格表: <https://teapotrouter.com/ja> ／ JSON: <https://teapotrouter.com/api/pricing>

## このプロジェクトについて

- 個人開発プロジェクトです
- 名称は HTTP ステータスコード 418 "I'm a teapot" から。ロゴは「418 を潰してティーポットにした」ものです 🫖
- お問い合わせ: support@teapotrouter.com
- 組織: <https://github.com/teapot-router>
