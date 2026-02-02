# Border & Stroke Documentation for locations.linda.co

## Summary

The application uses a consistent set of border styles across components. Below is a comprehensive breakdown of all border usage.

---

## BORDER COLOR PALETTE

| Color Name | RGB Value | Hex Equivalent | Opacity Variants |
|------------|-----------|----------------|------------------|
| **Gray (Primary)** | `rgb(189, 197, 209)` | `#BDC5D1` | 100%, 64%, 48% |
| **Light Gray** | `rgb(231, 234, 243)` | `#E7EAF3` | 100% |
| **Medium Gray** | `rgb(224, 224, 224)` | `#E0E0E0` | 100% |
| **Dark Gray** | `rgb(235, 235, 235)` | `#EBEBEB` | 100% |
| **Light Gray Alt** | `rgb(215, 215, 215)` | `#D7D7D7` | 100% |
| **Primary Blue** | `rgb(55, 125, 255)` | `#377DFF` | 100% |
| **Transparent** | `rgba(0, 0, 0, 0)` | - | 0% |
| **Card Border** | `rgba(34, 34, 34, 0.125)` | `#222222` | 12.5% |

---

## BORDER STYLES BY COMPONENT

### 1. Navbar Bottom Border
**Applied to:** Global navigation bar
```css
.navbar {
  border-bottom: 1px solid rgb(189, 197, 209);
}
```
- **Color:** `#BDC5D1` (Gray)
- **Width:** 1px
- **Style:** solid

---

### 2. Widget/Card Borders
**Applied to:** Dashboard widgets, stat cards, content containers
```css
.widget {
  border: 1px solid rgba(189, 197, 209, 0.64);
}
```
- **Color:** `#BDC5D1` at 64% opacity
- **Width:** 1px
- **Style:** solid
- **Border Radius:** 4px

**Used on:**
| Page | Element |
|------|---------|
| `/locations/{id}` | Statistics widgets, sidebar |
| `/call_tracking/incoming_calls` | Table rows |
| `/gmb/locations/{id}/edit` | Panel sections |
| `/locations/{id}/change_log` | Change log items |

---

### 3. Form Input Borders
**Applied to:** Text inputs, selects, multiselect dropdowns

#### Standard Input
```css
input, .multiselect {
  border: 1px solid rgb(189, 197, 209);
  border-radius: 4px;
}
```
- **Color:** `#BDC5D1`
- **Width:** 1px
- **Border Radius:** 4px

#### Alternative Input (Google Accounts page)
```css
.form-control {
  border: 2px solid rgb(235, 235, 235);
  border-radius: 0px;
}
```
- **Color:** `#EBEBEB`
- **Width:** 2px
- **Border Radius:** 0px (square)

---

### 4. Button Borders

#### Primary Button
```css
.btn-primary {
  border: 1px solid rgb(55, 125, 255);
  border-radius: 4px;
}
```
- **Color:** `#377DFF` (Primary Blue)
- **Width:** 1px

#### Context/Action Button
```css
.btn-context {
  border: 1px solid rgba(189, 197, 209, 0.48);
  border-radius: 4px;
}
```
- **Color:** `#BDC5D1` at 48% opacity
- **Width:** 1px

#### Outline Button (Secondary)
```css
.btn-outline {
  border: 1px solid rgb(55, 125, 255);
  border-radius: 4px;
}
```
- **Color:** `#377DFF`
- **Width:** 1px

---

### 5. Selection Card Borders

#### Active/Selected State
```css
.post-type-card.active,
.cta-option.active {
  border: 2px solid rgb(55, 125, 255);
}
```
- **Color:** `#377DFF` (Primary Blue)
- **Width:** 2px
- **Border Radius:** 8px (cards), varies for options

#### Inactive State
```css
.post-type-card {
  border: 2px solid rgb(224, 224, 224);
}
```
- **Color:** `#E0E0E0`
- **Width:** 2px

---

### 6. Stat Card Borders
**Applied to:** Post statistics, metric cards
```css
.stat-card {
  border: 1px solid rgb(224, 224, 224);
  border-radius: 8px;
}
```
- **Color:** `#E0E0E0`
- **Width:** 1px
- **Border Radius:** 8px

---

### 7. Alert/Info Box Borders

#### Blue Info Alert
```css
.alert-info-secondary {
  border: 1px solid rgb(55, 125, 255);
}
```
- **Color:** `#377DFF`
- **Width:** 1px

#### Transparent Border (Warning Alerts)
```css
.alert-warning {
  border: 1px solid rgba(0, 0, 0, 0);
}
```
- **Color:** Transparent
- **Note:** Background color provides visual boundary

---

### 8. Avatar/Image Borders
**Applied to:** Profile images, circular avatars
```css
.rounded-circle.bordered {
  border: 1px solid rgb(231, 234, 243);
}
```
- **Color:** `#E7EAF3` (Light Gray)
- **Width:** 1px
- **Border Radius:** 50% (circular)

---

### 9. Table Borders

#### Table Row
```css
tr {
  border: 1px solid rgba(189, 197, 209, 0.64);
}
```

#### Table Cell Right Border
```css
th, td {
  border-right: 1px solid rgba(189, 197, 209, 0.64);
}
```
- **Color:** `#BDC5D1` at 64% opacity
- **Width:** 1px

---

### 10. Panel/Card Header Borders
```css
.card-header {
  border: 1px solid rgba(34, 34, 34, 0.125);
}
```
- **Color:** `#222222` at 12.5% opacity
- **Width:** 1px

---

### 11. Divider/HR Borders
```css
hr.content-divider {
  border: 1px solid rgb(189, 197, 209);
}
```
- **Color:** `#BDC5D1`
- **Width:** 1px

