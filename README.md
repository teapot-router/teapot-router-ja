<div align="center">

# ティーポットルーター — コーディングエージェント向け LLM API ゲートウェイ

**キーはひとつ。プロトコルはふたつ。使った分だけ — 残高は永久に失効しません。**

Claude Code・Codex CLI・OpenAI SDK ツールのためのホステッドゲートウェイ: 環境変数 2 つを差し替えるだけで、すべての AI コーディングツールがひとつのエンドポイント・ひとつの残高・リクエスト単位のコスト台帳にまとまります。

[はじめる](https://teapotrouter.com/ja/register) · [料金 — 公開・機械可読 JSON](https://teapotrouter.com/api/pricing) · [ドキュメント](https://teapotrouter.com/ja/docs) · [サービス状況](https://teapotrouter.com/ja/status)

</div>

---

## なぜコーディングエージェントにゲートウェイなのか

Claude Code と OpenAI SDK ツールを併用していると、こうなりがちです: ツールごとにエンドポイントとキーが別々に必要で、請求は毎月のブラックボックス。

ゲートウェイはこの配管を整理します:

| | 直接接続（ベンダーごと） | ゲートウェイ経由 |
| --- | --- | --- |
| エンドポイント & キー | ベンダーごとに 1 組 | **キー 1 つ、プロトコル 2 つ** |
| 請求 | ダッシュボード N 個、月次合計のみ | 残高 1 つ、**リクエスト単位の台帳** |
| コスト可視性 | 「$84 かかった」 | 「あのセッションは $6.20 — 78% は再送されたコンテキスト」 |
| 利用規約 | ベンダーごとのポリシー | ここでは: **残高の有効期限なし**、残額ベースで返金 |

## セットアップ: 環境変数 2 つ

```bash
# Claude Code（Anthropic プロトコル）
export ANTHROPIC_BASE_URL="https://api.teapotrouter.com"
export ANTHROPIC_AUTH_TOKEN="sk-****"

# OpenAI SDK / Codex CLI — 同じキーで /v1 エンドポイント
# base_url = https://api.teapotrouter.com/v1
```

登録 → 初回リクエスト → トラブルシューティングまでのステップバイステップガイド: [teapotrouter.com/ja/docs](https://teapotrouter.com/ja/docs)

## サイトで確認できること

- [【ブログ】Claude Code の請求額はどこへ消えるのか](https://teapotrouter.com/ja/blog/where-does-a-claude-code-bill-go)
- [無料コスト計算ツール（ログイン不要・リアルタイム料金）](https://teapotrouter.com/ja/claude-code-cost-calculator) — サブスク vs 従量課金の損益分岐点がわかる
- **公開料金** — 全モデルの基準単価と実払い額。ログイン不要の JSON エンドポイント（[`/api/pricing`](https://teapotrouter.com/api/pricing)）なので、スクリプトで比較することも
- **モデル別料金ページ** — 例: [claude-opus-5-5](https://teapotrouter.com/ja/pricing/claude-opus-5-5)
- **Claude Code 料金ガイド** — サブスク vs 従量課金 vs ゲートウェイ、実際のコスト計算付き: [ドキュメント](https://teapotrouter.com/ja/docs/claude-code-pricing)
- **トラブルシューティングガイド** — 接続・401・クォータ系エラーを原因別の解決策とマッチング: [ドキュメント](https://teapotrouter.com/ja/docs/claude-code-troubleshooting)

## どんなゲートウェイにも尋ねるべき 2 つの質問（ここも例外ではありません）

- **モデルはどこから調達していますか?** 公式・正規 API チャネルから従量で課金して調達しています。アカウント共有やサブスクの転売はしていません。
- **何をログに記録しますか?** 課金メタデータのみ（モデル・トークン・コスト・レイテンシ）— リクエスト単位の台帳が成り立つのはこのためです。「ゼロログ」の演出はしません。会話内容には触れません。

## 正直な限界

個人開発、最近のローンチ、マーケティング予算なし — 料金エンドポイントは常に稼働中のモデル一覧を返すので、この README を鵜呑みにせず自分で確認してください。マルチアップストリームのフェイルオーバーを内蔵していても、ゲートウェイは依存関係のひとつです。代替経路を残しておいてください。

問い合わせ: support@teapotrouter.com

---

<div align="center">

名前は HTTP ステータスコード 418 "I'm a teapot" から 🫖 — [フルストーリー](https://teapotrouter.com/ja/418)

**[Teapot Router](https://teapotrouter.com/ja)** — Claude Code と GPT のための stability-first AI ゲートウェイ

</div>
