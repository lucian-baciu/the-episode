# The Episode — website rebuild context

Last updated: 30 September 2026

## 1. Project summary

Rebuild [the-episode.ro](https://www.the-episode.ro/) from Wix as a fast, premium, conversion-focused website for **The Episode — Jacuzzi Penthouses** in Cluj-Napoca.

The new site should preserve the useful information and broadly familiar structure of the current website, while making the offer immediately understandable and substantially improving direct-booking conversion, property clarity, trust, photography hierarchy, multilingual SEO, accessibility, and performance.

This repository is the new implementation. The intended stack is:

- Next.js App Router and TypeScript
- Tailwind CSS
- shadcn/ui primitives, customized to the brand rather than shipped with default styling
- Server Components and static generation by default
- A third-party booking/PMS or channel-manager integration for live availability and reservations

The frontend should feel like a boutique hospitality brand, not a generic apartment listing, Wix template, or animation-heavy technology demo.

## 2. Business objective

The website must help a visitor answer these questions within seconds:

1. What is being offered?
2. Why is it special?
3. How many apartments are there, and how do they differ?
4. Is it trustworthy?
5. Is it available for my dates, and what does it cost?
6. How can I book or ask a question immediately?

Primary commercial goal: increase qualified direct booking starts and completed direct bookings.

Secondary goals:

- Increase WhatsApp enquiries from visitors who are not ready to book.
- Reduce dependence on OTA pages for basic information and reassurance.
- Build organic visibility for high-intent accommodation searches in Cluj-Napoca.
- Provide a clear RO/EN experience.
- Establish reliable measurement of the booking funnel.

## 3. Product positioning

The product is not merely “an apartment.” It is the combined experience of:

- a private, heated jacuzzi;
- a top-floor terrace;
- panoramic city views;
- privacy;
- an atmospheric night away in Cluj-Napoca;
- the convenience of underground parking and proximity to Iulius Mall.

Primary audience: couples looking for a romantic night, anniversary, birthday, or city break.

Secondary audiences:

- solo and business travellers;
- small groups or families of 2–4 people;
- visitors who value a private spa experience and parking;
- travellers who need to stay near Iulius Mall, FSEGA, EXPO Transilvania, or the airport.

The tone should be specific, warm, confident, elegant, and sensory. Avoid vague hotel language such as “Bucură-te de confort” unless it is supported by concrete details.

## 4. Current property facts

The following facts are supported by the current site or current marketplace listings, but all mutable facts must be rechecked before launch:

- Brand/listing name: The Episode — Jacuzzi Penthouses.
- The offer consists of **two top-floor apartments**.
- Each apartment has a private terrace and its own private hot tub/jacuzzi.
- The jacuzzi is heated and described as available throughout the year.
- Current marketplace descriptions position the units for 1–4 guests.
- A Booking.com listing describes a one-bedroom apartment with one double bed and one sofa bed, approximately 45 m².
- Amenities currently promoted include underground/on-site parking, air conditioning, Wi-Fi, equipped kitchen, TV, secured access, terrace/balcony, barbecue, and panoramic city views.
- Address shown publicly: Strada Teodor Mihali 31–35 / 31–33–35, floor 7, 400591 Cluj-Napoca, Romania. The exact canonical formatting must be confirmed.
- Contact number on the current website: +40 770 660 983. An external listing reportedly contains a different number; the canonical number must be audited before launch.
- The property is near Iulius Mall and FSEGA and is within reach of EXPO Transilvania and the airport.
- Booking.com snapshot on 30 September 2026: 9.6/10 from 236 reviews; facilities 9.7, cleanliness 9.6, comfort 9.7, value 9.4, location 9.5, staff 9.8, Wi-Fi 9.0. These values are dynamic and must never be hard-coded without an update process or a visible “last verified” policy.
- Airbnb snapshot on 30 September 2026: 4.9/5 from 77 reviews for the surfaced listing. This is also dynamic.

Reference pages:

- Current website: https://www.the-episode.ro/
- Booking property page: https://www.booking.com/hotel/ro/the-episode-jacuzzi-penthouse.ro.html
- Booking reviews: https://www.booking.com/reviews/ro/hotel/the-episode-jacuzzi-penthouse.en-gb.html
- Airbnb listing surfaced during discovery: https://www.airbnb.com/rooms/1144322083727239504

## 5. Current Wix website audit

The crawlable homepage currently contains:

- a hero headed “Evadarea Urbană: Apartamente Exclusiviste cu Jacuzzi Privat”;
- an address-led supporting line and reservation CTA;
- a services/amenities grid;
- a large, undifferentiated gallery;
- a short generic introduction;
- a map/contact area;
- a generic name/email/subject contact form;
- phone/WhatsApp and address details.

Main problems to solve:

- The hero does not communicate the product and differentiator strongly enough.
- The two apartments are not clearly separated, compared, or individually bookable.
- Photos from both units are mixed together, so a visitor cannot tell what they are booking.
- The long gallery documents the property instead of leading with emotion.
- Reviews and rating breakdowns are not prominent enough.
- Year-round jacuzzi availability is buried.
- The location is shown, but not sold through useful travel times and nearby landmarks.
- The contact form does not match accommodation-booking intent.
- Availability and price require too much hunting.
- Current image alternative text appears keyword-stuffed instead of descriptive.
- Current title and metadata are weak and generic.

## 6. Information architecture

Planned public routes:

```text
/
  redirect or locale negotiation

/ro
/en

/ro/penthouse-1
/ro/penthouse-2
/ro/galerie
/ro/locatie
/ro/intrebari-frecvente

/en/penthouse-1
/en/penthouse-2
/en/gallery
/en/location
/en/faq
```

The final slugs for the apartments must use the confirmed public names. Do not create dozens of thin SEO landing pages. Prefer 5–8 strong, useful pages per language.

Expected global navigation:

- Apartamente / Penthouses
- Galerie / Gallery
- Locație / Location
- Întrebări frecvente / FAQ
- RO / EN switcher
- Verifică disponibilitatea / Check availability

On mobile, use a persistent booking bar with a price hint when trustworthy pricing is available and a primary availability CTA. A separate floating WhatsApp action may be used if it does not obscure content or accessibility controls.

## 7. Homepage blueprint

### 7.1 Hero

Use the strongest real sunset/night jacuzzi photograph as a full-bleed visual. The image must immediately communicate private jacuzzi, rooftop atmosphere, and city view.

Working Romanian copy:

> **Penthouse cu jacuzzi privat și vedere panoramică în Cluj-Napoca**
>
> Două apartamente la ultimul etaj, cu terasă privată, jacuzzi încălzit tot anul și parcare subterană, lângă Iulius Mall.

Trust line, only with currently verified values:

> ★ 9,6/10 · 236 recenzii Booking

Primary CTA: **Verifică disponibilitatea**

Secondary CTA: **Scrie-ne pe WhatsApp**

### 7.2 Availability and price

Place an availability search immediately below or partially overlapping the hero:

- Check-in
- Check-out
- Oaspeți
- Verifică disponibilitatea

When the integration supports it, return bookable units and total price in context, for example:

> Penthouse One · 12–14 octombrie · 2 nopți · 1.480 lei · Rezervă

Do not imply live availability or direct-booking capability until the backend/channel manager is integrated and tested.

### 7.3 Trust strip

Keep this short and scannable. Candidate items:

- 9,6 Booking
- 236 recenzii
- Jacuzzi privat
- Parcare gratuită
- Check-in simplu

Dynamic ratings require a clear source and refresh strategy.

### 7.4 The two apartments

Show two large editorial cards, each with its own photography and page:

- confirmed apartment name;
- one strong photograph;
- bedroom count and maximum occupancy;
- jacuzzi, terrace, and view;
- meaningful differentiators between the two units;
- “Vezi apartamentul” CTA;
- availability/booking CTA where supported.

Never mix imagery without identifying the unit.

### 7.5 Curated gallery

Show approximately six exceptional images on the homepage:

1. jacuzzi at sunset or night;
2. terrace and skyline;
3. bedroom;
4. living room;
5. jacuzzi/day view;
6. one atmospheric detail.

Then link to the complete, unit-labelled lightbox gallery: **Vezi toate fotografiile →**

### 7.6 Reviews

Make social proof one of the largest sections. Include:

- overall source-specific rating and review count;
- category scores;
- 3–6 short, real, permission-safe review excerpts;
- source and date/verification context;
- link to the full external review source where appropriate.

Never fabricate, silently edit, or combine reviews. Avoid exposing reviewer data beyond what is needed and already public.

### 7.7 Experience-led section

Working direction:

> **O seară doar pentru voi**
>
> Jacuzzi fierbinte, priveliște peste Cluj și intimitatea unei terase la ultimul etaj.

Primary use cases: romantic weekend, anniversary or birthday, city break. Secondary use cases: business stay and groups of 2–4.

### 7.8 Year-round jacuzzi

This is a primary selling point, not a footnote.

Working direction:

> **Jacuzzi privat. 365 de zile pe an.**
>
> Apa este încălzită, iar jacuzzi-ul este disponibil inclusiv iarna.

Pair the section with a genuine winter or night photograph if one exists. Do not simulate seasonal conditions with misleading imagery.

### 7.9 Location

Headline direction: **Aproape de tot. Deasupra orașului.**

Show useful, verified walking/driving times for:

- Iulius Mall;
- FSEGA;
- EXPO Transilvania;
- Cluj International Airport;
- city centre.

Clarify the transport mode and avoid promising fixed travel times where traffic varies. The map is supporting content, not the entire location story.

### 7.10 Contact and final CTA

Replace the generic contact form with:

- availability/booking CTA;
- WhatsApp CTA;
- click-to-call fallback;
- optional concise enquiry flow only if it collects booking-relevant details.

Suggested prefilled WhatsApp opening:

> Bună! Am o întrebare despre The Episode pentru perioada …

## 8. Apartment page requirements

Each unit page should contain only that unit’s content:

- unique name and short positioning statement;
- hero image and clear “from” pricing only when supplied by the booking system;
- occupancy, beds, size, floor, check-in/out basics;
- private jacuzzi and terrace details;
- unit-specific amenities;
- curated unit-specific gallery;
- live availability and reservation CTA;
- concise policies;
- relevant reviews if they can be reliably attributed to the unit;
- location summary;
- FAQ entries relevant to the unit;
- links to compare or view the other penthouse.

## 9. Visual direction

The visual design should be restrained, editorial, warm, and premium.

Principles:

- Photography is the main visual asset.
- Favor cinematic crops, typography, whitespace, and deliberate pacing.
- Use warm neutrals and a dark evening tone that complements jacuzzi lighting and city views.
- Keep one clear primary action per section.
- Use subtle motion only where it improves comprehension or polish.
- Avoid parallax-heavy effects, decorative tech motifs, excessive gradients, glassmorphism, and generic luxury clichés.
- Components must remain accessible and readable over photography.
- Never use stock or generated property images as if they depict the real apartments.

The final identity direction, logo assets, color values, and typefaces remain to be confirmed.

## 10. Technical architecture

Use the Next.js App Router. The route implementation should follow the installed project foundation while aiming for this logical shape:

```text
app/
  [locale]/
    page.tsx
    penthouse/
      [slug]/page.tsx
    galerie/page.tsx
    locatie/page.tsx
    intrebari-frecvente/page.tsx
  sitemap.ts
  robots.ts
  opengraph-image.tsx or a validated static OG asset

components/
  ui/
  site/
  booking/

content/ or data/
  properties
  reviews
  faq
  translations
```

Architecture rules:

- Prefer Server Components and static generation.
- Keep client components limited to interactions such as date selection, gallery lightbox, mobile navigation, and booking widgets.
- Treat property content as structured data, not large hard-coded page fragments.
- Keep apartment identifiers stable across languages and booking integrations.
- Use `next/image` for real property images with responsive `sizes`.
- Preload only the true hero/LCP image; lazy-load lower content and full galleries.
- Generate canonical URLs and RO/EN `hreflang` relationships.
- Keep third-party widgets isolated so they do not dominate page performance or styling.
- Store secrets only in environment configuration; never commit credentials.

The current project foundation uses vinext/Cloudflare-compatible output for Sites hosting. No database or object-storage binding is enabled at this stage.

## 11. Booking and inventory integration

Do not build channel synchronization from scratch.

Core requirement: Booking.com, Airbnb, and the direct website must share reliable inventory so that direct bookings cannot create double bookings.

Preferred approach:

1. Select a PMS/channel manager that supports the existing channels.
2. Confirm it provides a hosted booking flow, embeddable widget, API, or deep links suitable for a custom Next.js frontend.
3. Make it the source of truth for availability, price, reservation, cancellation, and inventory updates.
4. Test simultaneous and near-simultaneous bookings across channels.

Periodic iCal-only synchronization should not be treated as equivalent to real-time inventory management without understanding its delay and overbooking risk.

Integration decision criteria:

- Booking.com and Airbnb connectivity;
- API/widget quality and branding control;
- Romanian lei and tax/fee handling;
- card/payment support and PSD2/SCA compatibility;
- cancellation/deposit rules;
- automated guest messages;
- webhooks or conversion callback capability;
- GDPR/data-processing terms;
- total monthly and per-booking cost;
- support quality;
- migration/export capability.

## 12. SEO and discoverability

Working Romanian homepage metadata:

- Title: **Penthouse cu Jacuzzi Privat în Cluj-Napoca | The Episode**
- Description: **Apartamente penthouse în Cluj-Napoca cu jacuzzi privat încălzit tot anul, terasă panoramică și parcare gratuită, lângă Iulius Mall.**

Natural search themes:

- cazare cu jacuzzi Cluj;
- apartament cu jacuzzi Cluj;
- jacuzzi privat Cluj;
- penthouse Cluj;
- cazare romantică Cluj;
- cazare lângă Iulius Mall.

SEO rules:

- Write for the visitor first; do not repeat keywords mechanically.
- Use descriptive image alt text, for example: “Jacuzzi privat pe terasa penthouse-ului The Episode la apus.”
- Use empty alt text for decorative images.
- Create unique metadata for every strong page.
- Add canonical URLs, RO/EN alternates, `sitemap.ts`, `robots.ts`, and an image-aware sitemap approach.
- Create a property-specific social preview, not a generic template card.
- Add valid JSON-LD using the most accurate supported schema types and property data.
- Vacation-rental structured data does not guarantee Google’s special accommodation experience; eligibility may depend on Google Hotel Center and additional requirements.
- Preserve or deliberately redirect useful existing URLs during the Wix cutover.

## 13. Analytics, consent, and conversion events

Likely analytics stack:

- Google Analytics 4;
- Meta Pixel only if Meta advertising is used;
- consent management appropriate to actual cookies, vendors, and Romanian/EU requirements.

Planned event vocabulary:

- `availability_search`
- `property_view`
- `booking_started`
- `booking_completed`
- `whatsapp_clicked`
- `phone_clicked`
- `booking_com_clicked`

Every event needs a documented trigger, parameters, and duplicate-prevention behavior. Do not send advertising or non-essential analytics before valid consent where consent is required.

## 14. Quality requirements

### Performance

- Optimize for excellent mobile Core Web Vitals.
- Serve appropriately sized AVIF/WebP variants when supported.
- Avoid loading the complete gallery on the homepage.
- Minimize client JavaScript and third-party scripts.
- Reserve image dimensions to prevent layout shift.
- Load booking widgets and maps intentionally rather than by default when possible.

### Accessibility

- Meet WCAG 2.2 AA as the working target.
- Provide semantic headings and landmarks.
- Maintain sufficient contrast over imagery.
- Ensure full keyboard operation and visible focus states.
- Make the gallery/lightbox, locale selector, date controls, and mobile booking bar accessible.
- Respect reduced-motion preferences.
- Use clear Romanian and English labels, validation, and error messages.

### Privacy and security

- Collect the minimum necessary personal data.
- Document every third-party processor.
- Provide privacy/cookie information and consent controls based on the final integrations.
- Validate server-side inputs and protect booking/enquiry endpoints from abuse.
- Never expose booking, analytics, or payment secrets in browser code.

## 15. Content and asset migration checklist

Before implementation is considered content-complete, obtain and organize:

- original, high-resolution property photos rather than compressed Wix derivatives;
- a unit-to-photo mapping for both apartments;
- confirmed apartment names and differentiators;
- logo/source brand assets and usage rules;
- exact address formatting;
- confirmed phone/WhatsApp number;
- official email address;
- amenities per unit;
- bed, occupancy, size, and accessibility details per unit;
- jacuzzi operating, cleaning, safety, and seasonal details;
- check-in/out, parking, cancellation, deposit, children, pets, smoking, and quiet-hours policies;
- approved review excerpts and their sources;
- verified landmark travel distances/times;
- booking/PMS provider details;
- legal company/operator details required in the footer and policies;
- Romanian master copy and approved English translation.

Image files should follow a consistent convention and retain ownership/license information. Suggested pattern:

```text
public/images/properties/{property-id}/{scene}-{sequence}.{ext}
```

## 16. Open decisions and risks

These must remain visible until resolved:

1. What are the official public names of the two apartments?
2. What concrete visual, layout, capacity, amenity, or view differences separate them?
3. Which photos belong to each apartment?
4. How are direct reservations handled today?
5. Is there an existing PMS/channel manager, payment processor, or booking engine?
6. Which phone number is canonical, and which external listings require correction?
7. Are current Booking/Airbnb ratings allowed to be shown and refreshed on the direct site, and by what mechanism?
8. What is the truthful “from” price, and can it be obtained live with all mandatory fees?
9. What are the exact walking/driving times to key landmarks?
10. Are both units legally and operationally offered under the same listing details and policies?
11. What domain/DNS access and Wix URL inventory are available for migration and redirects?
12. Which analytics, advertising, cookie, and legal requirements apply at launch?

Risks:

- presenting stale ratings, prices, or availability;
- double bookings from weak channel synchronization;
- mislabelling photos between units;
- losing Wix search equity during cutover;
- slowing the site with a third-party widget, gallery, maps, or tracking scripts;
- using marketplace content or guest quotes without suitable attribution/permission;
- inconsistent name, address, and phone data across directories.

## 17. Delivery sequence

Work in this order unless new information changes the dependencies:

1. Confirm facts, apartment naming, asset ownership, and current booking workflow.
2. Select/directly validate the PMS or booking integration.
3. Build the stronger hero and availability entry point.
4. Build clear apartment comparison and separate apartment pages.
5. Establish the curated photo system and full labelled gallery.
6. Add rating/review proof with a maintenance strategy.
7. Add the experience, year-round jacuzzi, and location story.
8. Add sticky mobile booking and WhatsApp actions.
9. Complete RO/EN content and locale routing.
10. Add metadata, structured data, redirects, sitemap, robots, and social preview.
11. Add analytics, consent, and conversion QA.
12. Complete accessibility, performance, responsive, booking, and launch checks.

## 18. Initial definition of done

The migration is ready for launch when:

- both apartments are accurately and separately represented;
- visitors can see real availability and total pricing or are clearly transferred to a trustworthy booking flow;
- inventory synchronization has been tested;
- mobile booking and WhatsApp actions work;
- RO and EN routes, metadata, canonicals, and alternates are correct;
- real photos are optimized and correctly labelled;
- ratings/reviews are sourced and maintainable;
- booking and contact funnel events are tested;
- consent and legal pages reflect the actual integrations;
- accessibility, responsive behavior, and Core Web Vitals have been checked;
- old Wix URLs have a redirect plan;
- production domain, HTTPS, sitemap, robots, and social previews are verified after cutover.

## 19. Scope of the current step

Completed in this first step:

- new project foundation;
- Next.js/TypeScript setup;
- Tailwind CSS setup;
- shadcn/ui setup;
- durable product, content, architecture, integration, SEO, analytics, migration, and risk context in this document.

Not part of this step:

- final visual design;
- homepage or interior page implementation;
- migration of property photos;
- booking/PMS integration;
- analytics or consent installation;
- production deployment or Wix cutover.
