# Keycode Inspector

Press any key and instantly see the JavaScript keyboard event fields for it: `event.key`, `event.code`, the deprecated `keyCode` and `which`, `event.location`, and which modifier keys are held. Like keycode.info, but a single self-contained file with no external dependencies. Works offline.

## Live demo

https://0xelitesystem.github.io/keycode-inspector/

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

Everything runs in your browser. Keypresses are read locally and never sent anywhere. There are no external scripts, no fonts, no stylesheets, and no analytics. Open the page source to confirm. It works fully offline.

## License

MIT. Copyright 0xelitesystem 2026.
