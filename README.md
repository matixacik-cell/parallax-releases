<p align="center">
  <img src="assets/icon.png" width="120" alt="Parallax">
</p>

<h1 align="center">Parallax</h1>

<p align="center">Every business on Google Maps, in a spreadsheet. Free, on your own Mac.<br><a href="https://parallaxleads.com">parallaxleads.com</a></p>

<p align="center">
  <a href="https://github.com/matixacik-cell/parallax-releases/releases/latest/download/Parallax.dmg"><img src="https://img.shields.io/badge/Download%20for%20Mac-000000?style=for-the-badge&logo=apple&logoColor=white" alt="Download for Mac"></a>
  <img src="https://img.shields.io/badge/version-0.1.0-000000?style=for-the-badge" alt="Version 0.1.0">
  <img src="https://img.shields.io/badge/Apple%20silicon-000000?style=for-the-badge" alt="Apple silicon">
  <img src="https://img.shields.io/badge/price-free-000000?style=for-the-badge" alt="Free">
  <a href="https://parallaxleads.com"><img src="https://img.shields.io/badge/parallaxleads.com-000000?style=for-the-badge&logo=safari&logoColor=white" alt="parallaxleads.com"></a>
</p>

<p align="center">
  <img src="assets/new-run.png" width="960" alt="The New run screen: a trade, a place, and the list of business types">
</p>

## What it does

Pick a trade and a place. Parallax searches Google Maps town by town and writes every business it finds into a spreadsheet. A town is a handful of searches. A whole state is a few hundred, and the map shows them light up while they run.

**What you get, per business:** name, category, phone, website, address, rating, number of reviews, opening hours, open or closed status, town, region, country, the search term that found it, coordinates, the Google Maps link and the place id. One row each, no duplicates across your runs.

**How it searches:**

- Every town with 5,000 or more people is on the map (69,174 of them, worldwide). Each town gets a square sized by its population; big cities are cut into many squares so nothing is missed.
- A trade also searches its related categories. "Plumber" searches plumbing service, drain cleaning service and water heater installer too. There are 526 business types to pick from, or type your own.
- Listings that hide the phone number (dentists, doctors, lawyers do this a lot) are opened one by one to get it.
- Businesses you already have from an earlier run are skipped, so every run brings new ones. You can turn that off.
- You set the cap: a number of businesses, a time limit, or everything.

**How fast, roughly:** one search takes about 20 seconds and brings about 30 businesses, three searches run at once. One town and one trade is done in a minute. A whole state and one trade is about 400 searches, around 45 minutes, and about 2.5 GB of proxy data.

## Requirements

- A Mac with Apple silicon (M1 or newer), macOS 12 or newer. Intel Macs are not covered by this build yet.
- Google Chrome installed. Parallax drives a hidden copy of it for the searches.
- A Webshare account for the proxies (below).

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

Under the hood this is an MCP server (the standard way AI tools plug in). It runs on your Mac only and talks to the app through a local door that only it has the key to. The tools it gives your assistant:

| Tool | What it does |
| --- | --- |
| `parallax_preview` | What a search would cover: the towns, the business types, and the approximate searches, businesses, minutes and data. Instant, costs nothing. |
| `parallax_start` | Start a search. With a wait of up to 50 seconds it returns the finished rows in the same answer. |
| `parallax_status` | Progress of a run, or the totals and the file path when it is done. Can wait for the end. |
| `parallax_results` | Rows from a run, in pages, as tab separated lines. Works while the run is still going. |
| `parallax_runs` | Your last 20 runs with their totals and file names. |
| `parallax_stop` | Stop the current run. Everything found so far stays in the file. |

A typical exchange: you ask for roofers in Sedona, the assistant previews the search, starts it with a wait, gets the rows back in the same call, notices Sedona only has five roofers, and widens to the next towns by itself before giving you the list.

## What stays on your Mac

No account. No server. Your results and your key live in your own Library folder, and nothing is sent to us. Parallax never copies review text or photos, never goes behind a login, never gets around a CAPTCHA.

## Questions people ask

**Why do I need proxies?** Google Maps limits how many searches one address can make. A hundred proxies spread the searches out so your Mac is never the one asking, and so the searches do not get slowed down or blocked.

**Why Webshare?** It is the cheapest plan we found that works well for this: 100 US proxies, 250 GB a month, about $5.39. Parallax has no deal with them, you pay them directly, and you can cancel any time.

**Does Parallax send anything to you?** No. There is no account and no server. The app talks to Google Maps through your proxies and to Webshare with your key, nothing else. The key and your results stay in your Library folder.

**Can I run it on a town outside the US?** Yes. The town list is worldwide. The proxies are US based, so results come in the language Google shows US visitors unless you change the language in Settings.

**How big can a run be?** As big as you like. A cap of 0 means every square gets searched; a time limit in Settings stops a long run by itself. Everything found so far is always in the file.

**Where are my files?** In your Library folder, under Application Support, in a folder per run. Runs in the app shows them, with one click export to wherever you want the sheet.

## Updates

New versions appear on the [Releases](https://github.com/matixacik-cell/parallax-releases/releases) page. The app does not update itself yet: download the new dmg and drag Parallax into Applications over the old one. Your runs and your key stay where they are.

## Links

Website: [parallaxleads.com](https://parallaxleads.com)  
Questions: [hello@parallaxleads.com](mailto:hello@parallaxleads.com)
