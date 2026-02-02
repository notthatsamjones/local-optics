# WCAG 2.0 AA Color Contrast Analysis


## Critical Failures (Ratio < 3:1)

| Issue | Ratio | Pages | Solution |
|-------|-------|-------|----------|
| Star gold on white | 1.35 | Reviews | Add stroke or use on dark background |
| Warning orange on white | 1.89 | All 3 pages | Use dark text instead of white |
| White text on warning bg | 1.89 | All 3 pages | Use `slate.900` text |
| Yellow/orange heat map on white | 1.07-1.97 | GeoGrid | Add dark stroke to numbers |

---

## Major Failures (3:1 - 4.5:1)

| Issue | Ratio | Pages | Solution |
|-------|-------|-------|----------|
| Blue 500 on white | ~4.5 | All 3 pages | Acceptable for large text/buttons; use 600+ for small text |
| Success green on white | 3.19 | All 3 pages | Add border or use dark text on light green bg |
| Slate 300/400 on white | 2.2-3.3 | Locations | Use only for borders/disabled; use 500+ for text |

---

## Page-Specific Remediation

### PAGE 1: Locations List (`/locations`)

| Element | Current Issue | Solution Using Existing Tokens |
|---------|---------------|-------------------------------|
| Location name links | Blue 500 borderline | Use `blue.600` for hover emphasis |
| Table dividers | Slate 300 low contrast | Acceptable for decorative borders |
| Form labels | Slate 400 fails for text | Use `slate.500` or `slate.800` |
| Filter labels | Slate 400 on slate-25 | Use `slate.500` minimum |
| Secondary buttons | Slate 400 text | Use `slate.500` for text, keep 400 for borders |

---

### PAGE 2: Location Detail (`/locations/[id]`)

| Element | Current Issue | Solution Using Existing Tokens |
|---------|---------------|-------------------------------|
| Warning banner | White on warning (1.89) | Use `slate.900` text on warning background |
| "Published" badge | Success green fails | Use `slate.900` text on `green.100` background |
| "Verified" badge | Blue 500 borderline | Use white text on `blue.500` background (passes) |
| Links & buttons | Blue 500 borderline | Acceptable; ensure adequate size |

---

### PAGE 3: GeoGrid Tracker (`/scheduled_geogrids_show`)

| Element | Current Issue | Solution Using Existing Tokens |
|---------|---------------|-------------------------------|
| Yellow heat map numbers | 1.07 ratio | Add 1px `slate.800` stroke to text |
| Orange heat map numbers | 1.97 ratio | Add 1px `slate.800` stroke to text |
| Red heat map numbers | 3.84 ratio | Add 1px `slate.900` stroke for safety |
| Tab navigation | Blue on light bg | Use `blue.600` or `blue.700` for active |

---

## Implementation Patterns

### Pattern 1: Alert Banners

**Problem:** White text on `semantic.warning` fails (1.89:1)

**Solution:** Invert the text color

```css
/* Instead of */
.alert-warning {
  background: var(--semantic-warning);
  color: var(--white);  /* FAILS */
}

/* Use */
.alert-warning {
  background: var(--semantic-warning);
  color: var(--slate-900);  /* PASSES 8.5:1 */
}
```

---

### Pattern 2: Status Badges

**Problem:** White text on success/warning backgrounds fails

**Solution:** Use light backgrounds with dark text

| Badge Type | Background | Text | Contrast |
|------------|------------|------|----------|
| Published | `green.100` | `slate.900` | 12:1+ |
| Verified | `blue.500` | `white` | ~4.5:1 (large text OK) |
| Pending | `yellow.100` | `slate.900` | 14:1+ |
| Error | `red.500` | `white` | 5.0:1 |

---

### Pattern 3: Heat Map Numbers

**Problem:** Light colors (yellow, orange) invisible on white

**Solution:** Add text stroke using existing dark tokens

```css
.heat-map-number {
  -webkit-text-stroke: 1px var(--slate-800);
  paint-order: stroke fill;
}

/* Or use text-shadow */
.heat-map-number {
  text-shadow:
    1px 1px 0 var(--slate-800),
    -1px -1px 0 var(--slate-800),
    1px -1px 0 var(--slate-800),
    -1px 1px 0 var(--slate-800);
}
```

---

### Pattern 4: Star Ratings

**Problem:** Gold stars invisible on white (1.35:1)

**Solution:** Add outline stroke

```css
.star-icon {
  fill: #FFDC42; /* Keep gold fill */
  stroke: var(--slate-400);
  stroke-width: 1px;
}
```

---

### Pattern 5: Secondary Text

**Problem:** `slate.300` and `slate.400` fail for readable text

**Solution:** Token usage guidelines

| Token | Contrast on White | Allowed Uses |
|-------|-------------------|--------------|
| `slate.300` | 2.38:1 | Borders, dividers only |
| `slate.400` | 3.33:1 | Disabled states, placeholders, icons |
| `slate.500` | 4.54:1 | Secondary text, labels |
| `slate.800` | 9.5:1+ | Body text |
| `slate.900` | 15:1+ | Headings, primary text |

---

### Pattern 6: Links & Interactive Elements

**Problem:** `blue.500` is borderline (~4.5:1)

**Solution:** Ensure minimum size requirements

| Element | Minimum Size | Token | Notes |
|---------|--------------|-------|-------|
| Body links | 16px+ | `blue.500` | Passes at large text threshold |
| Small links | 12px | `blue.600` | Use darker variant |
| Button text | 16px+ | `blue.500` | Acceptable with white bg |
| Navigation | 14px+ | `blue.500` | Underline helps recognition |

---

## Token Usage Reference

### Safe for Text on White

| Token | Hex | Contrast | Use For |
|-------|-----|----------|---------|
| `slate.500` | #767676 | 4.54:1 | Secondary text, form labels |
| `slate.600` | #6B6B6B | 5.4:1 | Emphasized secondary |
| `slate.700` | #555555 | 7.5:1 | Important secondary |
| `slate.800` | #3D454D | 9.5:1 | Body text |
| `slate.900` | #222222 | 15:1 | Headings |
| `blue.500` | #2c70d3 | ~4.5:1 | Large text/buttons only |
| `blue.600` | #265fb6 | ~5.5:1 | Small links |
| `blue.700` | #204f97 | ~7.5:1 | High contrast links |

### Decorative Only (Not for Text)

| Token | Hex | Contrast | Allowed Uses |
|-------|-----|----------|--------------|
| `slate.200` | #BDBFC5 | 1.8:1 | Borders, dividers |
| `slate.300` | #9CA9BD | 2.38:1 | Subtle borders |
| `slate.400` | #7D8FA0 | 3.33:1 | Disabled states, placeholders |

---

## Summary by Page

| Page | Critical Fixes | Implementation |
|------|----------------|----------------|
| Locations List | Form labels, secondary text | Swap slate.400 -> slate.500 for text |
| Location Detail | Warning banner text | Swap white -> slate.900 on warning bg |
| GeoGrid Tracker | Heat map numbers | Add text stroke with slate.800 |
| All Pages | Status badges | Use light bg + dark text pattern |

---

## Checklist

- [ ] Warning banners use `slate.900` text (not white)
- [ ] Form labels use `slate.500` minimum
- [ ] Secondary text uses `slate.500` minimum
- [ ] Status badges use light background + dark text pattern
- [ ] Heat map numbers have dark stroke/shadow
- [ ] Star ratings have visible outline
- [ ] Small links (<16px) use `blue.600` or darker
