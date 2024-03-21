# ouch.yazi

An archive previewer plugin for [yazi](https://github.com/sxyazi/yazi), using [ouch](https://github.com/ouch-org/ouch).

# Preview

![ouch yazi-preview](https://github.com/ndtoan96/ouch.yazi/assets/33489972/946397ec-b37b-4bf4-93f1-c676fc8e59f2)

# Installation

Make sure you have [ouch](https://github.com/ouch-org/ouch) available in PATH. Then clone the repo inside `~/.config/yazi/plugins/` (Linux) or `%APPDATA%\yazi\config\plugins\` (Windows). Add the below config to `yazi.tom`.

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

# Customization

If you want to change the icon or the style of text, you can modify the `init.lua` file directly (all of them are stored in the `lines` variable).
