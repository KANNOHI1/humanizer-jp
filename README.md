# humanizer-jp

日本語文章の「AIくささ」を検出・除去する Agent Skill（v1.2.0）。
メール・報告書・稟議・提案書・スライド内文言・職務経歴書など、日本語のビジネス文書全般に使う。

- **修理モード**: 既存の文章から AI くさい表現を検出して直す
- **生成モード**: 書く前に 15 パターンを禁止リストとして持ち、書いた後に 4 種の点検をかける

## 構成

- `SKILL.md` — 手順・原則・用途別の注意点
- `references/checklist-ja.md` — 15 パターンの検出辞書、執筆後の点検 A〜D、症状→処方表

## 導入

`humanizer-jp/` フォルダごと、各エージェントの skill ディレクトリに置く。

- Claude Code: `~/.claude/skills/humanizer-jp/`
- Gemini CLI: `~/.gemini/skills/humanizer-jp/`

```bash
git clone https://github.com/KANNOHI1/humanizer-jp.git ~/.gemini/skills/humanizer-jp
```

skill ディレクトリの中にバックアップや作業用コピーを置かないこと（同名 skill の競合になる）。

## 変更履歴

- **1.2.0** — 稟議・報告書・提案書向けの規定を追加（冒頭 3 行に判断事項・期限・規模、主張型の見出し、試算の明記、並べ方による因果の暗示を禁止、リスクの演出を禁止）。スライドのタイトルは主張まで入れる
- **1.1.0** — 話題テスト・拍の点検・短文化バイアスの禁止・症状→処方表・人間主語への書き換えを追加
- **1.0.0** — blader/humanizer と matsuikentaro1/humanizer_academic を日本語に翻訳・統合

## ライセンス

MIT（[LICENSE](LICENSE)）。元にした素材と出典は [NOTICE](NOTICE) を参照。
