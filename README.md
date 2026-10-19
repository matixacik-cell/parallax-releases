<p align="center">
  <img src="assets/icon.png" width="120" alt="Parallax">
</p>

<h1 align="center">Parallax</h1>

<p align="center">Every business on Google Maps, in a spreadsheet. Free, on your own Mac.</p>

<p align="center">
  <a href="https://github.com/matixacik-cell/parallax-releases/releases/latest/download/Parallax.dmg"><img src="https://img.shields.io/badge/Download%20for%20Mac-000000?style=for-the-badge&logo=apple&logoColor=white" alt="Download for Mac"></a>
  <img src="https://img.shields.io/badge/version-0.1.0-000000?style=for-the-badge" alt="Version 0.1.0">
  <img src="https://img.shields.io/badge/Apple%20silicon-000000?style=for-the-badge" alt="Apple silicon">
  <img src="https://img.shields.io/badge/price-free-000000?style=for-the-badge" alt="Free">
</p>

<p align="center">
  <img src="assets/new-run.png" width="960" alt="The New run screen: a trade, a place, and the list of business types">
</p>

## What it does

Pick a trade and a place. Parallax searches Google Maps town by town and writes every business it finds into a spreadsheet: name, phone, website, address, rating, reviews. A town is a handful of searches. A whole state is a few hundred, and the map shows them light up while they run.

## Download

1. Download [Parallax.dmg](https://github.com/matixacik-cell/parallax-releases/releases/latest/download/Parallax.dmg), open it, drag Parallax into Applications.
2. First open: macOS says it cannot verify the app, because we do not have an Apple developer certificate yet. Right click Parallax in Applications, choose Open, then Open again. On the newest macOS the button may be missing: open System Settings, go to Privacy and Security, scroll down, click Open Anyway.
3. The app walks you through connecting your proxies. Three steps, about three minutes.

## Your own proxies

Parallax searches through proxies you own, so Google never sees your Mac. Make a Webshare account, pick the 100 proxy plan (about $5.39 a month, enough for roughly 580,000 businesses), paste your API key into the app once. The key stays on your Mac, locked by macOS, and only ever goes to Webshare.

<p align="center">
  <img src="assets/connect-proxies.png" width="820" alt="The three steps to connect your proxies">
</p>

## Use it from your AI tools

<p align="center">
  <picture><source media="(prefers-color-scheme: dark)" srcset="assets/logos/claude-white.svg"><img src="assets/logos/claude-black.svg" height="30" alt="Claude"></picture>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
  <picture><source media="(prefers-color-scheme: dark)" srcset="assets/logos/cursor-white.svg"><img src="assets/logos/cursor-black.svg" height="30" alt="Cursor"></picture>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
  <picture><source media="(prefers-color-scheme: dark)" srcset="assets/logos/vscode-white.svg"><img src="assets/logos/vscode-black.svg" height="30" alt="VS Code"></picture>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
  <picture><source media="(prefers-color-scheme: dark)" srcset="assets/logos/codex-white.svg"><img src="assets/logos/codex-black.svg" height="30" alt="Codex"></picture>
</p>

Parallax has a connector for Claude, Claude Code, Cursor, VS Code and Codex. Open Settings in the app, pick your tool, press one button. Then ask:

```text
Find 20 roofers in Sedona with phone numbers.
```

The run shows live in the Parallax window and the rows come back into the chat. A small search comes back finished in one call; a big one reports progress until it ends.

## What stays on your Mac

No account. No server. Your results and your key live in your own Library folder, and nothing is sent to us. Parallax never copies review text or photos, never goes behind a login, never gets around a CAPTCHA.

## Updates

New versions appear on the [Releases](https://github.com/matixacik-cell/parallax-releases/releases) page. The app does not update itself yet: download the new dmg and drag Parallax into Applications over the old one. Your runs and your key stay where they are.

## Links

Website: [parallaxleads.com](https://parallaxleads.com)  
Questions: [hello@parallaxleads.com](mailto:hello@parallaxleads.com)
