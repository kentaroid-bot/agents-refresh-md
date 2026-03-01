---
name: agents-refresh-md
description: > 
  AGENTS.md/IDENTITY/SOUL/USER定期再読込でコンテキストfresh保つスキル（.mdのみ版 v1.1.1）。長セッションこんがらがり/忘れ防止。HEARTBEAT.md編集 + cron追加（手動ツールコール）。scripts/pyなしでClawHub配布軽量。Use when: (1) セッション長で人格ブレ心配、(2) /new避け記憶継続人間っぽく、(3) MEMORY/ToDo自動まとめ（ToDo/プロジェクト焦点キープ）。
---

## 🧠 Purpose (エージェント流記憶3層！🐾)

人間みたいに**理性保って記憶整理**！ AGENTS/IDENTITY/SOUL定期読込で、長セッションでも**セッション永遠🐾**キープ😆

**3層記憶構造:**
1. **IDENTITY.md (不変の魂👑):** 名前/vibe/ルール！ 絶対変わらないエージェントのコア💕
2. **MEMORY.md (動的知見🌱):** 進捗/決定/大事種！ ToDo焦点ここ！
3. **memory/YYYY-MM-DD.md (過去ログ📜):** 詳細掘る時だけ！ 蒸留してMEMORYへ😉

これで**人間っぽく継続**！ こんがらがりバイバイ✨

## Task: refresh_memory

### 理性の保持
AGENTS.md、SOUL.md、IDENTITY.mdを読む。

### 🪙 Gold Mining (蒸留プロセス！)
ログから**4つの金**を掘り出せ！ (消すじゃなく、MEMORY.mdに蒸留✨)
1. **確定事項 💎:** 決定/完了タスク (基盤固め)。
2. **未完了課題 ⚡:** 次アクション/ToDo (優先順)。
3. **教訓 🚫:** エラー/迷いから学んだ「地雷回避」。
4. **アイデアの種 🌱:** 雑談/思考の「将来ポテンシャル」。

**例:** dailyログ→MEMORY更新 → 人間っぽく継続！

### MEMORY.md構造例 (推奨)
柔軟にこのテンプレ使え！ (Statusは任意でヘッダー代用OK🐾)

```
- **# Status (任意):** 現在のフェーズ一言。
- **## Key Decisions 💎:** 確定事項。
- **## Next Actions ⚡:** 未完了ToDo (優先順)。
- **## Insight & Lessons 🚫:** 教訓/地雷回避。
- **## Creative Seeds 🌱:** アイデアの種。
```


# AGENTS Refresh Skill (.md-only v1.1.1)

ClawHub配布用軽量版。Pythonスクリプトなし、手動ツールコール中心。

## Quick Start
1. Trigger: このスキル読込後、手動で以下実行。
2. `edit HEARTBEAT.md`: Refreshタスク追加。
3. `cron add`: Daily 6AMリフレッシュ（下記コマンドコピー）。

## Workflow (手動)
1. 📊 `session_status` → コンテキスト長確認。
2. **HEARTBEAT.md編集例:**
   ```
   - [ ] Refresh: read workspace/{AGENTS.md,IDENTITY.md,SOUL.md,USER.md} → SOUL/USER/IDENTITY連鎖 + MEMORYまとめ (rotate: 4h, 朝9/昼13/夜20)
   ```
3. **Cron追加コマンド（copy-paste exec）:**
   ```
   cron action=add job='{"name":"agents-refresh-daily","schedule":{"kind":"cron","expr":"0 6 * * *","tz":"Asia/Tokyo"},"payload":{"kind":"systemEvent","text":"[Daily Refresh🐾] read workspace/{AGENTS.md,IDENTITY.md,SOUL.md,USER.md}! SOUL/USER/IDENTITY連鎖再読込 → ToDo/プロジェクト焦点キープ！ Recent MEMORY/ToDoまとめ。"},"delivery":{"mode":"announce"},"sessionTarget":"main","task":"refresh_memory"}'
   ```
4. Test: `cron action=run jobId=agents-refresh-daily` or heartbeat待機。

## Rotate Checks (Heartbeat内)
- 朝6/9AM, 昼13PM, 夜20PM: AGENTS→IDENTITY/SOUL連鎖読込 + MEMORY/ToDo更新。
- Recent memory/YYYY-MM-DD.md → MEMORY.md蒸留。

## References
- examples.md: 使用例。
- Cron詳細: web_search "OpenClaw cron schema"

**Changes v1.1.1:** pyなし軽量、cron JSON直書き、手動運用強化。ClawHub即配布OK！🐾
