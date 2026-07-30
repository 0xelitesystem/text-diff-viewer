# Text Diff Viewer

Compare two blocks of text and see a line-level diff in your browser. No server, no tracking, no third-party scripts.

**Live demo:** https://0xelitesystem.github.io/text-diff-viewer/

## Use

Open `index.html` in any modern browser, or visit the GitHub Pages link in the repo description.

Paste the original text on the left and the changed text on the right, then press Compare. The tool computes a line-level diff locally and shows:

- Color-coded lines (green for added, red for removed, plain for unchanged)
- A summary count (N added, N removed, N unchanged)
- Side-by-side view (original and changed in two columns) or inline view (one stream with `+` and `-` signs)
- An option to ignore leading and trailing whitespace when matching lines

The diff is computed with a real longest-common-subsequence (LCS) algorithm over the lines, so the matching is correct rather than a naive line-by-line guess. The original text of each line is always shown; the ignore-whitespace option only affects which lines are treated as equal.

## Why this exists

Most online diff tools either run your text through a server or wrap a heavy editor library with analytics attached. This is the same idea, single file, no analytics, no signup, MIT licensed. The LCS implementation is in plain view so you can confirm the diff is honest.

## Privacy

Everything runs in your browser. The two blocks of text and the computed diff never leave your machine. Verify by viewing the page source or by opening DevTools and watching the network tab, no requests are made.

## Run locally

```bash
git clone https://github.com/0xelitesystem/text-diff-viewer
cd text-diff-viewer
# Open index.html in your browser, or:
python -m http.server 8000
```

## Contribute

Issues and PRs welcome:

- Bugs in diff edge cases (empty inputs, trailing newlines, very large files)
- Word-level or character-level highlighting within changed lines
- UI improvements (keep it minimal, no frameworks)
- Translations

Don't add: analytics, tracking, external scripts, npm dependencies. The whole point of this tool is no surveillance.

## Build

There is no build. It's a single HTML file.

## More

Part of a catalog of single-file browser tools and plain-language references, all MIT licensed and dependency-free: [0xelitesystem.github.io](https://0xelitesystem.github.io/). Built by [elitesystem.ai](https://elitesystem.ai).

## License

MIT.

## Related

- [json-formatter-and-validator](https://github.com/0xelitesystem/json-formatter-and-validator), format and validate JSON in your browser
- [case-converter](https://github.com/0xelitesystem/case-converter), convert text between casing styles
- [regex-tester](https://github.com/0xelitesystem/regex-tester), test regular expressions against sample text
