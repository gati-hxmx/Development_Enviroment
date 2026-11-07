# Development_Enviroment

Claude Code と Codex が、Issue から本番リリースまで人の承認を待たずに進める「自走型開発」のテンプレートです。新しいアプリは、このリポジトリを「Use this template」で複製して始めます。

## 何が入っているか

| 場所 | 中身 |
| --- | --- |
| [AGENTS.md](AGENTS.md) | Claude Code と Codex 共通の開発ルール（Claude は [CLAUDE.md](CLAUDE.md) から読み込む） |
| [.agents/skills/](.agents/skills) | 開発の全工程のスキル（triage → spec → … → release）。`.claude/skills/` はそこへのリンク |
| [docs/workflow.md](docs/workflow.md) | スキルのつながりと起動のきっかけ |
| [docs/ai-collaboration.md](docs/ai-collaboration.md) | Claude と Codex の分担、ブランチ、引き継ぎ、利用上限のとき |
| [docs/risk-policy.md](docs/risk-policy.md) | 人が入る条件と自動マージの条件 |
| [docs/stack.md](docs/stack.md) | 技術スタックの基準と標準構成 |
| [docs/setup.md](docs/setup.md) | 最初に人が一度だけ行う設定 |
| [.claude/settings.json](.claude/settings.json) | 権限と hooks（危険な操作を止める、検証が通るまで終わらせない） |
| [.github/workflows/](.github/workflows) | CI、AI の自動起動（Issue・レビュー・CI 失敗・定期実行）、リリース |
| [scripts/](scripts) | `check`（検証）、`notify`（Discord 通知）、`ai`（Codex が上限なら Claude に回す）、`setup-github.sh` |

## 使い方

1. [セットアップ](docs/setup.md) を一度行う（GitHub の Secret とルール、Codex の連携、Discord）
2. Issue に「やりたいこと」を書いて `agent` ラベルを付ける（Issue テンプレートなら自動で付きます）
3. あとは AI が進めます。人に連絡が来るのは [リスク基準](docs/risk-policy.md) の条件に当てはまったときだけです

## 由来

ルールの土台は、Hana（給与・シフト管理）の開発で作った AGENTS.md・共同開発ルール・スキル構成・`scripts/ai` を汎用化したものです。
