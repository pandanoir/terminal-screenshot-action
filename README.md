# Terminal Screenshot Action

[VHS](https://github.com/charmbracelet/vhs) を使ってターミナルのスクリーンショットを撮る GitHub Action。
ffmpeg によるリサイズにも対応。

## Usage

```yaml
- uses: naoto/terminal-screenshot-action@v1
  with:
    vhs-tape: .github/demo.tape
    resize-width: "1200"
```

リサイズ対象の画像は `.tape` ファイル内の `Screenshot` / `Output` コマンドから自動検出されます。

## Inputs

| Name | Required | Default | Description |
|------|----------|---------|-------------|
| `vhs-tape` | Yes | - | VHS `.tape` ファイルのパス |
| `resize-width` | No | `0` | リサイズ後の幅 (px)。`0` でスキップ |
| `vhs-version` | No | `latest` | インストールする VHS のバージョン |

## Requirements

- `ubuntu-latest` ランナー (apt-get を使用)

## Example

```yaml
jobs:
  screenshot:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v4
      - uses: naoto/terminal-screenshot-action@v1
        with:
          vhs-tape: .github/demo.tape
          resize-width: "1200"
```
