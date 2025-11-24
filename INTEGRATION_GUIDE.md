# Nutrition Landing Page - Integration Guide

## 📋 Overview

This is a high-converting, mobile-first landing page for CrossFit Leiden's nutrition coaching programs. The page focuses on getting visitors to book a Goal Review with Coach Annie.

**Live Page:** `index.html`
**Primary CTA:** Book Goal Review
**Booking URL:** `https://kilo.gymleadmachine.com/widget/bookings/crossfitleiden/goalreview?user_id=FCGLJ30Zesqd3ZV6nbLR`

---

## 🎨 Design System

### Color Palette
```javascript
colors: {
    'brand-teal': '#14B8A6',      // Primary CTA, accents
    'brand-warm': '#F97316',      // Secondary CTA, 1-on-1 program
    'brand-soft': '#F3F4F6',      // Backgrounds
}
```

### Typography
- **Font Stack:** System fonts (Apple SF, Segoe UI, Roboto)
- **Headlines:** Bold, 3xl-6xl (responsive)
- **Body:** 16-20px, gray-600
- **Line Height:** Relaxed (1.625)

### Spacing & Layout
- **Max Width:** 4xl-7xl depending on section
- **Padding:** 4-8 on mobile, 6-8 on desktop
- **Section Spacing:** py-16 sm:py-24 (vertical rhythm)
- **Grid:** Single column mobile, 2-5 columns desktop

### Design Principles
- **Mobile-first:** Single column, full-width CTAs
- **Whitespace:** Generous padding and margins
- **Rounded corners:** 2xl (1rem) for cards and images
- **Shadows:** Soft shadows (sm-xl) for depth
- **Gradients:** Subtle background gradients (teal/orange)

---

## 🏗️ Page Structure

### 1. Sticky Header
```html
<header class="sticky top-0 z-50 bg-white border-b">
  - Logo: "CrossFit Leiden"
  - CTA Button: "Book Goal Review"
</header>
```

### 2. Hero Section
- **Layout:** 2-column (text left, image right on desktop)
- **Headline:** "Eat better. Feel stronger. With a plan that fits your life."
- **Subheading:** Program options overview
- **CTA:** Large "Book Goal Review" button (brand-warm)
- **Trust Line:** "Warm, personal support in the heart of Leiden."
- **Image:** Hero image (691ef44c330ab57ef1da3eed.png)

### 3. How It Works (4 Steps)
- **Layout:** 4-column grid (2x2 on mobile, 4x1 on desktop)
- **Style:** Numbered circles with different colors
- **Steps:**
  1. Book your Goal Review (teal)
  2. Set your personal plan (warm orange)
  3. Weekly guidance (light teal)
  4. See and feel the results (light orange)

### 4. Meet Coach Annie
- **Layout:** 2-column (image left, text right)
- **Image:** Coach photo (690ddfa4b23abd77a66a3e1b.png)
- **Copy:** Warm introduction, non-judgmental tone
- **CTA:** "Book Goal Review" button

### 5. Program 1: 1-on-1 Coaching
- **Card Style:** Orange gradient background
- **Price:** €350/month, minimum 2 months
- **Features:**
  - Fully personalised
  - Choose data-driven or principles-based
  - High accountability
  - Focus on basics (protein, veggies, movement, calories)
- **CTA:** "Book Goal Review"
- **Best for:** Maximum support and clear results

### 6. Program 2: 28-Day Kickstart
- **Card Style:** Teal gradient background
- **Price:** €200 total, 28 days
- **Features:**
  - Group-based program
  - Daily check-ins
  - Weekly focus themes
  - Simple actionable steps
  - Can repeat once
- **CTA:** "Book Goal Review"
- **Best for:** Group energy and 4-week boost

### 7. Comparison Section
- **Desktop:** Clean table with alternating backgrounds
- **Mobile:** Stacked cards (orange and teal)
- **Rows:** Structure, Support, Approach, Price, Duration, Best for
- **CTA:** "Book Goal Review" after table

### 8. Testimonials
- **Layout:** 3-column grid (1 column on mobile)
- **Style:** White cards with quote icons
- **Quotes:**
  - "I finally stopped overthinking food..."
  - "I felt supported the whole way..."
  - "Annie helped me understand what works for me..."

### 9. FAQ Section
- **Style:** Native HTML `<details>` accordion
- **Questions:** 5 common questions
- **Styling:** Gray background, rounded corners, rotating arrow icon

### 10. Final CTA Section
- **Background:** Gradient (teal-orange-teal)
- **Headline:** "Ready to feel better in your body?"
- **CTA:** Large "Book Goal Review" button

### 11. Footer
- **Background:** Dark gray (gray-900)
- **Content:** Brand name, location, tagline
- **Tagline:** "Warm community. Personal support. Real results."
- **CTA:** Final "Book Goal Review" button

---

## 🎯 Brand Voice Guidelines

### Tone
- Warm, friendly, human
- Simple English, short sentences
- Supportive, non-judgmental
- Calm confidence + adventure + community

### What to AVOID
- No "crazy diet" language
- No extreme fitness jargon
- No aggressive "bro" language
- No complicated words
- No hype or exaggeration

