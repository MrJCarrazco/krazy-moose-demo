# PLACEHOLDERS — krazy-moose demo (must resolve BEFORE commissioning)

Prospect: **Krazy Moose Subs**, 405 E Herning Ave, Wasilla, AK 99654 · (907) 357-8774
Repo: `MrJCarrazco/krazy-moose-demo`

## VERIFIED — safe to show (sourced, not invented)

| Item | Value on page | Source |
|---|---|---|
| Business name | Krazy Moose Subs | Yelp, TripAdvisor, BBB, DoorDash, order.online, akdelivered — all agree |
| Address | 405 E Herning Ave, Wasilla, AK 99654 | same set; BBB profile gives 99654-7125 |
| Phone | (907) 357-8774 | same set; `tel:+19073578774` |
| Category | Sandwich / sub shop | Yelp category "Sandwiches"; TripAdvisor "Quick Bites, American" |
| TripAdvisor rating | 4.6, 248 reviews | tripadvisor.com Wasilla restaurant list |
| TripAdvisor rank | #1 of 95 Wasilla restaurants | TripAdvisor (also #1 in Wasilla "Sandwiches") |
| Yelp rating | 4.3, 207 reviews | Yelp business page (recorded at build time) |
| Menu **item names** (cold subs, hot subs, grilled sandwiches, salads, cookies, chips, drinks, party platters) | Menu section, verbatim | akdelivered.com partnered menu + Uber Eats store page — the shop's own published menu |
| Sizes: 5″ / 10″ / 20″ / wrap / salad | size chips | same published menus |
| "Place all large orders a minimum of 24 hours in advance" | party-platter card, quoted | akdelivered.com restaurant info, verbatim |
| Party platter feeds 8–10, choose 2 cold sandwich types | party-platter card | akdelivered.com menu, verbatim |
| Hours — Yelp column | Mon 10:30–4, Tue–Fri 10:30–6, Sat 10:30–4, Sun closed | Yelp listing, **labelled as Yelp's** |
| Hours — akdelivered column | Mon 10:30–3, Tue–Fri 10:30–5:45, Sat 10:30–3:45, Sun closed | akdelivered.com, **labelled as that platform's ordering hours** |
| Third window 10:00 am – 5:55 pm | mentioned in source note | order.online store header |
| 10″ Cheese Steak listed at $16.45 / $18.95 / $19.45 | price-divergence table, **labelled as the platforms' listed prices, not the shop's** | order.online / Uber Eats / DoorDash store pages |
| No website of their own | pitch section | No first-party domain found; order.online is listed as "website" on several profiles |
| Existing listings linked (Facebook, Yelp, TripAdvisor, order.online, akdelivered, DoorDash) | chips in Find section | each URL loaded and confirmed to be this business |
| Map pin ≈ 61.5823, -149.4404 | OSM embed, caption says approximate | BBB schema geo 61.582264,-149.440445; place listing 61.582324,-149.440115 |

## PLACEHOLDERS / UNVERIFIED — visible on page as placeholders, or deliberately omitted

| Item | Status on page | Action before live |
|---|---|---|
| **Counter prices** | **Visible dashed placeholder.** No price is presented as the shop's. Only the platforms' own listed prices appear, in a table that names each platform | Owner supplies real counter prices |
| **Authoritative hours** | **Two labelled, conflicting columns + a visible dashed placeholder.** No single schedule is asserted as correct | Owner confirms the real counter hours + holiday closures |
| **Daily specials, soups, seasonal cookie flavours** | Named in the placeholder box as not published anywhere | Owner supplies |
| **All photography** | **Four dashed "YOUR PHOTO HERE" blocks.** Zero images ship with the page — no stock food photos | Owner supplies storefront, a cut 10″ sub, the cookies |
| **The shop's own story / copy** | Fourth placeholder block, "Your words here" | Owner writes it |
| **Founding year / years in business** | **Deliberately omitted.** A BBB profile lists foundingDate 2007 and an Alaska registry entry for "Krazy Moose Subs LLC 2" dates to 2020 — these conflict and neither is the business's own statement | Owner states a real year |
| **Owner / staff names** | **Deliberately omitted.** A BBB profile names two individuals; not published by the business itself, and not needed | Owner decides |
| **Email address** | **Deliberately omitted.** Two addresses appear in third-party scrapes (one a personal-looking Yahoo address, one a hiring address) — neither is published by the business as a customer contact | Owner supplies a business address |
| **Customer testimonials / quotes** | **Zero on the page.** Review text exists publicly but is other people's copyrighted words; only aggregate scores are cited, with sources | Owner collects quotes with permission |
| **Awards / certifications / health score** | **Deliberately omitted** | Add only if real |
| **Google rating** | **Omitted.** Third-party aggregators report wildly different Google counts (658, 749, 777) — no reliable figure | Read it off the real Google Business Profile |
| **"Historic building", "second floor", "bread made in-house"** | **Omitted.** These appear only in third-party blog and review text, never in the business's own words | Owner confirms, then it becomes copy |
| **Catering / platter form** | Disabled (JS `alert`), labelled "nobody at the shop receives this" | Wire `action="https://formsubmit.co/OWNER_EMAIL"` on commission |
| `robots noindex,nofollow` | **ON** | Remove ONLY after commissioning + owner approval |
| Logo / brand colours | Hand-coded antler SVG + amber/charcoal palette. No logo used (no permission) | Request logo + colours |
| Domain | none; demo on github.io | Check availability on commission |

