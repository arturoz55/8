# Apogee

Landing page for a concept multichain trading terminal (Solana, Ethereum, Base, BNB Chain, Arbitrum, Polygon, Avalanche, Optimism and Robinhood Chain). It is a single static file, `index.html`, with no build step.

The terminal in the hero runs entirely in the browser with generated market data:

- **Pulse board:** tokens launch and move from Fresh to Bonding to Graduated as their bonding curve fills.
- **Live candles:** a canvas chart for the selected token, with a new candle every 5 seconds.
- **Trading:** start with 10 SOL and buy or sell with presets. Fills include a 0.75% fee and price impact.

Nothing connects to a wallet or a blockchain.

Run it by opening `index.html` in a browser, or with `python3 -m http.server`.

MIT licensed. See `LICENSE`.

## Wallets and X

- **Connect wallet** lists 11 Solana wallets (Phantom, Solflare, Backpack, OKX, Coinbase, Trust, Magic Eden, Bitget, Exodus, Glow, Nightly) and also picks up any other installed wallet through the Wallet Standard, using the icon the wallet itself provides. Icons for wallets that are not installed come from the open-source `@solana/wallet-adapter-*` packages. It only reads the public address and the SOL balance from a public mainnet RPC. It never signs transactions or asks for a seed phrase. Wallets that are not installed link to their download pages.
- **X profile:** linked to [@UseApogee](https://x.com/UseApogee) through `X_URL` in the script of `index.html`. The "Share on X" button in the terminal posts the user's open positions.

## Teaser video

`media/teaser.html` renders a 22-second 1920x1080 teaser on a canvas, where every frame is a pure function of time. `media/apogee-teaser.mp4` is the rendered result and `media/apogee-teaser.jpg` a poster frame. The fonts in `media/fonts` are Inter and JetBrains Mono, both under the SIL Open Font License. Open the HTML in a browser to preview it playing in real time.

## Chains

The terminal switches between 9 chains from the hero chips or the chain menu in the terminal bar. Picking an EVM chain asks a connected wallet to switch network (wallet_switchEthereumChain). Each chain keeps its own board, balance and positions, and the choice is remembered. The wallet window has a Solana tab (Wallet Standard) and an Ethereum / Robinhood Chain tab that discovers installed EVM wallets through EIP-6963 and reads the address, network and ETH balance through the wallet itself.

Chain logos come from the MIT-licensed [`@web3icons/core`](https://www.npmjs.com/package/@web3icons/core) package and are shown only to identify each network.
