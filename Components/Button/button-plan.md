
# Current State

Document current button styling inconsistencies across pages

| Button Type                | Pages                                                                                                                                         | Height | Padding      | Font Size | Font Weight | Border Radius |
| -------------------------- | --------------------------------------------------------------------------------------------------------------------------------------------- | ------ | ------------ | --------- | ----------- | ------------- |
| Primary (Large)            | /locations, /google_accounts, /gmb/locations/{id}/local_posts, /gmb/locations/{id}/media/identity, /scheduled_geogrids_index, /locations/{id} | 48px   | 0px 12px     | 16px      | 600         | 4px           |
| Secondary (Large, Outline) | /google_accounts, /scheduled_geogrids_index                                                                                                   | 48px   | 0px 12px     | 16px      | 600         | 4px           |
| Ghost (Large)              | /scheduled_geogrids_index                                                                                                                     | 48px   | 0px          | 16px      | 600         | 4px           |
| Secondary (Small, Outline) | /google_accounts ("Sync")                                                                                                                     | 40px   | 0px 12px     | 16px      | 600         | 4px           |
| Secondary (Small, Outline) | /gmb/locations/{id}/local_posts, /gmb/locations/{id}/media/identity                                                                           | 40px   | 0px 16px     | 16px      | 600         | **2px**       |
| Extra Small (Outline)      | /locations/{id}                                                                                                                               | 32px   | **0px 16px** | 12px      | 600         | 4px           |
| Context Menu               | /locations, /locations/{id}, /gmb/locations/{id}/local_posts, /gmb/locations/{id}/media/identity, /scheduled_geogrids_index                   | 25px   | 0px          | 16px      | **400**     | 4px           |

# Proposed State

### Primary Button

