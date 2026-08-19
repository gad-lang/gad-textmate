# gad-textmate

The **Gad language TextMate bundle** — a single, editor-agnostic source of syntax
highlighting and editing support for Gad and its dialects (`.gad`, `.gadt`
template, `.gadx`). Shared by the [VS Code](https://github.com/gad-lang/vscode-gad)
and [IntelliJ](https://github.com/gad-lang/intellij-gad) plugins so both editors
highlight identically.

## Contents

| Path | What |
| --- | --- |
| `syntaxes/gad.tmLanguage.json` | TextMate grammar for `.gad` / `.gadt` (**generated** — see below) |
| `syntaxes/gadx.tmLanguage.json` | TextMate grammar for `.gadx` |
| `language-configuration.json` | Brackets/comments/auto-closing for Gad |
| `gadx-language-configuration.json` | Language configuration for Gadx |
| `schemas/*.schema.json` | JSON schemas for `.gad.yaml` / `.gadide.yaml` config |
| `package.json` | Bundle manifest (declares the languages + grammars) |

## Source of truth

`syntaxes/gad.tmLanguage.json` is **generated** from the Gad compiler vocabulary
by the main [`gad`](https://github.com/gad-lang/gad) repository
(`cmd/internal/pluginsync`), so highlighting always tracks the language — do not
hand-edit it. The other files are authored here directly.

## Use

Consume this repo as a git submodule (the VS Code and IntelliJ plugins do), or
install the npm package `@gad-lang/textmate`. A TextMate/VS Code host reads the
grammars via `package.json` → `contributes.grammars`; the `source.gad` /
`source.gadx` scope names are stable.

## License

MIT — see [`LICENSE`](LICENSE).
