# Ubuntu Image Fetcher

A command-line tool that downloads images from a list of URLs, with safety checks built in along the way.

## What it does

You give it one or more image URLs (comma-separated), and it:
- Verifies each URL actually points to an image before downloading (checks `Content-Type`)
- Skips files over 5MB to avoid accidentally pulling something huge
- Checks for duplicates using MD5 hashing, so re-running it doesn't fill your folder with copies
- Saves everything into a `Fetched_Images` folder, handling connection errors and bad URLs without crashing

## Why "Ubuntu"

Named after the concept, not the OS — "I am because we are." The idea was building something that respects the resources it's pulling from: checking file types and sizes before grabbing anything, rather than just blindly downloading whatever's at a URL.

## Running it

```bash
python Ubuntu_Requests.py
```

It'll prompt for one or more URLs, then fetch, validate, and save each one, printing status as it goes.

## Built with

Python, the `requests` library (auto-installs if missing), `hashlib` for duplicate detection.

## What I'd add next

- Support for a file of URLs instead of manual comma-separated input
- Progress bars for larger batches
- Optional image resizing/compression on save
