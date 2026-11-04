# Mahjinnies storefront

Static storefront for Mahjinnies, including product collections, the supplied logo, contact dialog, persistent multi-product cart, and Shopify checkout.

## Deploy

Publish the `public/` directory on any static host. No build command or dependencies are required. Netlify can deploy directly from this repository using the included `netlify.toml`.

For a local preview, run `python3 -m http.server 8000 --directory public` and open http://localhost:8000.

## Shopify

- Checkout domain: `https://shopify.mahjinnies.com`.
- Public Storefront API: `https://fubw3f-mg.myshopify.com/api/2026-10/graphql.json`.
- Product handles and variant IDs are defined in `public/app.js`.
- Public price requests use Shopify's tokenless Storefront API; no admin tokens are included or required by this source.
- The cart persists in the visitor's local browser. Checkout sends every selected variant and quantity together to Shopify.
- The estimated subtotal excludes discounts, shipping and taxes. Shopify confirms final prices, availability and payment.
- If public price loading fails, the site hides the subtotal and lets Shopify confirm prices at checkout. Live public API requests still require verification in a visitor browser: the authoring environment blocks direct requests to the shop. Unit checks passed for subtotal arithmetic, sold-out handling, quantity edits, cart persistence, and fallback behavior.

## Files

- `public/index.html`: page content, header, contact and cart dialogs.
- `public/style.css`: responsive styles.
- `public/app.js`: catalog, filters, cart, price fetching and checkout links.
- `public/assets/`: product images and brand logo.

Google Fonts are loaded from Google; browser/system fonts provide fallbacks. No original uploads, internal notes, or credentials are included.
