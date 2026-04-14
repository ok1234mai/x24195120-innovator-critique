# Solution Design: RainbowFiddle

## Overview

**RainbowFiddle** is an AR-powered cultural wellness platform that transforms Irish mythological stories into immersive, movement-based experiences in urban spaces. Users interact with magical creatures (starting with the legendary "Cat of the Rainbow") through their smartphone cameras, triggering AR encounters that respond to their physical movements—dancing, walking, reaching—creating embodied cultural moments.

---

## Solution Architecture

### Core Product: Mobile AR Experience App (iOS & Android)

**Name:** RainbowFiddle
**Tagline:** "Dance with your ancestors."

### How It Works

1. **Geolocation Activation:** Users approach designated cultural heritage zones (Temple Bar, St. Stephen's Green, Ha'penny Bridge, etc.) in Dublin; the app recognizes the location via GPS and AR anchors.

2. **Story Portal:** The app displays a glowing "apple" icon at the location. Tapping it opens the mythological narrative (audio narration in Irish/English with subtitles).

3. **AR Creature Manifestation:** The Rainbow Cat appears in the camera view, projected onto real-world surfaces. The creature responds to user movement via the device's motion sensors.

4. **Movement Triggers:** Dancing in front of the screen causes the Cat to dance alongside, creating a duet. Walking triggers the Cat to follow. Gestures (reaching, spinning) unlock different magical effects (glowing trails, musical notes, blooming flowers).

5. **Social Layer:** Users can record 15-second AR clips, add Irish proverbs/filters, and share to social platforms. Friends can "join" via link, creating a shared AR experience.

6. **Well-being Tracking:** After each session, users rate their mood (1-10) and answer a 3-question reflection prompt. The app tracks "Cultural Wellness Score" over time.

---

## Provider Profile

### Organization Type: **B Corp Certified Social Enterprise / Startup Hybrid**

**Name:** RainbowFiddle Labs Ltd.
**Legal Structure:** Private limited company (Ltd.) with B Corp pending certification
**Founded:** 2024, Dublin, Ireland

### Mission Alignment
RainbowFiddle operates as a **social enterprise**—profit is secondary to cultural and well-being impact. We partner with Fáilte Ireland (tourism), the Arts Council, and local councils to access heritage sites and funding.

### Revenue Model

| Stream | Description | % of Revenue |
|--------|-------------|--------------|
| B2C App Download | Free base app; premium "Mythic Pass" ($4.99/month) unlocks all stories | 35% |
| B2B Partnerships | Cultural institutions license the platform for their sites | 30% |
| Brand Experiences | Irish whiskey, tourism brands sponsor specific AR encounters | 20% |
| Merchandise | Physical "Apple Tokens" that unlock exclusive content (NFC-enabled) | 10% |
| Research Grants | Well-being outcome data sold (anonymized) to academic institutions | 5% |

---

## Key Features

### For End Users (Urban Irish Millennials & Diaspora)

- **6 Mythological Encounters** in the launch version (Dublin: 4, Cork: 1, Galway: 1)
- **Multi-language Support:** Irish Gaelic, English, Spanish, Mandarin
- **Offline Mode:** Download one story at a time for areas with poor connectivity
- **Accessibility Modes:** Audio description, high-contrast AR, reduced-motion option

### For Partner Institutions

- **Analytics Dashboard:** Real-time data on user engagement, dwell time, emotional response
- **Custom Story Integration:** Museums can create their own AR experiences using our creator tool
- **Co-marketing:** Brand visibility within AR encounters

### For Investors & Impact Funders

- **Measurable Outcomes:** 30+ well-being metrics tracked per user per session
- **Cultural Impact Report:** Annual publication of engagement statistics and well-being improvements
- **Scalability Blueprint:** 3-year plan for expansion to Edinburgh, Wales, Brittany (Celtic nations)

---

## Technology Stack

| Component | Technology |
|-----------|------------|
| AR Engine | 8th Wall (WebAR—no app download required) + ARKit/ARCore fallback |
| Backend | Supabase (PostgreSQL, Auth, Realtime) |
| CDN & Media | Cloudflare Workers + Mux |
| Analytics | Mixpanel + custom event tracking |
| Payments | Stripe |
| Deployment | Vercel (web), Expo (native wrapper) |
| Design | Figma → Framer for prototyping |

---

## Competitive Advantage

| Competitor | Weakness | RainbowFiddle Advantage |
|------------|----------|------------------------|
| Heritage Ireland apps | Passive, text-heavy, no AR | Fully immersive, movement-responsive |
| Pokemon Go | No cultural depth, extractive model | Purpose-driven, community-building |
| Wander (VR travel) | Disembodied, isolating | Embodied, local, shareable |
| Local museums | Fixed location, fee barriers | Mobile, free, urban-scattered |

---

## Team Composition

- **Founder/CEO:** Cultural historian + startup operator
- **CTO:** AR/ML engineer from Trinity College Dublin
- **CDO:** Experience designer from Abbey Theatre
- **COO:** Former Fáilte Ireland partnerships lead
- **Advisors:** Professor of Digital Humanities (UCD), Managing Director (Dogpatch Labs alumni)

---

## Impact Metrics (Year 1 Targets)

- **Downloads:** 50,000
- **Monthly Active Users:** 15,000
- **Average Session Duration:** 8.5 minutes
- **Well-being Score Improvement:** +18% average per session
- **Stories Shared:** 100,000 social shares
- **Partner Sites Activated:** 25
- **Revenue:** €400,000
