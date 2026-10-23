# Methodology

## Test design

The investigation used read-only analytics review and controlled anonymous browser sessions. Viewports included a 390 by 844 mobile profile and a 1440 by 900 desktop profile. The flow stopped at the checkout information or Shipping step. No customer information, payment information, or order submission was used.

## Storefront checks

The route matrix covered a homepage, a canonical product collection, two representative product pages, the cart, and the standard checkout handoff. Each route was checked for HTTP response, horizontal overflow, key controls, console signals, and route-specific interactions.

The cart checks covered Add to Cart, cart quantity change from 1 to 2, checkout control presence, and checkout handoff. A physical iPhone session supplemented the simulated platform matrix.

## Event checks

The controlled browser trace was reviewed for checkout requests, first-party collection requests, checkout preload resources, and direct Triple Whale signals. A request being created or aborted was not treated as proof of event acceptance or event loss.

Triple Whale and Shopify Analytics were then compared using the same store time zone and the same dashboard hour. The comparison used aggregate signals rather than checkout tokens or customer identifiers.

## Platform isolation

The platform matrix separated Linux x86_64 behavior from simulated Windows, macOS, Android, and iPhone branches. This distinction was important because a client-side optimization layer changed script loading behavior on one branch. Platform simulation was treated as isolation evidence, not as a substitute for physical-device testing.

## Release controls

The investigation did not remove apps, disable consent, defer payment integrations, alter Shop Pay, or publish theme changes. Targeted JavaScript guards were kept in a duplicate QA theme. Production deployment remained subject to preview, before and after evidence, stakeholder review, pullback verification, and rollback readiness.
