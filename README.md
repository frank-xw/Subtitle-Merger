# Subtitle-Merger

Merge two SRT subtitle files into a single dual-language ASS file.

## What it does

Takes two SRT files (e.g., English and Chinese) and combines them into one ASS file with both languages displayed together. The main language appears on top in larger text, the secondary language below in smaller gray text.

## Requirements

- Python 3.10 or higher
- No external packages needed

## Quick Start

Put your subtitle files in a folder with suffixes `-EN.srt` and `-CN.srt`, then run:

```bash
python main.py
```

Output will be named like `Video.EN_CN.ass`.

## Usage Examples

**Specify files explicitly:**
```bash
python main.py english.srt chinese.srt
```

**Custom output name:**
```bash
python main.py -o merged.ass
```

**Adjust font sizes:**
```bash
python main.py --main-size 60 --secondary-size 50
```

Run `python main.py --help` for all options.

## How it works

The script matches subtitles by timestamp (with 500ms tolerance), then generates an ASS file with two styled tracks. Main subtitles use Arial, secondary uses PingFang SC for Chinese characters.

## Note

- Input must be valid SRT format
- HTML tags are automatically removed
- Only handles two subtitle tracks at a time
