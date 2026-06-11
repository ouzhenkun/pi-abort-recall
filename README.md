# pi-abort-recall

**Recall your last prompt back to the editor after aborting — so you can edit and retry without retyping.**

[![npm version](https://img.shields.io/npm/v/pi-abort-recall?style=for-the-badge)](https://www.npmjs.com/package/pi-abort-recall)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg?style=for-the-badge)](https://opensource.org/licenses/MIT)

## Why

When you press Escape to abort an AI response, your original message disappears from the editor. If you wanted to tweak the wording and retry, you have to retype it from scratch.

This extension puts it back automatically.

## Install

```bash
pi install npm:pi-abort-recall
```

Requires Pi v0.37.0+.

## How It Works

1. Captures the text content of each user message as it's sent
2. When an assistant response ends with `stopReason: "aborted"`, restores the last user message back to the editor via `ctx.ui.setEditorText`

That's it. No config, no dependencies.

## Limitations

- Only restores the most recent user message — earlier messages in a multi-turn conversation are not recoverable.
- Image or file attachments in the original message are not restored, only text content.

## License

MIT
