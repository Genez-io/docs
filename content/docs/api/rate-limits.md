# Rate Limits

Each API key may make **200 requests a minute**. The limit is per key, so one
busy job does not slow down another system using a different key.

---

## When you go over

A request over the limit is answered with `429` and the code `rate_limited`.
Nothing is lost: the request simply did not run. Wait, then send it again.

---

## Staying under it

**Ask for more in one request.** A list endpoint returns many records at once.
Reading a page of results is one request; reading the same records one at a
time is many.

**Spread a large export.** If you are copying a long history into a warehouse,
add a short pause between pages rather than sending everything as fast as your
code can.

**Retry with a growing wait.** On a `429`, wait a second, then two, then four.
A retry loop with no wait will simply hit the limit again.

**Use a key per system.** Two jobs on two keys have 200 requests a minute each.
Two jobs on one key share 200 between them.

---

## If 200 a minute is not enough

The limit suits reporting, exports and dashboards. If you have a case that
genuinely needs more, talk to your account manager rather than working around
it with many keys — keys are also how access is bounded, and splitting them
for throughput weakens that.
