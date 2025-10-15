# get_pic_for_4chan

Utility script to automatically fetch and process images for 4chan threads.

## Overview
This tool monitors specified 4chan boards and downloads images matching criteria you define. Useful for archival and research purposes.

## Setup
1. Clone repository
2. Install dependencies: `pip install -r requirements.txt`
3. Configure boards in `config.json`

## Usage
```bash
python get_pic.py --board g --thread 12345678
```

## Features
- Multiple board support
- Filter by image type/size
- Rate limiting built-in
- Metadata extraction

# Touch update: 1760535253

# PR Merge: 2025-10-15 - enhancement/merge-4113

# PR Merge: 2025-10-15 - refactor/merge-7258
