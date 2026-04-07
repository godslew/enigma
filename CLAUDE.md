# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## リポジトリ概要

godslew の汎用 Claude Code スキル マーケットプレイス。Claude Code のプラグインシステムを通じてスキルを配布する。

## アーキテクチャ

```
.claude-plugin/marketplace.json   ← マーケットプレイス定義（プラグイン一覧・バージョン）
plugins/
  <plugin-name>/
    .claude-plugin/plugin.json    ← プラグインメタデータ
    README.md
    skills/
      <skill-name>/
        SKILL.md                  ← スキル定義（YAML frontmatter + Markdown本文）
```

- `marketplace.json`: マーケットプレイス全体の定義。新しいプラグインを追加する際はここの `plugins` 配列にエントリを追加する
- `plugin.json`: 各プラグインのメタデータ（name, version, description）
- `SKILL.md`: スキル本体。YAML frontmatter に `name`, `description`, `allowed-tools` を定義し、本文にスキルの内容を記述する

## スキル追加時の規約

- SKILL.md の `description` フィールドにはトリガーフレーズ（`Use when user says "..."` 形式）を含める
- `allowed-tools` でスキルが使用できるツールを明示的に制限する
- スキルは特定言語に依存しない汎用的な原則として記述する（言語固有の規約はユーザーの `~/.claude/rules/` に配置）
