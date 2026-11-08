# Squeek Beats

A rhythm game built on the real wheel of Squeektoshi, the hamster behind Squeekchain.

Every time the magnet on his wheel passes the sensor, the chain records the exact moment. Squeek Beats turns those moments into a beat, and you tap along. Perfect, Good or Miss, with combo scoring and a score card you can share.

Unofficial community project, not affiliated with Squeekchain. It runs on the public Squeekchain Sepolia test API.

## Features

- **Replay a real run**: plays real wheel passes with their exact timing (`GET /v1/measurement/runs`, `passages[].offsetNs`). The slightly uneven rhythm is the hamster's, not a metronome.
- **Daily run**: everyone gets the same real run each UTC day, picked deterministically from the archive, so scores are comparable between friends without any server. Tracks your daily streak and best score in your browser.
- **Live mode**: follows his current pace (`GET /v1/status`, `rpmMilli`). Only available while he is running. The tempo is derived from RPM, so it follows his pace but is not a recording of each pass.
- **Three sound kits**: drums, wheel clicks, and a hamster melody where each pass plays a note on a pentatonic scale.
- **Score card**: shown on screen after each round, with a copy-result button and a Share on X link.
- **Stream overlay**: open `index.html?overlay=1` for a transparent, text-free wheel that pulses to the live pace, meant as a browser source over a stream.
- **Latency slider** for Bluetooth and slow audio setups.

## Security and privacy

- No wallet connection, no transactions, no accounts, no backend, no analytics.
- No downloads and no external scripts, fonts or images. One HTML file.
- The only network requests are read-only GETs to `api.squeekchain.com`.
- The browser stores only your best scores and streak (localStorage). Nothing leaves your device.

## Honest notes

- Replay uses archived runs from the first pages of the API history, so it is a real run but not necessarily the latest one.
- If the API cannot be reached, the game says so and falls back to a clearly labelled practice pattern.
- Sounds are synthesized in the browser (Web Audio), not recorded hamster sounds.

## Run it

Open `index.html` in a browser. One file, no build step, no dependencies.
