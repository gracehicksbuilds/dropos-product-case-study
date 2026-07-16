# Product Decisions

Some of the choices behind DropOS, and why they were made this way.

## Why signed, time-boxed access passes instead of a static QR code

A static QR code (a simple image containing a customer ID) can be
screenshotted and shared, defeating the entire purpose of access control
at a limited-capacity event. DropOS access passes are generated per
customer, tied to a specific drop and collection window, and designed to
be verified rather than merely displayed. This is a foundational decision,
not an add-on: it shapes how registration, allocation and verification all
connect to one another.

## Why more than one allocation approach

Not every drop has the same shape of demand. A drop with inventory
comfortably ahead of expected demand doesn't need anything more than
straightforward, transparent first-come-first-served allocation. A drop
that will be significantly oversubscribed needs a different mechanism:
one that doesn't reward whoever has the fastest internet connection or the
most automated registration script. DropOS is being developed to support
more than one allocation approach (first-come-first-served and
raffle-based release) so a retailer can choose the right mechanism for
the specific drop, rather than forcing every launch through the same
process. Implementation maturity currently varies by allocation type. The
internal mechanics of how each approach works are intentionally not
detailed publicly.

## Why tenant isolation is enforced at the data layer

Role checks and application-level guards are necessary but not
sufficient: a bug in application logic should not be able to expose one
retailer's customer data to another. DropOS enforces tenant isolation at
the database layer as the final backstop, independent of whether every
line of application code got the access check right. This was a
foundational architecture decision made early, not retrofitted.

## Why retailers remain the merchant of record

DropOS is designed so retailers remain the merchant of record. Customer
payments are intended to flow directly to the retailer's own connected
payment provider rather than through DropOS. This keeps DropOS out of
payment liability and keeps the retailer in direct control of their own
customer transactions and funds. It shapes how the payments architecture
is designed throughout the product, even in areas (such as self-service
payment-provider onboarding) that are still under development.

## Why the store-facing scanner is a separate, mobile-first surface

The person running a scanner on a launch day is not sitting at a desktop
dashboard; they're standing at a door, on a phone, often for hours.
Rather than adapting the retailer admin dashboard for a small screen,
DropOS gives store staff a dedicated, full-bleed, camera-first interface
built around a single job: scan, read the result, act, move to the next
customer.

## Why every operational state is explicit

A verification outcome is never left as an unlabelled pass/fail. A
customer's registration, an invite's status, and a check-in's outcome are
each an explicit, named state, including states for the unusual cases
(a pass presented at the wrong collection window, a pass already used)
rather than folding those into a generic "invalid" result. This gives
store staff enough information to make a fair judgment call in the
moment, and gives the retailer an accurate record of what actually
happened afterwards.

## Why overrides are designed to be part of the record, not an exception

Store staff sometimes need to admit a customer despite an unusual
verification state: a genuine edge case, not a fraud attempt. DropOS is
designed to treat that override as a first-class, recorded action rather
than a silent workaround, so the retailer's operational record reflects
what actually happened on the day. The in-scanner override interface
itself is still being completed.
