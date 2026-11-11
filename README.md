# NFC Bridge example

A one-page demo showing how to drop the NFC Bridge library into any site with a single `<script>` tag.

**Live demo:** https://edprats.github.io/web-nfc-example/ (open in Chrome on Android with NFC turned on)

## Usage

```html
<script src="https://web-nfc-fawn.vercel.app/nfc-bridge.js"></script>

<button id="scan">Scan NFC tag</button>

<script>
  NfcBridge.bind(document.getElementById('scan'), {
    getAuthData: () => ({ session: 'demo_session', nonce: 'demo_nonce' }),
    onResult: result => console.log(result),
    onError: err => console.error(err.code, err.message)
  });
</script>
```

Tap the button and hold a tag to the phone. `onResult` receives JSON with your `session`/`nonce`, the tap timestamp, and the tag's serial number and decoded NDEF records.

## Requirements

- Android phone with NFC on
- Chrome 89+ (or another Chromium browser)
- HTTPS (GitHub Pages works)