---

### 12. Badge/Pill Borders
```css
.topic-badge {
  border: 1px solid rgb(224, 224, 224);
  border-radius: 16px;
}
```
- **Color:** `#E0E0E0`
- **Width:** 1px
- **Border Radius:** 16px (pill shape)

---

### 13. CTA Section Borders
```css
.cta-section {
  border: 1px solid rgb(224, 224, 224);
}
```
- **Color:** `#E0E0E0`
- **Width:** 1px

---

### 14. Third-Party Widget Border
**Applied to:** External/floating widgets
```css
/* External widget button */
button {
  border: 0.5px solid rgba(31, 30, 29, 0.4);
  border-radius: 12px;
}
```
- **Color:** Near-black at 40% opacity
- **Width:** 0.5px
- **Border Radius:** 12px

---

## BORDER RADIUS VALUES

| Value | Usage |
|-------|-------|
| `0px` | Square inputs (Google Accounts), some alerts |
| `1px` | Panels |
| `2px` | Tags |
| `4px` | Standard inputs, buttons, widgets, dropdowns |
| `4.8px` | Warning alerts (rounded-lg) |
| `5px` | Multiselect tags |
| `6px` | Status messages |
| `8px` | Stat cards, badges, selection cards |
| `12px` | External widgets |
| `16px` | Pill badges |
| `50%` | Circular avatars |

---

## BORDER USAGE BY PAGE

| URL | Border Elements |
|-----|-----------------|
| **All Pages** | Navbar bottom border, avatar borders |
| `/locations` | Table row/cell borders, multiselect borders, context buttons |
| `/locations/{id}` | Widget borders, sidebar border, dividers |
| `/locations/{id}/change_log` | Table borders, diff card borders |
| `/gmb/locations/{id}/local_posts` | Stat card borders, post card borders |
| `/gmb/locations/{id}/local_posts/new` | Selection card borders (active/inactive), CTA borders |
| `/gmb/locations/{id}/edit` | Panel borders, table borders |
| `/gmb/locations/{id}/reviews` | Panel border, sidebar border |
| `/call_tracking/incoming_calls` | Input borders, table borders |
| `/google_accounts` | Info alert border, form-control borders (2px), card header |
| `/gallery` | Button borders |
| `/audit_report_configurations/.../reports/...` | Info alert borders, outline buttons |

---

## CSS VARIABLES / TOKENS
```css
/* Border Color Tokens */
--border-color-primary: rgb(189, 197, 209);           /* #BDC5D1 */
--border-color-primary-64: rgba(189, 197, 209, 0.64);
--border-color-primary-48: rgba(189, 197, 209, 0.48);
--border-color-light: rgb(231, 234, 243);             /* #E7EAF3 */
--border-color-medium: rgb(224, 224, 224);            /* #E0E0E0 */
--border-color-dark: rgb(235, 235, 235);              /* #EBEBEB */
--border-color-blue: rgb(55, 125, 255);               /* #377DFF */
--border-color-card: rgba(34, 34, 34, 0.125);

/* Border Width Tokens */
--border-width-thin: 0.5px;
--border-width-default: 1px;
--border-width-thick: 2px;

/* Border Radius Tokens */
--radius-none: 0px;
--radius-sm: 2px;
--radius-default: 4px;
--radius-md: 6px;
--radius-lg: 8px;
--radius-xl: 12px;
--radius-pill: 16px;
--radius-circle: 50%;
```

---

## COMPLETE BORDER SPECIFICATIONS

| Border Style | Width | Color | Opacity | Radius | Usage |
|--------------|-------|-------|---------|--------|-------|
| `1px solid rgb(189, 197, 209)` | 1px | #BDC5D1 | 100% | 4px | Navbar, inputs, dividers |
| `1px solid rgba(189, 197, 209, 0.64)` | 1px | #BDC5D1 | 64% | 4px | Widgets, tables, sidebar |
| `1px solid rgba(189, 197, 209, 0.48)` | 1px | #BDC5D1 | 48% | 4px | Context buttons |
| `1px solid rgb(231, 234, 243)` | 1px | #E7EAF3 | 100% | 50% | Avatars |
| `1px solid rgb(224, 224, 224)` | 1px | #E0E0E0 | 100% | 8px | Stat cards, badges |
| `2px solid rgb(224, 224, 224)` | 2px | #E0E0E0 | 100% | 8px | Inactive selection cards |
| `2px solid rgb(55, 125, 255)` | 2px | #377DFF | 100% | 8px | Active selection cards |
| `1px solid rgb(55, 125, 255)` | 1px | #377DFF | 100% | 4px | Primary buttons, info alerts |
| `2px solid rgb(235, 235, 235)` | 2px | #EBEBEB | 100% | 0px | Form controls (alt) |
| `1px solid rgba(34, 34, 34, 0.125)` | 1px | #222222 | 12.5% | - | Card headers |
| `1px solid rgba(0, 0, 0, 0)` | 1px | transparent | 0% | 4.8px | Warning alerts |
| `0.5px solid rgba(31, 30, 29, 0.4)` | 0.5px | #1F1E1D | 40% | 12px | External widgets |

---

## NOTES

1. **Primary border color** (`#BDC5D1`) is used most frequently with varying opacities
2. **Blue borders** (`#377DFF`) indicate interactive/active states
3. **2px borders** are reserved for emphasis (active selections, some form fields)
4. **Border radius of 4px** is the default for most interactive elements
5. **Tables use right-side borders** on cells rather than full borders
6. **Transparent borders** maintain layout spacing while relying on background colors for visual definition