# CLAUDE.md — JoinMaxLifeMD B2B Affiliate Website Build

## Project Overview
Build a single-page B2B affiliate recruitment website for **JoinMaxLifeMD** — the brand name for MaxLifeMD's partner/affiliate program. This site targets chiropractors, gym owners, personal trainers, med spas, wellness coaches, and physical therapists who want to earn recurring commissions by referring patients to MaxLifeMD's telemedicine HRT & peptide therapy platform.

**Brand name on all website copy:** "JoinMaxLifeMD" (not "MaxLifeMD" alone — the affiliate brand is "JoinMaxLifeMD")
**Live reference (existing B2C affiliate page):** https://maxlifemdrx.com/affiliate-fitness/
**Competitor references studied for this build:**
- https://info.telewellnessmd.com/join-our-advertiser-program (affiliate value props, FAQ structure)
- https://getlyric.com/telehealth-partner-program/ (partner credibility stats, white-label positioning)
- https://www.gobymeds.com/partnerships/medical-affiliates (application form structure, medical affiliate UX)
- https://www.frontrowmd.com (clinician trust badges, doctor-powered credibility model)
- https://www.medbridge.com/affiliates (healthcare education affiliate structure)
- https://help.gethealthie.com/article/1219-healthies-affiliate-program (SaaS-style affiliate onboarding)
- https://www.dentulupro.com/patient-affiliates.html (patient-referral affiliate model)
- https://fancymeds.com/us/advocates-program (advocate/ambassador program structure)
- https://www.simplepractice.com/partners/ (professional partner program layout)

**This build is a standalone, high-conversion affiliate recruitment site** designed to convert local wellness providers into JoinMaxLifeMD affiliate partners.

## Tech Stack & Deployment
- **Framework:** Single-file HTML/CSS/JS (no framework dependency) OR Next.js static export — builder's choice based on complexity
- **Hosting:** Hostinger Cloud Startup plan, deployed via GitHub auto-deploy
- **GitHub repo:** `affiliateMD` (under bb313x account)
- **Branch:** Deploy from `main` branch → `public_html` directory on Hostinger
- **Domain:** Will be configured post-build (likely joinmaxlifemd.com or similar)
- **No backend required** — all CTAs route to external GoHighLevel booking link: `https://api.leadconnectorhq.com/widget/bookings/affiliateconsultationmaxlife`
- **Application form:** Built inline on the page (see Section 12 below) — does NOT route to GoHighLevel. The form collects partner application data and submits to GoHighLevel via webhook or embed.

## Design System

### Color Palette
```css
:root {
  --brand-navy: #1B4D6E;
  --brand-navy-dark: #0D2B3E;
  --brand-navy-light: #2A6F8E;
  --accent-coral: #E8593C;
  --accent-coral-light: #FEF0EC;
  --accent-gold: #F4A623;
  --bg-warm: #FAFAF8;
  --card-white: #FFFFFF;
  --text-primary: #1A2B3C;
  --text-muted: #6B7C8D;
  --border-light: #E8ECF0;
}
```

