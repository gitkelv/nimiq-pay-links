Pay Links

Get paid in Nimiq with one link. Pay Links is a Mini App for Nimiq Pay that turns a tip, a request or a group collection into a single link. The link opens inside Nimiq Pay, ready to pay in two taps. No account, no server, no copy-pasting addresses.

Live app: https://gitkelv.github.io/nimiq-pay-links/

The problem

In Nimiq Pay today, getting paid means copying an address and pasting it into a chat. There is no amount, no reason and no confirmation of who you are paying. Pay Links makes the receiving side as easy as the paying side.

What it does

Three kinds of link, all created in the Receive screen:
– Tip jar: open amount, with one-tap quick amounts you choose (10, 50, 100, 500 or 1,000 NIM, plus one custom amount).
– Request: an exact amount and a reason, with an optional short reference written on the payment so you can match it later (for example "meetup-oct").
– Group tip: one link for many people to chip in.

Also included:
– Private options: payers can tip without a message, and receivers can hide their address until it is tapped. Nimiq payments are public on-chain, so these reduce what the app shows; they do not make a payment untraceable.
– Share tools: copy link, native share, QR code (savable as an image), and a shareable thank-you card after a tip.
– Safety checks: the app blocks paying your own link, checks the payer's balance before sending, and says "Tip submitted" until the network confirms.
– Outside Nimiq Pay: the page explains what Pay Links is and offers "Open in Nimiq Pay" or "Get Nimiq Pay". It never fakes a payment.

How it works

Everything lives inside the link. When you create a link, the app packs the name, note, address, amounts and options into a compact string in the URL (?d=...). Opening the link rebuilds the page from that string, so there is no database to run, host or hack.

Payments use the Nimiq Pay provider:
– listAccounts to fill in your address and detect self-payments
– getBalance to check the payer's balance and read goal progress on older links
– sendBasicTransaction / sendBasicTransactionWithData to send NIM, with Nimiq Pay's own approval screen

The app never sees or holds keys or funds. Payments go straight from the payer's wallet to the receiver's address.

Run it

It is a single static file with no build step.
1. Open index.html in a browser to see the interface. Outside Nimiq Pay it cannot send payments.
2. To test for real, host it on HTTPS (GitHub Pages works: Settings, Pages, deploy from main and / (root)).
3. In Nimiq Pay, open Mini Apps, then Custom URL, and paste your Pages address. Use testnet and faucet NIM first.

Limits
– Links cannot be edited after sharing. Make a new link instead.
– Without a backend, the app cannot list who paid.
– NIM only for now. USDT on Polygon is planned.
– Per-link social previews would need a server, so shared links show a generic preview.

Credits
– Nimiq Pay Mini Apps Framework for the wallet and payments.
– qrcodejs (MIT) for QR codes, loaded from cdnjs.
– Mulish (SIL Open Font License) via Google Fonts.

License

MIT. See LICENSE.
