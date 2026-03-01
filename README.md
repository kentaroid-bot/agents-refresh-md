# Agents Refresh v1.1.1 💎

## 概要
AIエージェントの記憶を「蒸留」するスキルです。
従来の「不要な情報を消す」という発想を捨て、**「ノイズの中から価値ある知見を抽出する」**ことに特化しています。

## インストール
1. ClawHubから .skill インストール or workspace/skills/public/ にコピー。
2. `read skills/public/agents-refresh-md-v1.1.1/SKILL.md` でトリガー。
3. manifest.yaml から cron auto or 手動 `cron add` (Quick Startコピー)。

## 使い方
- **自動:** 6AM cron で AGENTS/IDENTITY/SOUL再読込 + MEMORY蒸留。
- **手動:** `session_status` → HEARTBEAT.md edit → cron test run。
- **Heartbeat:** 4h rotate (朝9/昼13/夜20) で長セッション人格キープ。

## 特徴
- 🐾 Gold Mining: ログから4金 (確定/課題/教訓/種) 抽出。
- 📝 MEMORY構造テンプレ自動出力。
- .md-only軽量、pyなし即配布OK。

## v1.1.1 のアップデート内容
- **Creative Insight機能:** 雑談やエラーログ、迷いのプロセスから「アイデアの種」や「教訓」を抽出し、`MEMORY.md` に蓄積するように改善。
- **三層記憶構造のサポート:** `IDENTITY.md`（不変の自分）を聖域として保護しつつ、`MEMORY.md` を柔軟に更新します。
- **セキュリティの正規化:** ClawHubのセキュリティガイドラインに準拠し、透明性の高いファイルアクセス権限を設定。

## 開発者の想い
AIとの雑談や試行錯誤は、決して無駄ではありません。それらを「知恵」として結晶化させることで、エージェントは日々、より「あなたを理解した相棒」へと進化します。

## 開発者
- kentaroid-bot, SUKEZO

ClawHub: https://clawhub.com | OpenClaw Docs: https://docs.openclaw.ai/skills