### What to USE
- "Simple, healthy habits"
- "Fits your life"
- "No stress, no extremes"
- "Small changes, big results"
- "Warm, personal support"

---

## 🔗 Integration Checklist

### Required Assets
- [ ] Hero image: `https://storage.googleapis.com/.../691ef44c330ab57ef1da3eed.png`
- [ ] Coach Annie image: `https://storage.googleapis.com/.../690ddfa4b23abd77a66a3e1b.png`
- [ ] Booking widget URL (configured)

### Technical Requirements
- [ ] Tailwind CSS (via CDN or build process)
- [ ] Responsive meta viewport tag
- [ ] Smooth scroll behavior
- [ ] All CTAs link to booking URL

### Tailwind Config
```javascript
tailwind.config = {
    theme: {
        extend: {
            colors: {
                'brand-teal': '#14B8A6',
                'brand-warm': '#F97316',
                'brand-soft': '#F3F4F6',
            }
        }
    }
}
```

### Key CSS Classes
- **Buttons:** `px-10 py-4 rounded-lg font-semibold shadow-lg hover:shadow-xl`
- **Cards:** `rounded-3xl p-8 sm:p-12 shadow-xl border`
- **Images:** `rounded-2xl shadow-lg object-cover`
- **Gradients:** `gradient-to-br from-X-50 to-Y-50`

---

## 📱 Responsive Breakpoints

- **Mobile:** < 640px (sm)
- **Tablet:** 640px - 768px (md)
- **Desktop:** 1024px+ (lg)

### Mobile Optimizations
- Single column layout
- Full-width CTAs
- Stacked comparison cards
- Larger touch targets (min 44px)
- Simplified navigation

---

## 🚀 Performance Tips

1. **Images:** Use optimized WebP format where possible
2. **Lazy Loading:** Add `loading="lazy"` to images below fold
3. **CDN:** Host images on fast CDN (Google Cloud Storage used)
4. **Minify:** Minify HTML/CSS for production
5. **Caching:** Set proper cache headers

---

## 🔄 Integration Steps

### Option 1: Standalone Page
1. Copy `index.html` to your main site
2. Update header to match main site navigation
3. Link to it from main navigation
4. Test booking flow

### Option 2: Component Integration
1. Extract each section as a reusable component
2. Match existing site's component structure
3. Apply your site's global styles
4. Import Tailwind config colors
5. Test responsiveness

### Option 3: Full Redesign
1. Use this as template for site-wide refresh
2. Apply color palette across all pages
3. Implement design system (spacing, typography)
4. Update all CTA buttons to match style
5. Roll out section by section

---

## 📝 Copy Template

All section copy is finalized and approved. Key messaging:

**Value Proposition:**
"Eat better. Feel stronger. With a plan that fits your life."

**Programs:**
- 1-on-1: Personal, flexible, high accountability
- Kickstart: Group energy, structured, budget-friendly

**Coach:**
"Warm, calm, and clear in her guidance."

**CTA:**
"Book Goal Review" (leads to program selection during call)

---

## 🎯 Conversion Strategy

### Primary Goal
Get visitors to book a Goal Review call

### Secondary Goal
Help visitors understand which program fits them

### Key Tactics
- 8 CTA buttons strategically placed
- Clear program comparison
- Social proof (testimonials)
- Trust signals (FAQ, Coach intro)
- Low-friction booking (one URL for all CTAs)

---

## 🛠️ Customization Guide

### To Change Colors
Update Tailwind config (lines 17-21)

### To Change Copy
Look for `<!-- EDITABLE -->` comments in HTML

### To Change Pricing
Update in program sections (lines 224-226, 320-322)

### To Change Images
Replace `src` URLs in hero and coach sections

### To Change Booking Link
Find/replace all instances of booking URL (8 locations)

---

## 📊 Analytics Recommendations

Track these events:
- `cta_click` with program context
- `section_view` for scroll depth
- `booking_started` when widget opens
- `booking_completed` (via booking platform)

---

## ✅ Launch Checklist

- [ ] All images loading correctly
- [ ] All CTAs link to correct booking URL
- [ ] Mobile responsive on real devices
- [ ] Browser testing (Chrome, Safari, Firefox)
- [ ] Page speed test (aim for < 3s load)
- [ ] Booking flow tested end-to-end
- [ ] Analytics tracking implemented
- [ ] Meta tags and SEO optimized
- [ ] Favicon added
- [ ] SSL certificate active

---

## 🔗 Quick Reference

**Booking URL:**
`https://kilo.gymleadmachine.com/widget/bookings/crossfitleiden/goalreview?user_id=FCGLJ30Zesqd3ZV6nbLR`

**Hero Image:**
`https://storage.googleapis.com/msgsndr/s0YuoK12A9YPXCKsfUp3/media/691ef44c330ab57ef1da3eed.png`

**Coach Image:**
`https://storage.googleapis.com/msgsndr/s0YuoK12A9YPXCKsfUp3/media/690ddfa4b23abd77a66a3e1b.png`

**Tailwind CDN:**
`https://cdn.tailwindcss.com`

---

**Last Updated:** 2025-01-24
**Status:** Production Ready ✅
