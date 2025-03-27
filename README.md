# ouch.yazi

[ouch](https://github.com/ouch-org/ouch) plugin for [Yazi](https://github.com/sxyazi/yazi).

![ouch.yazi](https://github.com/ndtoan96/ouch.yazi/assets/33489972/946397ec-b37b-4bf4-93f1-c676fc8e59f2)

## Features
- Archive preview
- Compression

## Installation

If you use Yazi from latest main branch
```bash
# Linux/macOS
git clone https://github.com/ndtoan96/ouch.yazi.git ~/.config/yazi/plugins/ouch.yazi

# Windows with cmd
git clone https://github.com/ndtoan96/ouch.yazi.git %AppData%\yazi\config\plugins\ouch.yazi

# Windows with powershell
git clone https://github.com/ndtoan96/ouch.yazi.git "$($env:APPDATA)\yazi\config\plugins\ouch.yazi"
```

If you use Yazi < 0.4.3
```bash
# Linux/macOS
git clone --branch v0.4.0 --single-branch https://github.com/ndtoan96/ouch.yazi.git ~/.config/yazi/plugins/ouch.yazi

# Windows with cmd
git clone --branch v0.4.0 --single-branch https://github.com/ndtoan96/ouch.yazi.git %AppData%\yazi\config\plugins\ouch.yazi

# Windows with powershell
git clone --branch v0.4.0 --single-branch https://github.com/ndtoan96/ouch.yazi.git "$($env:APPDATA)\yazi\config\plugins\ouch.yazi"
```

Make sure you have [ouch](https://github.com/ouch-org/ouch) installed and in your `PATH`.

## Usage

### Preview
For archive preview, add this to your `yazi.toml`:

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

Now go to an archive on Yazi, you should see the archive's content in the preview pane. You can use `J` and `K` to roll up and down the preview.

If you want to change the icon or the style of text, you can modify the `peek` function in `init.lua` file (all of them are stored in the `lines` variable).

### Compression
For compession, add this to your `keymap.toml`:

```toml
[[manager.prepend_keymap]]
on = ["C"]
run = "plugin ouch"
desc = "Compress with ouch"
```

The plugin uses `zip` format by default. You can change the format when you name the output file, `ouch` will detect format based on file extension.

And, for example, if you would like to set `7z` as default format, you can use `plugin ouch 7z`.

### Decompression
This plugin does not provide a decompression feature because it already is supported by Yazi.
To decompress with `ouch`, configure the opener in `yazi.toml`.

```toml
[opener]
extract = [
	{ run = 'ouch d -y "%*"', desc = "Extract here with ouch", for = "windows" },
	{ run = 'ouch d -y "$@"', desc = "Extract here with ouch", for = "unix" },
]
```