| Property | Token |
|----------|-------|
| Font-size | `font.interactive.button.fontSize` (16px) |
| Font-weight | `font.interactive.button.fontWeight` (600) |
| Line-height | `font.interactive.button.lineHeight` (24px) |
| Padding | `button.primary.padding` (12px 24px) |
| Border-radius | `button.primary.borderRadius` → `border-radius.md` (8px) |
| Background | `button.primary.background` → `blue.500` (#2c70d3) |
| Background (hover) | `button.primary.backgroundHover` → `blue.600` (#265fb6) |
| Text color | `button.primary.text` → `foundations.white` (#FFFFFF) |

### Secondary Button

| Property | Token |
|----------|-------|
| Background | `button.secondary.background` → `slate.25` (#F4F6F9) |
| Background (hover) | `button.secondary.backgroundHover` → `slate.100` (#D4DDE6) |
| Text color | `button.secondary.text` → `slate.900` (#222222) |
| Border | `button.secondary.border` → `slate.200` (#BDBFC5) |

### Outline Button

| Property | Token |
|----------|-------|
| Background | `button.outline.background` (transparent) |
| Text color | `button.outline.text` → `slate.500` (#767676) |
| Border | `button.outline.border` → `slate.300` (#9CA9BD) |
| Border (hover) | `button.outline.borderHover` → `slate.400` (#7D8FA0) |

### Interaction States

| Property | Token |
|----------|-------|
| Disabled opacity | `interaction.disabled.opacity` (0.5) |
| Disabled cursor | `interaction.disabled.cursor` (not-allowed) |
| Focus outline | `interaction.focus.outline` (2px solid #2c70d3) |
| Focus outline offset | `interaction.focus.outlineOffset` (2px) |

## Migration Checklist

| Page | Route | CSS to Remove |
|------|-------|---------------|
|      |       |               |

### QA Steps
1. Verify primary button background is #2c70d3, hover #265fb6
2. Confirm font is 16px/600 weight
3. Check border-radius is 8px
4. Test focus and disabled states




# locations.linda.co

---

## Primary Button (Large)

| Property | Token | Value |
|----------|-------|-------|
| Font-size | font.button.fontSize | 16px |
| Font-weight | font.button.fontWeight | 600 |
| Line-height | font.button.lineHeight | 16px |
| Padding | button.primary.padding | 0px 12px |
| Border-radius | button.primary.borderRadius | 4px |
| Background | button.primary.background → blue.500 | rgb(55, 125, 255) / #377DFF |
| Border | button.primary.border | 1px solid rgb(55, 125, 255) |
| Text color | button.primary.text | rgb(255, 255, 255) / #FFFFFF |
| Height | button.primary.height | 48px |

**Appears on:**
- `/locations` — "Add new location"
- `/google_accounts` — "Add Account"
- `/gmb/locations/{id}/local_posts` — "Create New Post"
- `/gmb/locations/{id}/media/identity` — "Add Media"
- `/scheduled_geogrids_index` — "Create config", "Save changes"
- `/locations/{id}` — "Proceed to Call Tracking"

---

## Primary Button (Active/Hover State)

| Property | Token | Value |
|----------|-------|-------|
| Background | button.primary.backgroundActive → blue.600 | rgb(50, 115, 235) / #3273EB |
| Border | button.primary.borderActive | 1px solid rgb(50, 115, 235) |

**Appears on:**
- `/google_accounts` — "Add Account" (active state)

---

## Secondary Button (Outline)

| Property | Token | Value |
|----------|-------|-------|
| Font-size | font.button.fontSize | 16px |
| Font-weight | font.button.fontWeight | 600 |
| Line-height | font.button.lineHeight | 16px |
| Padding | button.secondary.padding | 0px 12px |
| Border-radius | button.secondary.borderRadius | 4px |
| Background | button.secondary.background | rgb(255, 255, 255) / #FFFFFF |
| Border | button.secondary.border → blue.500 | 1px solid rgb(55, 125, 255) |
| Text color | button.secondary.text → blue.500 | rgb(55, 125, 255) / #377DFF |
| Height | button.secondary.height | 48px |

**Appears on:**
- `/google_accounts` — "Enable All Locations"
- `/google_accounts` — "Sync" (height: 40px)
- `/scheduled_geogrids_index` — "New config", "Configs", "Config's geogrids", "Edit config"

---

## Secondary Button (Active State)

| Property | Token | Value |
|----------|-------|-------|
| Background | button.secondary.backgroundActive → blue.50 | rgb(244, 247, 252) / #F4F7FC |
| Border | button.secondary.borderActive | 1px solid rgb(55, 125, 255) |
| Text color | button.secondary.textActive → blue.500 | rgb(55, 125, 255) / #377DFF |

**Appears on:**
- `/scheduled_geogrids_index` — "Configs" (active tab)
- `/locations/{id}` — "Month" (active date range)

---

## Small Button (Outline)

| Property | Token | Value |
|----------|-------|-------|
| Font-size | font.button.sm.fontSize | 16px |
| Font-weight | font.button.fontWeight | 600 |
| Line-height | font.button.sm.lineHeight | 16px |
| Padding | button.sm.padding | 0px 16px |
| Border-radius | button.sm.borderRadius | 2px |
| Background | button.sm.background | rgb(255, 255, 255) / #FFFFFF |
| Border | button.sm.border → blue.500 | 1px solid rgb(55, 125, 255) |
| Text color | button.sm.text → blue.500 | rgb(55, 125, 255) / #377DFF |
| Height | button.sm.height | 40px |

**Appears on:**
- `/gmb/locations/{id}/local_posts` — "Edit" (on each post)
- `/gmb/locations/{id}/media/identity` — "G" (Google link), Delete button

---

## Extra Small Button (Outline)

| Property | Token | Value |
|----------|-------|-------|
| Font-size | font.button.xs.fontSize | 12px |
| Font-weight | font.button.fontWeight | 600 |
| Line-height | font.button.xs.lineHeight | 12px |
| Padding | button.xs.padding | 0px 16px |
| Border-radius | button.xs.borderRadius | 4px |
| Background | button.xs.background | rgb(255, 255, 255) / #FFFFFF |
| Border | button.xs.border → blue.500 | 1px solid rgb(55, 125, 255) |
| Text color | button.xs.text → blue.500 | rgb(55, 125, 255) / #377DFF |
| Height | button.xs.height | 32px |

**Appears on:**
- `/locations/{id}` — "Archive"

---

## Ghost Button (Text Only)

| Property | Token | Value |
|----------|-------|-------|
| Font-size | font.button.fontSize | 16px |
| Font-weight | font.button.fontWeight | 600 |
| Line-height | font.button.lineHeight | 16px |
| Padding | button.ghost.padding | 0px |
| Border-radius | button.ghost.borderRadius | 4px |
| Background | button.ghost.background | transparent |
| Border | button.ghost.border | none |
| Text color | button.ghost.text → blue.500 | rgb(55, 125, 255) / #377DFF |
| Height | button.ghost.height | 48px |

**Appears on:**
- `/scheduled_geogrids_index` — "Back to Geogrid"

---

## Ghost Button (Muted)

| Property | Token | Value |
|----------|-------|-------|
| Font-size | font.button.fontSize | 16px |
| Font-weight | font.button.fontWeight | 600 |
| Line-height | font.button.lineHeight | 16px |
| Padding | button.ghostMuted.padding | 0px |
| Border-radius | button.ghostMuted.borderRadius | 4px |
| Background | button.ghostMuted.background | rgb(255, 255, 255) / #FFFFFF |
| Border | button.ghostMuted.border | none |
| Text color | button.ghostMuted.text → gray.500 | rgb(119, 131, 143) / #77838F |
| Height | button.ghostMuted.height | 48px |

**Appears on:**
- `/scheduled_geogrids_index` — "Clear filters"

---

## Icon Button (Small Secondary)

| Property | Token | Value |
|----------|-------|-------|
| Font-size | font.button.sm.fontSize | 14px |
| Font-weight | font.button.fontWeight | 600 |
| Line-height | font.button.sm.lineHeight | 14px |
| Padding | button.iconSm.padding | 4px 8px |
| Border-radius | button.iconSm.borderRadius | 2px |
| Background | button.iconSm.background | rgb(255, 255, 255) / #FFFFFF |
| Border | button.iconSm.border | none |
| Text color | button.iconSm.text → gray.500 | rgb(119, 131, 143) / #77838F |
| Height | button.iconSm.height | 36px |

**Appears on:**
- `/scheduled_geogrids_index` — "Repeat", "Run", "Open PNG", "CSV", "GIF"

---

## Context Menu Button (Ellipsis/More)

| Property | Token | Value |
|----------|-------|-------|
| Font-size | font.button.context.fontSize | 16px |
| Font-weight | font.button.context.fontWeight | 400 |
| Line-height | font.button.context.lineHeight | 24.608px |
| Padding | button.context.padding | 0px |
| Border-radius | button.context.borderRadius | 4px |
| Background | button.context.background | rgb(255, 255, 255) / #FFFFFF |
| Border | button.context.border → gray.200 | 1px solid rgba(189, 197, 209, 0.48) |
| Text color | button.context.text → gray.500 | rgb(119, 131, 143) / #77838F |
| Height | button.context.height | 25px |
| Min-height | button.context.minHeight | auto |

**Appears on:**
- `/locations` — Row action menu (⋯)
- `/locations/{id}` — Status dropdown (⋯)
- `/gmb/locations/{id}/local_posts` — Context menus
- `/gmb/locations/{id}/media/identity` — Context menus
- `/scheduled_geogrids_index` — Row context menus

---

## Dropdown Menu Item

| Property | Token | Value |
|----------|-------|-------|
| Font-size | font.dropdown.fontSize | 18px |
| Font-weight | font.dropdown.fontWeight | 400 |
| Line-height | font.dropdown.lineHeight | 22.5px |
| Padding | dropdown.item.padding | 6px 16px |
|


___

# Dropdown Height Analysis for locations.linda.co

## Summary

**No dropdowns are smaller than 48px in height.** All dropdown/select components meet or exceed the 48px minimum height.

---

## Dropdown Heights Found

| Component Type | Height | Min-Height | Pages Found |
|----------------|--------|------------|-------------|
| `.multiselect` | **48px** | 40px | All filter pages |
| `.select2-selection` | **52px** | 0px | Posts page |
| `select.form-control` | **52px** | 0px | Google Accounts |
| `.dropdown.user-menu` | **54px** | auto | All pages (navbar) |

---

## Detailed Findings by Page

### `/locations`
- Multiselect dropdowns (States, Tags, Folders, Accounts): **48px**

### `/reviews_dashboard`
- Multiselect dropdowns (Search, Location, Rating, Response): **48px**

### `/scheduled_geogrids_index` & `/live_geogrids_index`
- Multiselect dropdowns (Business details, Categories, Tags, Grid size, etc.): **48px**

### `/audit_reports`
- Multiselect dropdowns (Audit configuration, Location): **48px**

### `/call_tracking/incoming_calls`
- Multiselect dropdowns (Location, Statuses): **48px**

### `/call_tracking/phone_numbers/new`
- Multiselect dropdowns (Telephony Account, Country): **48px**

### `/gmb/locations/{id}/local_posts`
- Select2 dropdowns (Sort by, Status): **52px**

### `/google_accounts`
- Native select (rows per page): **52px**

### Navbar (All Pages)
- User menu dropdown: **54px**

---

## CSS Specifications
```css
/* Multiselect Component */
.multiselect {
  height: 48px;
  min-height: 40px;
}

.multiselect__tags {
  min-height: 46px;
  padding: 10px 40px 0px 16px;
}

/* Select2 Component */
.select2-selection--single {
  height: 52px;
}

/* Native Select (Google Accounts) */
select.form-control {
  height: 52px;
}

/* Navbar Dropdown */
.dropdown.user-menu {
  height: 54px;
  padding: 9px;
}
```

---

## Conclusion

✅ **All dropdowns are 48px or taller**

The minimum dropdown height in the application is **48px** (multiselect components), which meets standard touch target accessibility guidelines. Some dropdowns (select2, native selects) are slightly taller at **52px**.