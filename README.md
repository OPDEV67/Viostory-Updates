# Viostory — Windows updates

This **public distribution repository** hosts Viostory installers and a signed update manifest. The game source stays in the private repository `OPDEV67/Viostory`.

## Update feed

Once releases are built and signed, `latest.json` will describe the newest Windows installer. **No installer or valid signed update has been published yet.**

The manifest format is:

```json
{"version":"0.9.6","url":"https://github.com/OPDEV67/Viostory-Updates/releases/download/v0.9.6/Viostory_Beta_0.9.6_Setup.exe","sha256":"<64 lowercase hex digits>","signature":"<Ed25519 base64 signature>","notes":"Release notes"}
```

Signature covers UTF-8 `version + '\\n' + url + '\\n' + sha256`. The public key is embedded in the app's `update-config.json`; the private key must never be published.

For the stable HTTPS manifest endpoint, enable GitHub Pages (Deploy from branch, main/root) and publish a verified `latest.json` to the repository root after each release. The resulting endpoint will be `https://opdev67.github.io/Viostory-Updates/latest.json` once Pages is enabled and deployed.
