# Subtitle-Merger

Merge two SRT subtitle files into a single dual-language subtitle file (ASS or SRT format).

## What it does

Takes two SRT files (e.g., English and Chinese) and combines them into one file with both languages displayed together. By default outputs SRT format with both languages on separate lines. Can also output ASS format where the main language appears on top in larger text, the secondary language below in smaller gray text.

## Requirements

- Python 3.10 or higher
- No external packages needed

## Quick Start

Put your subtitle files in a folder with suffixes `-EN.srt` and `-CN.srt`, then run:

```bash
python main.py
```

Output will be named like `Video.EN_CN.srt` (SRT format by default).

## Usage Examples

**Specify files explicitly:**
```bash
python main.py english.srt chinese.srt
```

**Output ASS format instead:**
```bash
python main.py --format ass
```

**Custom output name:**
```bash
python main.py -o merged.srt
```

**Adjust font sizes (ASS only):**
```bash
python main.py --format ass --main-size 60 --secondary-size 50
```

**Adjust subtitle position (ASS only):**
```bash
python main.py --format ass --gap-size 20
```

Run `python main.py --help` for all options.

## Output Formats

- **SRT** (default): Simple text format with both languages on separate lines. Compatible with all players.
- **ASS**: Advanced format with customizable styling, fonts, colors, and positioning. Main subtitles use Arial, secondary uses PingFang SC for Chinese characters.

## How it works

The script matches subtitles by timestamp (with 500ms tolerance), then generates either an SRT file with merged text or an ASS file with two styled tracks.

## Note

- Input must be valid SRT format
- HTML tags are automatically removed
- Only handles two subtitle tracks at a time
- Font size and color options only apply to ASS format
