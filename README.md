# Sway Keybinds Viewer

A terminal UI application that reads and displays your [Sway](https://swaywm.org/) window manager keybindings in an interactive table.

## Installation (Recommended)

Download the latest `swaybinds` executable from the [Releases](../../releases) page and move it to your PATH:

```bash
sudo mv swaybinds /usr/local/bin/
sudo chmod +x /usr/local/bin/swaybinds
```

Then run it from anywhere:

```bash
swaybinds
```

Or bind it to a key combo in your Sway config:

```
bindsym $mod+Shift+x exec foot -e swaybinds
```

## Running from Source

### Requirements

- Python 3.8+
- A virtual environment (recommended)

```bash
python -m venv .venv
source .venv/bin/activate
pip install -r requirements.txt
```

Then run:

```bash
python main.py
```

## How It Works

The app reads `~/.config/sway/config`, scans for `bindsym` entries and `$mod` variable definitions, and displays each keybinding as a row in a scrollable two-column table (Key / Command).

## Project Structure

```
.
├── main.py                    # Textual app entry point
├── requirements.txt           # Python dependencies
└── utils/
    └── keybinds_reader.py     # Sway config parser
```