## Sourcing conflicts worth knowing before the call
- **Yelp's own numbers move.** Captured as 4.3/207 for this build; crawls days apart show 4.4/198 and 4.4/202. The page says the figures were recorded at build time and that live figures move.
- **Hours disagree across three platforms** (Yelp / akdelivered / order.online). This is a feature of the pitch, not a defect of the page — it is the clearest argument for owning one authoritative source.
- **Price for the same item differs by ~18%** across order.online, Uber Eats and DoorDash. Shown as a sourced table, explicitly not attributed to the shop.
- **Two Alaska entity records** ("Krazy Moose Subs" and "Krazy Moose Subs LLC 2") share the address. Do not assert a legal entity name.

## No fabricated claims
No testimonials, no invented ratings, no invented review counts, no years in business, no awards, no certifications, no staff names, no menu prices, no stock photography. Every menu item name on the page is transcribed from the business's own published ordering menu.

## Agency identity
Visible agency credit is **"Digital Consulting Studios"** only. No personal human byline appears anywhere in the page (verified by grep against the served bytes: 0 occurrences of each personal identifier).

## Reduced-motion bug (the one that has broken three previous demos)
House CSS carries a blanket `@media (prefers-reduced-motion: reduce){*{animation:none!important}}` while the hero elements are declared `opacity:0;animation:rise … forwards`. Killing the animation leaves them permanently invisible — a phone with Reduce Motion on shows a **blank hero**: no headline, no CTA, no phone number.

Fixed here by a scoped restoration at the end of the sheet:

```css
@media (prefers-reduced-motion: reduce){
  .antler,.kicker,.hero h1,.hero .sub,.cta-row,.hero .pin,
  .reveal,.reveal.d1,.reveal.d2,.reveal.d3{
    opacity:1!important;transform:none!important;animation:none!important
  }
  .hero h1 .glow,h2 em{background-position:0 0!important}
  .scroll-hint{display:none}
}
```

Verified on the **live** URL in a single active foreground tab with `prefers-reduced-motion` emulated to `reduce`: **6/6 hero elements** (`.antler`, `.kicker`, `.hero h1`, `.hero .sub`, `.cta-row`, `.hero .pin`) have computed `opacity: 1` and a non-zero bounding box, plus all `.reveal` elements visible.

## Other bugs found and fixed during this build (verified live)
1. **Gradient headings clipped their last glyph.** `-webkit-background-clip:text` clips to the glyph box, which cut the overhang of a trailing italic character (the ″ in "5″ to 20″"). Fixed with `padding-right` on `h2 em`.
2. **Hero address line hid behind the sticky call bar on a phone.** The banner + header take ~190px and the sticky bar covers the bottom ~55px; vertical centring pushed the `📍 405 E Herning Ave…` line underneath it. On phones the hero is now top-aligned with a tightened rhythm. Measured on a 390×844 viewport: address line bottom **759px**, sticky bar top **789px** — clear, with both CTAs and the phone number above the fold. No horizontal overflow at 390px.

## Deploy gate
Deploy pre-approved per the demos model (precedent: `true-north-collective` → MrJCarrazco/true-north-demo). Pages repo: `MrJCarrazco/krazy-moose-demo`, main / root. The business has **not** been contacted in any way.
