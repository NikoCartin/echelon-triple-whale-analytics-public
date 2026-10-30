# Echelon Mobile Funnel Analytics and Checkout QA

A sanitized technical case study by **Nícolas Cartín Reyes, Lead Developer**.

This repository documents a controlled investigation into a mobile e-commerce funnel signal that appeared to diverge between Triple Whale and Shopify Analytics. The work combines funnel interpretation, checkout event validation, responsive cart QA, and release safety without exposing private store configuration.

## Case study outcome

A controlled mobile storefront-to-checkout run reached the Shopify Checkout Information and Shipping steps without entering customer or payment data. The network capture alone could not prove that the Triple Pixel checkout-start event was received. A same-hour comparison later showed agreement between a Triple Whale Initiate Checkout signal and a Shopify session that reached checkout. The evidence did not support a confirmed aggregate tracking loss.

A physical iPhone check also confirmed that cart quantity changed correctly and that the Check out action reached the dummy checkout Shipping page. No production theme change was made during the investigation.

## What this demonstrates

- Funnel diagnosis without treating an analytics insight as proof of a storefront defect.
- Same-hour reconciliation between an attribution platform and Shopify Analytics.
- Controlled mobile cart and checkout validation without creating an order.
- Separation of storefront, optimizer, consent, payment, and analytics ownership.
- QA-only JavaScript guards with a clear no-production boundary.
- Sanitized technical documentation suitable for a public engineering portfolio.

## Follow-up: mobile checkout CRO remediation

The investigation led to a set of live theme fixes for mobile and in-app browser friction between the product page and payment: chat launcher placement, membership option order, popup suppression during checkout intent, a restored price and financing area, and site-scan clean-up. Landing-page findings were handed to the team that owns them. Measurement is in progress, and no uplift is claimed yet. [Read the CRO case study](docs/05-mobile-cro-remediation.md).

## Contents

- [Case overview](docs/01-case-overview.md)
- [Methodology](docs/02-methodology.md)
- [Findings and release safety](docs/03-findings-and-release-safety.md)
- [Reusable validation checklist](docs/04-validation-checklist.md)
- [Mobile checkout CRO remediation](docs/05-mobile-cro-remediation.md)
- [Changelog](CHANGELOG.md)

## Data handling

This public repository intentionally excludes private dashboard URLs, theme IDs, checkout tokens, session identifiers, customer information, payment data, raw browser exports, credentials, and internal access details. It contains generalized methods and sanitized outcomes only.
