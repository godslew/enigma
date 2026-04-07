# enigma

godslew の汎用 Claude Code スキル マーケットプレイス。

## プラグイン一覧

| プラグイン | 説明 |
|-----------|------|
| [enigma](plugins/enigma/) | コーディング原則など汎用スキル集 |

## インストール

`settings.json` の `extraKnownMarketplaces` に追加:

```json
"enigma": {
  "source": {
    "source": "github",
    "repo": "godslew/enigma"
  },
  "autoUpdate": true
}
```

`enabledPlugins` に追加:

```json
"enigma@enigma": true
```
