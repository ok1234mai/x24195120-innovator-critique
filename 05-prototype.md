# RainbowFiddle Prototype Specification

## Version: 1.0 MVP
**Status:** Functional Prototype (Demo-Ready)
**Date:** April 2026
**Platforms:** iOS 15+, Android 12+, WebAR (Chrome, Safari, Firefox)

---

## 1. Prototype Scope

The MVP prototype demonstrates the core user journey: discovering the Rainbow Cat at a heritage location, interacting via movement, and sharing the experience. It includes:

- 1 fully playable AR encounter (Dublin/Temple Bar location)
- Onboarding flow (3 screens)
- Core interaction engine (motion-responsive)
- Social sharing module
- Mood tracking post-experience

---

## 2. Visual Design System

### Color Palette

| Name | Hex | Usage |
|------|-----|-------|
| Emerald Root | #1A5F4A | Primary brand color, headers, buttons |
| Sunset Gold | #E8A849 | Accents, highlights, CTAs |
| Mist Grey | #F5F3F0 | Backgrounds, cards |
| Midnight | #1C1C1E | Primary text |
| Rainbow Gradient | Linear(#FF6B6B, #FFE66D, #4ECDC4, #A78BFA, #FF6B9D) | Special effects, the Cat's aura |
| Soft White | #FFFFFF | Text on dark backgrounds |

### Typography

| Element | Font | Weight | Size | Line Height |
|---------|------|--------|------|-------------|
| H1 (Hero) | Fraunces | 700 | 56px | 1.1 |
| H2 (Section) | Fraunces | 600 | 36px | 1.2 |
| H3 (Card) | Fraunces | 500 | 24px | 1.3 |
| Body | DM Sans | 400 | 16px | 1.6 |
| Caption | DM Sans | 400 | 12px | 1.4 |
| Button | DM Sans | 600 | 14px | 1.0 |

### Spacing System (8pt Grid)

- **xs:** 4px
- **sm:** 8px
- **md:** 16px
- **lg:** 24px
- **xl:** 32px
- **2xl:** 48px
- **3xl:** 64px
- **4xl:** 96px

### Border Radius

- **Buttons:** 12px
- **Cards:** 16px
- **Modals:** 24px
- **Images:** 12px
- **Full-round:** 9999px (avatars, badges)

### Shadows

| Level | Value |
|-------|-------|
| Soft | 0 2px 8px rgba(26,95,74,0.08) |
| Medium | 0 4px 16px rgba(26,95,74,0.12) |
| Strong | 0 8px 32px rgba(26,95,74,0.16) |
| Glow (Rainbow) | 0 0 40px rgba(168,139,250,0.4) |

---

## 3. Component Specifications

### A. The Rainbow Cat (AR Character)

| Attribute | Spec |
|-----------|------|
| Base Size | 120px × 120px (screen space) |
| Animation States | Idle (floating), Dance (4 keyframes), Follow, Magic Burst |
| Color Scheme | White base with iridescent rainbow mane and tail |
| Glow Radius | 20px ambient glow in rainbow gradient |
| Movement Speed | 0.5s ease-in-out between positions |
| Dance Moves | 4: Irish step-tap, Spin, Wave paw, Jump |
| Interaction Trigger | Device gyroscope + camera feed analysis |
| Performance Target | 60fps on iPhone 12+, Pixel 6+ |
| Fallback | Static illustration for older devices |

### B. Apple Portal (Location Marker)

| Attribute | Spec |
|-----------|------|
| Size | 80px × 80px idle, 100px × 100px on approach |
| Idle Animation | Gentle pulse (scale 1.0 → 1.05), 2s loop |
| Color | Emerald green with golden shine highlight |
| Icon | Stylized apple silhouette |
| Interaction | Tap to open story portal |
| Audio Cue | Soft chime on 3m proximity |

### C. Story Portal Overlay

| Attribute | Spec |
|-----------|------|
| Background | Blurred camera feed (backdrop-filter: blur(20px)) |
| Border | 1px rainbow gradient border |
| Width | 90vw max, 360px max |
| Padding | 24px |
| Content | Title, narration toggle, start button |
| Animation | Fade in 300ms + slide up 20px |

### D. Mood Tracker Modal

| Attribute | Spec |
|-----------|------|
| Trigger | Automatic after 60s or manual via button |
| Style | Bottom sheet, 80vw, rounded top corners |
| Mood Scale | 1-5 emoji scale (😔 → 😐 → 🙂 → 😊 → 🌟) |
| Reflection | 3 text inputs: "What surprised you?", "What did you feel?", "Who would you share this with?" |
| CTA | "Save & Share My Moment" (primary) |

### E. Social Share Card

| Attribute | Spec |
|-----------|------|
| Dimensions | 1080px × 1920px (Instagram Story), 1200px × 628px (Facebook) |
| Content | AR screenshot + Cat + proverb overlay |
| Filters | 3 presets: "Celtic Mist", "Golden Hour", "Neon Dublin" |
| Caption Template | "I just danced with the Rainbow Cat in Dublin 🐱🌈 #RainbowFiddle #IrishMagic" |
| Share Targets | Instagram, TikTok, Twitter/X, WhatsApp, native share sheet |

---

## 4. User Flow (Prototype)

```
[1] App Launch
    ↓
[2] Onboarding (3 slides, skip available)
    - Slide 1: "Welcome to Ireland's Magic"
    - Slide 2: "Find the Rainbow Cat"
    - Slide 3: "Dance with Your Heritage"
    ↓
[3] Location Permission Request
    ↓
[4] Map View (demo: Temple Bar highlighted)
    ↓
[5] Approaching Location → Apple Portal Appears
    ↓
[6] Tap Apple → Story Portal Opens
    ↓
[7] Narrated Intro (30s audio + text)
    ↓
[8] "Begin the Dance" → AR Camera Activates
    ↓
[9] Rainbow Cat Appears → User Dances
    ↓
[10] Magic Effects Trigger → Photo Capture Prompt
    ↓
[11] Mood Tracker → Rate Experience
    ↓
[12] Social Share → Return to Map
```

---

## 5. Technical Prototype Specs

### AR Implementation

| Aspect | Spec |
|--------|------|
| Primary | 8th Wall WebAR (no app install required for web) |
| Fallback | Native ARKit (iOS) / ARCore (Android) via Expo |
| Tracking | Plane detection (horizontal), marker-based fallback |
| Lighting | Environment lighting estimation for realistic shadows |
| Occlusion | People occlusion enabled where supported |
| Persistence | Cloud Anchor for multi-user sync (Phase 2) |

### Motion Detection

| Gesture | Detection Method | Cat Response |
|---------|------------------|---------------|
| Walking forward | GPS delta + accelerometer | Cat follows |
| Spin/rotate | Gyroscope > 90°/s | Cat spins |
| Reach out | Accelerometer spike + arm pose ML model | Magic burst |
| Jump | Vertical accelerometer | Cat jumps |
| Stand still | < 0.1g variance for 3s | Cat sits, looks at user |

### Performance Budgets

| Metric | Target |
|--------|--------|
| Time to Interactive | < 3s on 4G |
| AR Load Time | < 2s |
| Frame Rate | 60fps (min 30fps) |
| Bundle Size | < 25MB |
| Battery Impact | < 8% per 15min session |
| Memory Peak | < 300MB |

---

## 6. Prototype Screens (Static Mockups)

### Screen 1: Onboarding Hero
- Full-bleed Irish landscape image (Cliffs of Moher at sunset)
- Large Fraunces heading: "Your ancestors are waiting"
- Subtle parallax on scroll
- Skip button top-right

### Screen 2: Map View
- Stylized Dublin map with illustrated landmarks
- Glowing pulse on Temple Bar
- Bottom sheet with current location details
- "Start Adventure" floating button

### Screen 3: AR Experience
- Full-screen camera with overlaid Cat
- Minimal UI: close button (top-left), music toggle (top-right)
- Gesture hint arrows at bottom (first use only)
- Rainbow particle effects on interactions

### Screen 4: Share Card Preview
- AR screenshot as background
- Celtic knot frame overlay
- Animated proverb text
- Edit button for filters
- Share buttons row

---

## 7. Accessibility Compliance

| Feature | Implementation |
|---------|----------------|
| VoiceOver/TalkBack | Full audio descriptions, semantic labels |
| Reduce Motion | Option to disable animations, static Cat fallback |
| Color Blind | High-contrast mode, pattern-based UI elements |
| Small Text | 200% zoom support without horizontal scroll |
| Haptic Feedback | Optional vibration on interactions |

---

## 8. Testing Protocol (Prototype Phase)

| Test Type | Participants | Criteria |
|-----------|--------------|----------|
| Usability | 15 Irish millennials | Task completion > 90% |
| Performance | 30 devices | 60fps on target devices |
| Accessibility | 5 users with disabilities | WCAG 2.1 AA |
| Emotional Response | 50 sessions | Net Promoter Score > 40 |
| AR Accuracy | 100 location tests | < 1m drift, correct plane placement |

---

*This prototype specification defines the MVP scope for investor demonstration and beta testing.*
