# User Workflows

DropOS has three distinct people moving through a drop: the **customer**,
the **store team** on the ground, and the **retailer admin** who configured
the drop. Each has a different experience of the same underlying workflow.

## Customer workflow

1. **Discover the drop** — the customer finds a branded registration page
   for the specific launch, carrying the retailer's own look and feel.
2. **Register interest** — the customer submits their details against the
   drop's eligibility rules. Registration is time-boxed to the drop's open
   window.
3. **Wait for an outcome** — depending on demand, the customer is either
   allocated a place or held on a waitlist if the drop is oversubscribed.
4. **Receive a reservation and access pass** — an allocated customer
   receives a confirmed collection window and a unique, time-boxed QR
   access pass — not a code that can be freely shared or reused.
5. **Arrive and be verified** — at the store, the customer presents their
   pass. Verification is near-instant and gives the customer a clear
   outcome, not an ambiguous manual check.
6. **Collect** — a verified customer completes their collection or
   purchase with the store team.

## Store team workflow

1. **Open the scanner** — store staff use a purpose-built, mobile-first
   scanner interface rather than the full retailer dashboard — full-bleed,
   camera-first, designed for one-handed operation during a busy event.
2. **Scan each arriving customer's pass** — the scanner reads the QR code
   and returns one of four clear states (valid, invalid/expired, wrong
   collection window, or already checked in) rather than leaving staff to
   interpret a raw result.
3. **Act on the state** — a valid pass leads straight to admission. An
   unusual state (wrong window, already used) gives staff the information
   they need to make a judgment call. Accountable staff overrides for
   these cases are part of the designed product model; the in-scanner
   override interface itself is still being completed.
4. **Keep moving** — the interface is built to reset quickly after each
   scan, since the constraint on a launch day is throughput under pressure,
   not any single transaction.

## Retailer admin workflow

1. **Set up the campaign** — configure the drop: product details, store
   location(s), available stock, registration window, and which
   allocation approach to use.
2. **Monitor registration** — watch registrations arrive against capacity
   in real time, ahead of the drop's key decision points.
3. **Run or review allocation** — depending on the drop's configuration,
   allocation runs automatically as registrations arrive, or as a
   dedicated step once the registration window closes.
4. **Manage the invite and waitlist pool** — see who has been allocated a
   place, who is waitlisted, and the overall shape of demand for the drop.
5. **Watch the event live** — on launch day, follow check-ins and
   operational status as they happen, across one or multiple store
   locations.
6. **Review afterwards** — see registration, allocation and check-in
   activity as a complete operational record once the drop has closed.

## What ties these together

All three workflows read from and write to the same underlying system of
record. A store team's scan updates the same check-in record a retailer
admin sees in their live reporting. A customer's registration is the same
record an admin's allocation step acts on. There is one operational
timeline per drop, not three disconnected views of it.
