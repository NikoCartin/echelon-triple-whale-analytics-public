# Mobile Checkout CRO Remediation

**Author:** Nícolas Cartín Reyes, Lead Developer
**Date:** October 2026
**Platform:** Shopify Plus storefront, Triple Whale, Shopify Analytics
**Status:** Theme fixes live; conversion measurement window in progress

## Problem

Following the funnel investigation in this repository, the checkout-to-cart rate had fallen to roughly half of its summer level. Mobile carried the large majority of add-to-cart sessions and converted well below desktop, and shoppers inside social in-app browsers converted lowest of all.

## Approach

1. **Measurement first.** Validated the tracking pixel against a controlled live mobile checkout, then compared the attribution platform with Shopify Analytics. The attribution platform under-counted checkouts and over-counted add-to-carts, so Shopify Analytics became the source of truth for this metric.
2. **Real-device testing.** Tested the full product-page-to-payment path on a physical iPhone and inside the Instagram, Facebook and Snapchat in-app browsers, without placing real orders. Wallets and express checkouts worked; one third-party financing window was routed to its vendor.
3. **Friction inventory.** Recorded each obstacle between the product page and payment and separated theme issues (ours to fix) from app, page-builder and ad issues (routed to their owners).

## Fixes shipped

| Friction point | Fix |
| --- | --- |
| Chat launcher covered the sticky Add to cart and Check out buttons on phones and auto-opened full-screen | Raised above the sticky actions; auto-open disabled on phones |
| Monthly membership option sat below two upgrade cards on phones | "Continue monthly purchase" moved to the top on phones |
| Gamified discount popup could freeze scrolling during checkout intent | Not loaded once the cart has items; still shown to empty-cart visitors so email capture continues |
| A product-specific CSS rule hid the title, price and financing area at 1024 px and below on a shared template | Scoped correctly; monthly price restored, with a Shop Pay installments message while the financing widget is unavailable |
| Footer app link, dead quiz link, empty "No products found" menu panel, single-product image on a bundle card | App store buttons added, link routed to demo booking, empty panel removed, bundle image replaced |

Paid-social landing pages built in a page builder were analyzed (traffic source, early exits, CTA depth, offer consistency, revenue per visit compared with direct product-page traffic) and handed to the performance team, which owns those pages.

## Release discipline

Every change was built on an unpublished theme copy, previewed on desktop and mobile, approved, backed up, pushed as only the changed files and pulled back for verification.

## Impact

The friction points are removed on live, and the tracking gap is documented so the team reads the right metric. Checkout-to-cart is being monitored in Shopify Analytics over a 2 to 4 week window. **No conversion uplift is claimed yet.**

## Data handling

This document excludes order numbers, discount codes, theme IDs, backup names, dashboard URLs, people's names and exact revenue or session figures.
