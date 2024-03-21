# ouch.yazi

An archive previewer plugin for [yazi](https://github.com/sxyazi/yazi), using [ouch](https://github.com/ouch-org/ouch).

# Preview

![preview](https://github.com/Rolv-Apneseth/ouch.yazi/assets/69486699/ff1930c1-3632-4c21-8671-eca453977d8b)

# Installation

Clone the repo inside `~/.config/yazi/plugins/` (Linux) or `%APPDATA%\yazi\config\plugins\` (Windows). Add the below config to `yazi.tom`.

```toml
[plugin]
prepend_previewers = [
	# archive previewer
	{ mime = "application/zip",             run = "ouch" },
	{ mime = "application/gzip",            run = "ouch" },
	{ mime = "application/x-tar",           run = "ouch" },
	{ mime = "application/x-bzip",          run = "ouch" },
	{ mime = "application/x-bzip2",         run = "ouch" },
	{ mime = "application/x-7z-compressed", run = "ouch" },
	{ mime = "application/x-rar",           run = "ouch" },
	{ mime = "application/xz",              run = "ouch" },
	{ mime = "application/pdf",             run = "ouch" },
]
```
