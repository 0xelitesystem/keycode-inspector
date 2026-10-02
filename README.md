# Keycode Inspector

Press any key and instantly see the JavaScript keyboard event fields for it: `event.key`, `event.code`, the deprecated `keyCode` and `which`, `event.location`, and which modifier keys are held. Like keycode.info, but a single self-contained file with no external dependencies. Works offline.

**Live demo:** https://0xelitesystem.github.io/keycode-inspector/

## Use

1. Open the page and press any key.
2. Read `event.key`, `event.code`, `keyCode`, `which`, `location`, `repeat` and the live modifier state.
3. Scroll the history of recent keys, or click Clear history.
4. Search the lookup table for a key such as enter, arrow or f5 to see its `code` and `keyCode`.

## Why this exists

Writing keyboard handlers means checking what the browser actually reports for a key, and that should not need a site with ads or analytics. This is one HTML file with no tracking and no network calls that works offline, MIT licensed.

## Features

- Big live display of your last keypress
- Full field breakdown: `event.key`, `event.code`, `event.keyCode`, `event.which`, `event.location`, `event.repeat`
- Live modifier state for `ctrlKey`, `altKey`, `shiftKey`, `metaKey`
- Rolling history of the last 20 keys
- Searchable lookup table of common keys (Enter, Tab, arrows, function keys, numpad, and more) with their `code` and `keyCode`
- Dark-mode toggle
- Keyboard usable and accessible

A short list of keys (Tab, Space, Enter, arrows, and a few others) have `preventDefault` applied so the page does not scroll away or lose focus while you inspect them. This is noted in the interface. Every other key behaves normally.

## How it works

A single `keydown` listener reads the standardized properties off the `KeyboardEvent` and paints them to the page. The deprecated `keyCode` and `which` are shown because a lot of older code still reads them, but modern code should prefer `event.key` (the logical value) and `event.code` (the physical key). The lookup table is a static array baked into the page, so search runs instantly with no network calls.

## Privacy

Everything runs in your browser. Keypresses are read locally and never sent anywhere. There are no external scripts, no fonts, no stylesheets, and no analytics. Open the page source to confirm. It works fully offline. The one thing the page stores is your light or dark theme choice, saved in `localStorage` under the key `theme`.

## Run locally

```
git clone https://github.com/0xelitesystem/keycode-inspector
cd keycode-inspector
```

Open `index.html` in any modern browser. Or serve the folder with `python -m http.server` and visit http://localhost:8000.

## Build

No build step. The whole tool is one `index.html` with inline CSS and JavaScript and no dependencies.

## More

Part of a catalog of single-file browser tools and plain-language references, all MIT licensed and dependency-free: [0xelitesystem.github.io](https://0xelitesystem.github.io/). Built by [elitesystem.ai](https://elitesystem.ai).

## License

MIT. Copyright 0xelitesystem 2026.
