# obsidian-various-complements-plugin

[![release](https://img.shields.io/github/release/tadashi-aikawa/obsidian-various-complements-plugin.svg)](https://github.com/tadashi-aikawa/obsidian-various-complements-plugin/releases/latest)
[![Tests](https://github.com/tadashi-aikawa/obsidian-various-complements-plugin/workflows/Tests/badge.svg)](https://github.com/tadashi-aikawa/obsidian-various-complements-plugin/actions)
![downloads](https://img.shields.io/github/downloads/tadashi-aikawa/obsidian-various-complements-plugin/total)

This plugin for [Obsidian] enables you to complement input in markdown files.

## ⌨️Features

### ✨ Current file complement

It complements the text with tokens that exists in a current file.

You can set a strategy if the separator of your language is not only whitespace.

![settings](https://raw.githubusercontent.com/tadashi-aikawa/obsidian-various-complements-plugin/main/demo/settings.png)

#### Default

![default](https://raw.githubusercontent.com/tadashi-aikawa/obsidian-various-complements-plugin/main/demo/current-file-complement.gif)

#### Japanese

![default](https://raw.githubusercontent.com/tadashi-aikawa/obsidian-various-complements-plugin/main/demo/japanese-current-file-complement.gif)

#### Matching logic

- If `Match strategy` is `prefix`
  - Prefix match
  - case-sensitive (only first letter)
- If `Match strategy` is `partial`
  - Partial match
  - case-insensitive


### ✨ Custom dictionary complement

You can also use custom dictionaries to show suggestions on auto-complete.

![custom-dictionary-demo](https://raw.githubusercontent.com/tadashi-aikawa/obsidian-various-complements-plugin/main/demo/custom-dictionary-demo.gif)

You can add custom dictionaries from settings as follows.

![settings](https://github.com/tadashi-aikawa/obsidian-various-complements-plugin/blob/main/demo/setting-custom-directories.png?raw=true)

- ⚠ Absolute paths are not supported
- ⚠ Relative paths **that point outside of Vault** are not supported
  - On desktop, it might work correctly but not supported, be careful :)

#### Definitions of a dictionary file

You can define a word for each line in dictionary files.

| Col1 | Col2        | Col3 and later |
| ---- | ----------- | -------------- |
| word | description | aliases        |

- It uses `<TAB>` as a separator
- Surrounding with `%%` means a comment (ex: `%%This is a comment%%`)

Ex.
```
Looks good to me		LGTM
As far as I know	spoken used to say that you think that something is true, although it is possible that you do not know all the facts or cannot remember completely	AFAIK
red	🔴	color
blue	🔵	color
green	🟢	color
😄		@smile @laugh @good
```

It is more straightforward to edit on Google Spread Sheet.

![custom-dictionary-spreadsheet](https://raw.githubusercontent.com/tadashi-aikawa/obsidian-various-complements-plugin/main/demo/custom-dictionary-spreadsheet.png)

**After you update settings about custom dictionaries, please execute a `Reload custom dictionaries` command.**

#### Matching logic

- If `Match strategy` is `prefix`
  - Prefix match
  - case-sensitive (only first letter)
- If `Match strategy` is `partial`
  - Partial match
  - case-insensitive

### ✨ Internal link complement

It complements the text with internal links, which include both resolved and unresolved.

![internal-link-complement-demo](https://raw.githubusercontent.com/tadashi-aikawa/obsidian-various-complements-plugin/main/demo/internal-link-complement.gif)

You can notice it and insert them **even if you forget to have created internal links**.

#### Matching logic

- If `Match strategy` is `prefix`
  - Prefix match (Ignore prefix-emoji)
    - `Obs` matches both `Obsidian` and `💎Obsidian`
  - **case-insensitive**
- If `Match strategy` is `partial`
  - Partial match
  - case-insensitive
  
### ✨ Predictable complement

Predictable complement is similar to a [Hippie completion] for IntelliJ IDEA; it is triggered by a hotkey, `Shift + Space` by default.

[Hippie completion]: https://www.jetbrains.com/help/idea/auto-completing-code.html#hippie_completion

![predictable-complement-demo](https://raw.githubusercontent.com/tadashi-aikawa/obsidian-various-complements-plugin/main/demo/predictable-complement.gif)

#### Matching logic

- Prefix match
- case-sensitive


## 👁 Live preview support

It supports Live Preview mode for now.

![default](https://raw.githubusercontent.com/tadashi-aikawa/obsidian-various-complements-plugin/main/demo/livepreview.gif)

## 📱 Mobile support

It supports on mobile.

![default](https://raw.githubusercontent.com/tadashi-aikawa/obsidian-various-complements-plugin/main/demo/mobile.gif)

## 🖥️ For developers

- Requirements
    - [Task]

### Development

```console
task init
task dev
```

### Release

```
task release VERSION=1.2.3
```

[Obsidian]: https://obsidian.md/
[Task]: https://github.com/go-task/task
