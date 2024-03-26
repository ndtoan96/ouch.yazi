# ouch.yazi

An archive previewer plugin for [Yazi](https://github.com/sxyazi/yazi), using [ouch](https://github.com/ouch-org/ouch).

![ouch.yazi](https://github.com/ndtoan96/ouch.yazi/assets/33489972/946397ec-b37b-4bf4-93f1-c676fc8e59f2)

## Installation

```bash
# Linux/macOS
git clone https://github.com/ndtoan96/ouch.yazi.git ~/.config/yazi/plugins/ouch.yazi

# Windows
git clone https://github.com/ndtoan96/ouch.yazi.git %AppData%\yazi\config\plugins\ouch.yazi
```

Make sure you have [ouch](https://github.com/ouch-org/ouch) installed and in your `PATH`.

## Usage

Add this to your `yazi.toml`:

```toml
[plugin]
prepend_previewers = [
	# Archive previewer
	{ mime = "application/*zip",            run = "ouch" },
	{ mime = "application/x-tar",           run = "ouch" },
	{ mime = "application/x-bzip2",         run = "ouch" },
	{ mime = "application/x-7z-compressed", run = "ouch" },
	{ mime = "application/x-rar",           run = "ouch" },
	{ mime = "application/x-xz",            run = "ouch" },
]
```

## Customization

If you want to change the icon or the style of text, you can modify the `init.lua` file directly (all of them are stored in the `lines` variable).
