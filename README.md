# HERY - Visual Studio Code Extension

Language support for [HERY](https://github.com/AmadlaOrg/hery) (Hierarchical Entity Relational YAML) files.

## Features

### Syntax Highlighting

- HERY reserved properties (`_type`, `_extends`, `_meta`, `_body`, `_requires`) highlighted as keywords
- Entity URIs with version detection (`amadla.org/entity/application@v1.0.0`)
- Version constraints (`@v1.0.0`, `@^v1.0.0`, `@latest`)
- Full YAML syntax support (strings, numbers, booleans, null, anchors, aliases, block scalars, flow collections)
- Comments, document separators (`---`, `...`)

### Snippets

| Prefix | Description |
|--------|-------------|
| `hery` | New entity with type, meta, and body |
| `hery-min` | Minimal entity (type + body) |
| `hery-extends` | Entity with `_extends` inheritance |
| `hery-requires` | Entity with `_requires` dependencies |
| `hery-full` | Entity with all five reserved properties |
| `hery-package` | Package entity |
| `hery-template` | Template entity for weaver |
| `hery-webserver` | Webserver application entity |
| `hery-tools` | Tools configuration entity |
| `hery-secret` | Secret entity for doorman |
| `hery-vm` | Virtual machine infrastructure entity |
| `_type` | Insert `_type` property |
| `_extends` | Insert `_extends` property |
| `_meta` | Insert `_meta` block |
| `_body` | Insert `_body` block |
| `_requires` | Insert `_requires` block |

### Editor Defaults

- 2-space indentation
- Advanced auto-indent
- Indent-based code folding

### File Icon

Custom file icon for `.hery` files in both light and dark themes.

## Installation

### From Source

```bash
# Install vsce if you don't have it
npm install -g @vscode/vsce

# Package and install
cd hery-code-editor-plugin
vsce package
code --install-extension hery-0.1.0.vsix
```

### Manual

Copy this directory to your VS Code extensions folder:

```bash
cp -r hery-code-editor-plugin ~/.vscode/extensions/amadla.hery-0.1.0
```

Then reload VS Code.

## HERY Format

HERY files are YAML documents with five reserved root-level properties:

```yaml
---
_type: amadla.org/entity/application@v1.0.0
_extends: github.com/AmadlaOrg/EntityApplication@v1.0.0
_meta:
  name: MyApp
  description: Application definition
  tags:
    - web
_requires:
  - amadla.org/entity/package@v1.0.0
_body:
  server_name: localhost
  port: 8080
```

See the [HERY specification](https://github.com/AmadlaOrg/hery) for full details.

## License

MIT
