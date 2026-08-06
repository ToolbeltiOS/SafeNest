# F3 — Smart App Banner + real App Store URL

> ## ✅ EXECUTED 2026-08-06
>
> Apple approved **build 4**. Shipped in commit `7aae533`, live on safenest.lol.
>
>     APP_STORE_ID = 6786512308
>     https://apps.apple.com/app/safenest-know-before-you-move/id6786512308
>
> **What actually shipped**, against the plan below:
>
> | Planned | Outcome |
> |---|---|
> | Real App Store link replacing the placeholder | Done — and the placeholder text/dashed badge is gone entirely, replaced by Apple's official badge artwork (sha256 `a26fc5b3…`, committed to `brand/appstore-badge.svg`, never hotlinked or altered) |
> | Smart App Banner on all 80 pages | **79/79 real pages.** The 80th `.html` is the 53-byte Google Search Console verification token — not markup, and adding a meta tag would break verification. Deliberately excluded. |
> | "Re-decide the hierarchy" | Ruled: report stays primary (immediate-gratification purchase, conversion machinery behind it); App Store badge is a strong secondary directly below. Device-aware — on iOS the badge leads, since the app is free to search and the banner already offered the handoff. |
>
> **A trap worth recording.** The iOS reordering was first written as
> `flex-direction: row-reverse` and was a **no-op** — the two CTAs wrap onto
> separate lines at most widths, and reversing a wrapped row reorders within
> each line only. It looked identical to desktop and would have shipped as a
> feature that did nothing. Caught by screenshotting the iOS variant and
> comparing geometry, not by reading the CSS. Now uses `order`, verified live:
> badge `top:356`, report `top:435`.
>
> Beyond the plan, three things this batch had to fix that it did not
> anticipate: the 25 city pages needed the app's honest mention restored, the
> Premium section still hedged "available today instead", and **terms §7 was
> factually wrong** — it sent every buyer to Apple for refunds, including web
> buyers whose money moves through Stripe.
>
> Nothing below is outstanding. Kept as the record of what was staged and why.

---

