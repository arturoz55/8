# Kestrel

Landing page for a concept Solana trading terminal. It is a single static file, `index.html`, with no build step.

The terminal in the hero runs entirely in the browser with generated market data:

- **Pulse board:** tokens launch and move from Fresh to Bonding to Graduated as their bonding curve fills.
- **Live candles:** a canvas chart for the selected token, with a new candle every 5 seconds.
- **Trading:** start with 10 SOL and buy or sell with presets. Fills include a 0.75% fee and price impact.

Nothing connects to a wallet or a blockchain.

Run it by opening `index.html` in a browser, or with `python3 -m http.server`.

MIT licensed. See `LICENSE`.
