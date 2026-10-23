# Reusable Validation Checklist

## Before testing

- Define the exact date, time zone, device profile, and funnel event.
- Use an anonymous session and a non-purchase test flow.
- Record the analytics dashboard window before starting.
- Keep payment, customer data, and order submission out of scope.

## During storefront testing

- Load the product page and confirm HTTP response.
- Confirm Add to Cart creates the expected cart state.
- Confirm quantity changes update the cart.
- Check for horizontal overflow and blocked controls.
- Open standard checkout and stop at Information or Shipping.
- Capture console errors and separate first-party from third-party sources.

## During analytics reconciliation

- Compare Triple Whale and Shopify Analytics in the same store time zone.
- Use the same reporting hour and allow the dashboard to refresh.
- Compare aggregate counts before attempting event identity matching.
- Treat checkout tokens and session IDs as private data.
- Never infer event acceptance from a request being created alone.

## Before release

- Repeat on physical iPhone and Android devices.
- Test standard checkout and Shop Pay separately.
- Capture before and after screenshots or preview links.
- Keep app, consent, payment, and optimizer changes separate.
- Use a duplicate theme and a smallest-scope reversible change.
- Pull back the QA files and verify the source hash.
- Obtain stakeholder approval before production deployment.
