
# Current State

[Document current card/background styling inconsistencies across pages]

| Page | Background Color | Border Radius | Border | Box Shadow | Padding |
|------|------------------|---------------|--------|------------|---------|
|      |                  |               |        |            |         |

## Proposed State

### Card Component

| Property | Token |
|----------|-------|
| Background | `component.card.background` → `foundations.white` (#FFFFFF) |
| Border | `component.card.border` → `slate.200` (#BDBFC5) |
| Border-radius | `component.card.borderRadius` → `border-radius.md` (8px) |
| Padding | `component.card.padding` → `spacing.lg` (16px) |

### Surface/Background

| Property | Token |
|----------|-------|
| Page background | `surface.background.page` → `slate.25` (#F4F6F9) |
| Card background | `surface.background.card` → `foundations.white` (#FFFFFF) |
| Default border | `surface.border.default` → `slate.200` (#BDBFC5) |
| Secondary border | `surface.border.secondary` → `slate.300` (#9CA9BD) |
| Interactive border | `surface.border.interactive` → `blue.500` (#2c70d3) |

### Elevation

| Property | Token |
|----------|-------|
| Box-shadow | `shadow.default` (0 0 12px rgba(0,0,0,0.1), 0 1px 2px rgba(0,0,0,0.1), 0 1px 3px rgba(0,0,0,0.08)) |

### Related Tokens

| Property | Token |
|----------|-------|
| Border-radius (sm) | `border-radius.sm` (4px) |
| Border-radius (md) | `border-radius.md` (8px) |
| Border-radius (lg) | `border-radius.lg` (12px) |
| Border-width (thin) | `border-width.thin` (1px) |

## Migration Checklist

| Page | Route | CSS to Remove |
|------|-------|---------------|
|      |       |               |

### QA Steps
1. Verify card background is #FFFFFF
2. Confirm border is 1px solid #BDBFC5
3. Check border-radius is 8px
4. Verify page background is #F4F6F9


____

# locations.linda.co

## Summary of Card Types Found

The site uses several distinct card/box styling patterns across different page types. Here's a comprehensive breakdown:

---

## 1. GLOBAL CARD STYLES

### Standard Widget Cards
**Used on:** `/locations/{id}` (Location Dashboard), Audit Reports
- **Class:** `.widget`
- **Background:** `rgb(255, 255, 255)` (white)
- **Border:** `1px solid rgba(189, 197, 209, 0.64)` (light gray)
- **Border Radius:** `4px`
- **Box Shadow:** `none`

### Panel Cards
**Used on:** `/gmb/locations/{id}/edit`
- **Class:** `.panel.panel-default`
- **Background:** `rgb(255, 255, 255)` (white)
- **Border:** `1px solid rgb(215, 215, 215)` (gray)
- **Border Radius:** `1px`

---

## 2. STAT CARDS

### Post Stats (Posts Page)
**URL:** `/gmb/locations/{id}/local_posts`
- **Class:** `.stat-card`
- **Background:** `rgb(255, 255, 255)` (white)
- **Border:** `1px solid rgb(224, 224, 224)` (light gray)
- **Border Radius:** `8px`
- **Dimensions:** ~204px × 83px

### Call Tracking Stats
**URL:** `/call_tracking/incoming_calls`
- **Class:** `.incoming-calls-stats__card`
- **Background:** `rgb(244, 247, 252)` (light blue)
- **Border Radius:** `16px`

---

## 3. ALERT/BANNER CARDS

### Orange Warning Banner (Top Alert)
**Used on:** All GMB location pages
- **Class:** `.alert.alert-warning.rounded-lg`
- **Background:** `rgb(249, 174, 52)` (orange)
- **Border:** `1px solid rgba(0, 0, 0, 0)`
- **Border Radius:** `4.8px`
- **Text Color:** `rgb(255, 255, 255)` (white)

### Blue Info Alert
**URL:** `/gmb/locations/{id}/edit`
- **Class:** `.alert.alert-info-secondary`
- **Background:** transparent
- **Border:** `1px solid rgb(55, 125, 255)` (blue)
- **Text Color:** `rgb(55, 125, 255)` (blue)

### Dark Alert
- **Class:** `.alert.alert-dark`
- **Background:** `rgb(106, 106, 106)` (gray)
- **Text Color:** `rgb(255, 255, 255)` (white)

---

## 4. EMPTY STATE CARDS

**Used on:** `/reports`, `/gallery`, `/gb/moments`, `/gb/widgets`, `/keywords`, `/facebook_accounts`
- **Background:** `rgb(255, 255, 255)` (white)
- **Border:** `1px solid` (subtle gray)
- **Border Radius:** `4px`
- Contains illustration + CTA button

---

## 5. FEATURE CARDS

**URL:** `/call_tracking/phone_numbers`
- ROI Insights, Call Recording, Detailed Stats, Smart Routing
- **Background:** `rgb(255, 255, 255)` (white)
- **Border:** Subtle gray
- **Border Radius:** `4px`
- Contains icon + title + description

---

## 6. REVIEW CARDS

**URL:** `/gmb/locations/{id}/reviews`
- Timeline-style cards with user avatar
- **Background:** `rgb(255, 255, 255)` (white)
- **Border:** Subtle bottom border for separation
- Contains star rating, review text, reply section

---

## 7. MEDIA CARDS

**URL:** `/gmb/locations/{id}/media/identity`
- Image thumbnail cards
- **Background:** Dark gray `rgb(60, 60, 60)` container area
- **Border:** `2px solid` (blue when selected)
- Contains image, status label (green "Submitted" badge)

---

## 8. CHANGE LOG DIFF CARDS

**URL:** `/locations/{id}/change_log`
- Before/After comparison cards
- **Background:** Light yellow tint for changes
- **Border:** `1px solid rgb(215, 215, 215)`
- Contains side-by-side state comparison with arrow

---

## 9. INFORMATION/DISCLAIMER CARDS

**URL:** `/google_accounts`
- **Class:** `.alert` style
- **Background:** Light blue tint
- **Border:** Blue border
- **Text Color:** Blue

---

## PAGES WITH CARDS (BY URL)

| URL Pattern | Card Types Present |
|-------------|-------------------|
| `/locations/{id}` | Widget cards (stats charts), Map sidebar card |
| `/locations/{id}/automation` | Section cards with illustrations |
| `/locations/{id}/change_log` | Diff comparison cards |
| `/locations/{id}/keywords` | Empty state card |
| `/gmb/locations/{id}/edit` | Panel cards, Warning alerts |
| `/gmb/locations/{id}/media/*` | Image media cards |
| `/gmb/locations/{id}/local_posts` | Stat cards, Post cards |
| `/gmb/locations/{id}/reviews` | Review timeline cards |
| `/gmb/locations/{id}/questions` | Empty state card, Warning alert |
| `/reports` | Empty state card |
| `/gallery` | Empty state cards (2 sidebar cards) |
| `/audit_report_configurations/{id}/reports/{id}` | Section cards (Geogrid, Categories, etc.) |
| `/call_tracking/incoming_calls` | Blue stat cards |
| `/call_tracking/phone_numbers` | Feature cards, Quick Setup card |
| `/google_accounts` | Info disclaimer card |
| `/facebook_accounts` | Empty state card |
| `/gb/moments` | Empty state card |
| `/gb/widgets` | Empty state card |

---

## PAGES WITHOUT CARD ELEMENTS (Table-based layouts)

| URL | Layout Type |
|-----|-------------|
| `/locations` | Data table |
| `/reviews_dashboard` | Filter + table |
| `/scheduled_geogrids_index` | Data table |
| `/live_geogrids_index` | Data table |
| `/audit_reports` | Data table |

---

## BACKGROUND COLORS REFERENCE

| Color | RGB Value | Usage |
|-------|-----------|-------|
| White | `rgb(255, 255, 255)` | Primary card background |
| Light Blue | `rgb(244, 247, 252)` | Stat cards (Call Tracking) |
| Orange | `rgb(249, 174, 52)` | Warning banners |
| Gray | `rgb(106, 106, 106)` | Dark alerts |
| Page Background | `rgb(249, 250, 252)` | Main page background |

---

## CSS CLASSES SUMMARY
```css
/* Standard Widget Card */
.widget {
  background: rgb(255, 255, 255);
  border: 1px solid rgba(189, 197, 209, 0.64);
  border-radius: 4px;
}

/* Stat Card (Posts) */
.stat-card {
  background: rgb(255, 255, 255);
  border: 1px solid rgb(224, 224, 224);
  border-radius: 8px;
}

/* Stat Card (Call Tracking) */
.incoming-calls-stats__card {
  background: rgb(244, 247, 252);
  border-radius: 16px;
}

/* Orange Warning Banner */
.alert.alert-warning.rounded-lg {
  background: rgb(249, 174, 52);
  border: 1px solid rgba(0, 0, 0, 0);
  border-radius: 4.8px;
  color: rgb(255, 255, 255);
}

/* Blue Info Alert */
.alert.alert-info-secondary {
  background: transparent;
  border: 1px solid rgb(55, 125, 255);
  color: rgb(55, 125, 255);
}

/* Panel Card */
.panel.panel-default {
  background: rgb(255, 255, 255);
  border: 1px solid rgb(215, 215, 215);
  border-radius: 1px;
}
```