### Typography
- **Headings:** Cormorant Garamond (Google Fonts) — serif, weight 700. This matches the existing Daven Insurance site aesthetic (serif-forward, professional, high-trust).
- **Body / UI text:** System font stack: `system-ui, -apple-system, 'Segoe UI', sans-serif`
- **Heading sizes:** H1=32-36px, H2=24-28px, H3=16-18px
- **Body size:** 15-16px, line-height 1.6
- **Accent pattern:** Use `<em>` tags in headings styled as coral (#E8593C) instead of italic — e.g., "Turn your practice into a <em>revenue engine</em>"

### Visual Style
- **Aesthetic:** Premium medical/wellness — not startup-y, not clinical. Think "high-end advisory firm meets modern telehealth." Clean, spacious, trustworthy.
- **Hero:** Gradient background (navy-dark → navy → navy-light at 135deg), white text, gold accent on key stats
- **Curved section dividers:** Use CSS clip-path ellipse transitions between sections (hero → white, dark → light)
- **Cards:** White bg, 1px #E8ECF0 border, 12px border-radius, subtle hover lift (transform translateY(-2px) + shadow)
- **CTAs:** Coral (#E8593C) primary buttons, 8px border-radius, 600 weight, slight scale on hover
- **Icons:** Use simple Unicode or inline SVG — no icon library dependency needed. Keep minimal.
- **Images:** Stock photos of gym interiors, chiropractors with patients, wellness professionals. Use Unsplash or Pexels. Optimize to WebP.
- **NO generic AI aesthetics:** No purple gradients, no Inter/Roboto, no floating blobs or abstract shapes.

## Page Sections (Top to Bottom)

### 1. Navigation
- Fixed/sticky nav on scroll
- Logo: "JoinMaxLifeMD" text logo (bold sans, gold "MD" accent) — or use the existing MaxLifeMD logo image from https://maxlifemdrx.com/wp-content/uploads/2024/06/MaxLife-MD-Logo-Transparent-BG-1-1024x256.png with "Join" prepended
- Nav links: Why Join | How It Works | Earnings | Apply | Partner Types | FAQ
- "Apply Now" as a coral CTA button in the nav (scrolls to application form section)
- Mobile: hamburger menu

### 2. Hero Section
- Badge pill: "B2B PARTNER PROGRAM" (uppercase, small, translucent bg)
- H1: "Turn your practice into a **revenue engine**" (gold emphasis on "revenue engine")
- Subtext: "Refer patients to board-certified telemedicine doctors for HRT, peptide therapy, and weight loss. You earn recurring commissions. We handle all medical, compliance, and pharmacy."
- Two CTAs: "Apply Now" (coral solid) + "Learn More" (outline)
- Stats bar: "47 States Covered" | "$8,400+ Avg. Partner Earnings/Year" | "Zero Medical Liability"
- Background: Navy gradient with subtle grid/dot pattern overlay for texture

### 3. Why Become a JoinMaxLifeMD Affiliate (NEW SECTION — inspired by TeleWellnessMD, Lyric, GobyMeds, FrontRowMD)
This section is CRITICAL for conversion. It answers "why should I care?" before showing "how it works." Use a 2x3 or 3x2 card grid with icons.

- Section heading: "Why partner with **JoinMaxLifeMD**"
- Subtext: "Help your patients thrive while you build a sustainable new revenue stream — backed by physician-supervised telehealth you can trust."

**Card 1: Recurring Revenue, Not One-Time Fees**
Earn competitive monthly commissions on every active patient — not just a one-time referral bonus. As patients refill prescriptions and continue care, you earn. Month after month. No cap on earnings.

**Card 2: Physician-Supervised, HIPAA-Compliant Care**
Every patient is evaluated by a board-certified telemedicine physician. All consultations are HIPAA-secure. All prescriptions are clinically appropriate and at the sole discretion of the prescribing provider. Your reputation is protected.

**Card 3: Zero Inventory, Zero Liability, Zero Hassle**
You never touch a medication, manage a shipment, or handle patient records. JoinMaxLifeMD manages all medical consultations, pharmacy fulfillment, prescription management, and ongoing patient monitoring. You simply refer.

**Card 4: FDA-Registered, U.S.-Based Compounding Pharmacy**
All medications are sourced from FDA-registered, U.S.-based compounding pharmacies. Patients receive pharmaceutical-grade treatments with full regulatory compliance. Quality your patients can trust and you can stand behind.

**Card 5: Full Marketing Toolkit — Print & Digital**
Receive co-branded flyers, posters, business cards, QR codes, social media templates, email copy, and a custom landing page — all designed to make referrals effortless. We even ship physical materials to your office.

**Card 6: Dedicated Affiliate Success Team**
You're not alone. Every partner gets personalized onboarding, compliance training, performance reporting, and a dedicated point of contact. We help you optimize campaigns and grow your earnings over time.

**Optional trust signals row beneath cards (inspired by Lyric and FrontRowMD):**
- "47 states covered" | "Board-certified physicians" | "FDA-registered pharmacy" | "HIPAA-compliant platform" | "LegitScript approved"
- Consider adding a "Clinician-Trusted" or "Doctor-Backed" badge similar to FrontRowMD's medical badge concept

### 4. How It Works (3 Steps)
- Section heading: "Three steps. **Zero hassle.**"
- Step 1: "Apply & get approved" — Complete a 2-minute application. We verify your business and activate your custom referral dashboard within 48 hours.
- Step 2: "Share your link with patients" — Use your custom referral link, QR code, or co-branded materials in your office, texts, emails, and social media.
- Step 3: "Get paid monthly — forever" — Earn $25–$50 per patient per month, every month they stay subscribed. No caps. No clawbacks. Real recurring revenue.
- Visual: Numbered circles (coral bg) with connecting line/arrow between them

### 5. Commission Tiers (3-Column Cards)
- Section heading: "Partner tiers & **earnings**"
- Three cards side by side (responsive → stack on mobile):

**Starter Tier:**
- $25/patient/month
- 0–10 active patients
- Custom referral link & QR code
- Digital marketing kit
- Monthly payouts (NET-30)

**Pro Tier (FEATURED — coral border accent):**
- $35/patient/month
- 11–50 active patients
- $100 bonus per 10th referral
- Co-branded landing page
- Physical marketing kit shipped to your location
- Bi-monthly payouts (NET-15)

**Elite Tier:**
- $50/patient/month
- 51+ active patients
- $250 bonus per 25th referral
- Full co-branded experience
- Dedicated account manager
- Weekly payouts (NET-7)

### 5. Earnings Calculator (Interactive)
- Section heading: "Calculate your **earnings**"
- Slider: "Number of referred patients" (1–100)
- Auto-updating output cards:
  - Monthly earnings (patients × tier rate)
  - Annual earnings (monthly × 12)
  - Current tier name
  - Per-patient rate
- Tier logic: 0-10 = $25 (Starter), 11-50 = $35 (Pro), 51+ = $50 (Elite)
- Smooth, responsive — this is the "sticky" interactive element that sells

### 6. Who Partners With Us (Dark Section)
- Navy background section
- 6 partner type cards in a 3×2 grid (2×3 on mobile):
  1. Chiropractors — "Add HRT & peptides to your recovery toolkit"
  2. Gym Owners — "Help members break through plateaus"
  3. Personal Trainers — "Offer what supplements can't"
  4. Med Spas — "Layer HRT into your anti-aging menu"
  5. Wellness Coaches — "Back your guidance with real medicine"
  6. Physical Therapists — "Accelerate patient recovery timelines"
- Each card: simple icon (SVG or Unicode) + title + one-line description

### 7. What's Included
- Section heading: "Everything you need to **succeed**"
- Feature grid (2 columns):
  - High-converting landing pages (custom to your business)
  - Plug-and-play marketing materials (print + digital)
  - Lifetime recurring commissions on all purchases
  - HIPAA-compliant, doctor-led telemedicine care
  - No inventory, no liability, no hassle
  - Dedicated affiliate support team
  - Real-time referral tracking dashboard
  - Co-branded patient experience

### 8. Testimonials
- Section heading: "Partners are **earning**"
- 2–3 testimonial cards with quote, name, title
- Testimonial 1: "This partnership has been a game changer. I've got members finally losing fat after years of frustration. And as a gym owner, I've added thousands in passive revenue." — Coach Joe, Gym Owner
- Testimonial 2: "My chiropractic patients were already asking about peptides for inflammation and recovery. Now I have a compliant, doctor-supervised way to connect them with real treatment — and I earn for every referral." — Dr. Martinez, Chiropractor, NJ
- Testimonial 3: "I was skeptical at first, but the onboarding was so easy. Within two weeks I had my first three referrals. MaxLifeMD handles everything — I just share the link." — Sarah K., Wellness Coach, FL

### 9. FAQ (Accordion)
- Section heading: "Frequently asked **questions**"
- Expandable accordion items:

Q: Do I need a medical license to be an affiliate?
A: No. You are referring patients to MaxLifeMD's licensed telemedicine doctors. You never prescribe, diagnose, or treat. Your role is simply to share information and connect patients to our platform.

Q: What does MaxLifeMD handle?
A: Everything medical: telemedicine consultations with board-certified physicians, lab ordering and review, prescription management, compounding pharmacy fulfillment, medication shipping, and ongoing patient monitoring. You handle zero of it.

Q: How much can I realistically earn?
A: With 20 active referred patients at the Pro tier ($35/patient/month), you'd earn $700/month or $8,400/year in recurring passive income. Top partners with 50+ patients earn $2,500+/month.

Q: What treatments can my patients access?
A: GLP-1 weight loss (semaglutide, tirzepatide), NAD+ therapy, testosterone optimization, hormone replacement therapy, peptide protocols (BPC-157, Sermorelin, CJC-1295/Ipamorelin), sexual health, and sleep optimization. All physician-supervised.

Q: Is there any cost to become an affiliate?
A: No. The program is completely free to join. We provide all marketing materials, your custom referral dashboard, and ongoing support at no cost.

Q: What about compliance and liability?
A: MaxLifeMD maintains all medical licenses, HIPAA compliance, and malpractice insurance. As an affiliate, you have zero medical liability. You're sharing information about a telemedicine service — the same way you might recommend a nutritionist or specialist.

Q: How do I get paid?
A: Commissions are paid monthly via direct deposit or PayPal. You can track all referrals and earnings in real-time through your partner dashboard.

Q: Can I be an affiliate if I'm outside NJ/NY/FL?
A: Yes! MaxLifeMD serves patients in 47 states. While our initial affiliate recruitment focuses on NJ, NY, and FL, we welcome partners from any state.

### 10. Become an Affiliate — Application Form (NEW SECTION — inspired by GobyMeds medical affiliates form)
This is the PRIMARY conversion point of the page. All "Apply Now" CTAs throughout the page should smooth-scroll to this section. The form should be clean, professional, and embedded directly on the page — NOT a link to an external form.

- Section heading: "Apply to become a **JoinMaxLifeMD** partner"
- Subtext: "It takes less than 3 minutes. We review every application within 48 hours."
- Form background: Light warm bg (#FAFAF8) with a subtle card container (white, 1px border, 16px border-radius)

**Form Fields (modeled after GobyMeds + TeleWellnessMD application):**

Row 1 (2 columns):
- First Name (text, required)
- Last Name (text, required)

Row 2 (2 columns):
- Email Address (email, required)
- Phone Number (tel, required)

Row 3 (2 columns):
- Business Name (text, required)
- Business Website (url, optional)

Row 4 (2 columns):
- Business Type (dropdown, required): Chiropractic Practice | Gym / Fitness Studio | Personal Training | Med Spa / Aesthetics | Wellness Coaching | Physical Therapy | Naturopath / Nutritionist | Other
- State (dropdown, required — list all 50 states)

Row 5 (full width):
- Estimated Number of Patients/Members/Clients (dropdown): Under 50 | 50–100 | 100–250 | 250–500 | 500+

Row 6 (full width):
- How did you hear about JoinMaxLifeMD? (dropdown): Google Search | Social Media | Referral from Another Partner | Industry Event | Other

Row 7 (full width):
- Anything else you'd like us to know? (textarea, optional, 3 rows)

Row 8 (full width):
- Checkbox: "I agree to the JoinMaxLifeMD Affiliate Program Terms & Conditions and understand that as an affiliate I will not provide medical advice, diagnose, prescribe, or treat patients." (required)

Submit button: "Submit Application" (coral, full-width on mobile, centered on desktop)

**Form submission:** POST to GoHighLevel webhook endpoint (Bryan will configure this). For the build, use a placeholder action URL and add a success state that shows: "Application received! We'll review your information and be in touch within 48 hours. Check your email for next steps."

**Below the form, add a trust bar:**
- "Free to join" | "No medical license required" | "47 states" | "HIPAA compliant" | "Recurring commissions"

### 11. Final CTA Section (below form, for visitors who scroll past)
- Full-width navy gradient background
- H2: "Questions before you apply?"
- Subtext: "Schedule a free 15-minute consultation with our affiliate team. We'll walk you through the program, answer your questions, and help you decide if JoinMaxLifeMD is right for your practice."
- Large coral CTA: "Schedule a Free Consultation" → links to GoHighLevel booking: https://api.leadconnectorhq.com/widget/bookings/affiliateconsultationmaxlife
- Secondary link: "Or email us at affiliates@maxlifemdrx.com"

### 12. Footer
- JoinMaxLifeMD logo
- Links: Home | Contact Us | Terms & Conditions | Privacy Policy | Telehealth Consent
- LegitScript seal (if applicable): https://static.legitscript.com/seals/38004082.png
- Copyright: © 2026 JoinMaxLifeMD. All rights reserved.
- Disclaimer: "JoinMaxLifeMD is a partner program of MaxLifeMD, a telemedicine platform that connects patients with licensed healthcare providers. Affiliate partners do not provide medical services. All medical decisions, including treatment and prescriptions, are at the sole discretion of the prescribing provider. Payment does not guarantee the prescribing or dispensing of medication."

## Performance & SEO Requirements
- Lighthouse score target: 90+ on all metrics
- Meta title: "JoinMaxLifeMD | Earn Recurring Revenue Referring Patients to Telemedicine HRT & Peptide Therapy"
- Meta description: "JoinMaxLifeMD — the affiliate program for chiropractors, gyms, trainers, and wellness pros. Earn $25-$50/patient/month in recurring commissions referring patients to physician-supervised HRT, peptide therapy, and weight loss. Free to join. Zero medical liability."
- Open Graph tags for social sharing (og:title, og:description, og:image)
- Schema.org markup for local business / medical business
- Lazy-load all images
- Minify CSS/JS in production
- Mobile-first responsive design (breakpoints: 480, 768, 1024, 1280)

## Files to Create
1. `index.html` — Full single-page site with all sections including inline application form
2. `styles.css` — All styles (or inline in `<style>` if single-file preferred)
3. `script.js` — Calculator logic, accordion, smooth scroll, mobile nav, form validation & submission (or inline in `<script>`)
4. `README.md` — Basic deployment instructions for Hostinger + GitHub

## Deployment Notes
- GitHub repo: `affiliateMD` under bb313x account
- Hostinger auto-deploy: main branch → public_html
- Previous deployment issue: nested public_html directory bug was manually resolved via File Manager — ensure build output goes directly to root of public_html, not a subdirectory
- Test at Hostinger temporary URL before pointing custom domain

## Additional Design Inspiration Notes

### From TeleWellnessMD (affiliate value props):
- Their "Why Partner" section uses 6 icon cards with clear benefit headlines — we've adopted this pattern for our "Why Become an Affiliate" section
- Their FAQ is comprehensive (8+ questions) — we match this depth
- Their "refill-based system" messaging around building "sustainable, predictable monthly income" is strong — incorporate this language into the commission tier descriptions
- Their "Join Us in Redefining Wellness" mission statement section is a nice touch — consider adding a brief mission/vision block near the bottom

### From Lyric Health (partner credibility):
- Their stats bar (6M+ members, 58% repeat users, $150M+ savings, JD Power ranked) builds instant credibility — we've adapted this with our own stats in the hero
- Their "White Label Platform — Your Brand, Our Engine" positioning is powerful for more sophisticated partners — consider mentioning co-branding capabilities more prominently
- Their partner testimonials from named organizations add real credibility — when real testimonials are available, replace placeholder ones

### From GobyMeds (application form + medical affiliates):
- Their form is clean, professional, and inline on the page (not a separate URL) — we've modeled our form after this
- Their "Your Patients Trust You. We Support You." messaging resonates — incorporate similar trust-bridge language
- Their "Revenue for Your Time" framing is excellent — positions commissions as compensation for patient education, not just referral fees
- Their "Clinical Toolkit" concept (patient handouts, digital resources) aligns with our marketing kit offering

### From FrontRowMD (clinician trust):
- Their "Clinicians' Choice" medical badge concept is interesting — consider developing a "JoinMaxLifeMD Trusted Partner" badge that affiliates can display on their websites and in their offices
- Their model of doctors recommending products "without compensation" (just cashback for patients) addresses the trust/conflict-of-interest concern head-on — our compliance section should emphasize that affiliates earn for education and referral, not for influencing medical decisions

### From SimplePractice Partners:
- Their clean, professional partner page layout with clear tiers and a simple application flow is best-in-class for B2B SaaS partnerships — we've adopted similar clarity in our tier structure
- Their emphasis on "grow your practice" rather than "make money" puts the partner's business growth first — mirror this framing in headlines

### From FancyMeds Advocates Program:
- Their ambassador/advocate model where partners get product discounts + commissions is a nice dual incentive — consider offering affiliates a personal discount on MaxLifeMD products they use themselves (builds product knowledge and personal testimony)
