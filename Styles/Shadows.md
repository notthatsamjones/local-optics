
# Current State
## Usage

1. Navbar shadow is universal - appears on every page
2. `.shadow-sm` Bootstrap class is used for subtle elevation on cards and buttons
3. Blue glow shadows indicate interactive/selected states
4. Inset shadows are used for status indicators (left border effect)
5. Dropdown shadows are the most prominent (24px blur) for clear floating effect
6. Most content cards do NOT have shadows - they use borders instead

## SHADOW USAGE BY PAGE

| URL                                              | Elements with Shadows                                                                     |
| ------------------------------------------------ | ----------------------------------------------------------------------------------------- |
| **All Pages**                                    | Navbar                                                                                    |
| `/locations`                                     | Table row status indicators (suspended), Dropdown menus                                   |
| `/gmb/locations/{id}/local_posts`                | Main card (`.shadow-sm`)                                                                  |
| `/gmb/locations/{id}/local_posts/new`            | Info alert, Card container, Post type cards (active), CTA options (active), Submit button |
| `/gmb/locations/{id}/reviews`                    | Panel container                                                                           |
| `/call_tracking/incoming_calls`                  | Chart container                                                                           |
| `/google_accounts`                               | Card container                                                                            |
| `/reports`                                       | Panel container                                                                           |
| `/gallery`                                       | Export widget, Scheduled widget                                                           |
| `/audit_report_configurations/{id}/reports/{id}` | Type rating items                                                                         |


---

## CSS VARIABLES / COMMON VALUES
```css
/* Shadow Tokens */
--shadow-navbar: rgba(0, 0, 0, 0.08) 0px 2px 4px 0px;
--shadow-sm: rgba(34, 34, 34, 0.075) 0px 2px 4px 0px;
--shadow-panel: rgba(0, 0, 0, 0.05) 0px 1px 0px 0px;
--shadow-widget: rgba(189, 197, 209, 0.24) 0px 2px 6px 0px;
--shadow-dropdown: rgba(189, 197, 209, 0.48) 0px 8px 24px 0px;
--shadow-chart: rgba(0, 0, 0, 0.1) 0px 1px 3px 0px;
--shadow-active-blue: rgba(55, 125, 255, 0.3) 0px 6px 20px 0px;
--shadow-active-blue-sm: rgba(55, 125, 255, 0.2) 0px 2px 12px 0px;
--shadow-border: rgb(213, 218, 226) 0px 0px 0px 1px;
--shadow-status-orange: rgb(249, 174, 52) 4px 0px 0px 0px inset;
```



---

## Reference

### 1. Navbar Shadow (Global)
**Applied to:** Top navigation bar on all pages
```css
.navbar {
  box-shadow: rgba(0, 0, 0, 0.08) 0px 2px 4px 0px;
}
```
- **Color:** Black at 8% opacity
- **Offset:** 0px horizontal, 2px vertical
- **Blur:** 4px
- **Spread:** 0px
- **Usage:** Creates subtle elevation for sticky header

---

### 2. Standard Card Shadow (`.shadow-sm`)
**Applied to:** Cards, alerts, buttons with `.shadow-sm` class
```css
.shadow-sm {
  box-shadow: rgba(34, 34, 34, 0.075) 0px 2px 4px 0px;
}
```
- **Color:** Dark gray (#222222) at 7.5% opacity
- **Offset:** 0px horizontal, 2px vertical
- **Blur:** 4px
- **Spread:** 0px

**Used on:**
| `/gmb/locations/{id}/local_posts` | Main card container |
| `/gmb/locations/{id}/local_posts/new` | Info alert, card container, submit button |

---

### 3. Panel/Card Bottom Shadow
**Applied to:** Panel containers, Google Accounts card
```css
.panel, .card {
  box-shadow: rgba(0, 0, 0, 0.05) 0px 1px 0px 0px;
}
```
- **Color:** Black at 5% opacity
- **Offset:** 0px horizontal, 1px vertical
- **Blur:** 0px
- **Spread:** 0px
- **Effect:** Very subtle bottom line shadow

**Used on:**
| `/reports` | Panel container |
| `/gmb/locations/{id}/reviews` | Panel container |
| `/google_accounts` | Card container |

---

### 4. Gallery Widget Shadow
**Applied to:** Gallery sidebar widgets
```css
.gallery-widget {
  box-shadow: rgba(189, 197, 209, 0.24) 0px 2px 6px 0px;
}
```
- **Color:** Gray-blue (#BDC5D1) at 24% opacity
- **Offset:** 0px horizontal, 2px vertical
- **Blur:** 6px
- **Spread:** 0px

**Used on:**
/gallery` | Export widget, Scheduled widget |

---

### 5. Dropdown Shadow
**Applied to:** Open dropdown/select menus
```css
.multiselect__content-wrapper {
  box-shadow: rgba(189, 197, 209, 0.48) 0px 8px 24px 0px;
}
```
- **Color:** Gray-blue (#BDC5D1) at 48% opacity
- **Offset:** 0px horizontal, 8px vertical
- **Blur:** 24px
- **Spread:** 0px
- **Effect:** Prominent floating shadow for dropdowns

**Used on:**
All pages | Multiselect/dropdown menus when open |

---

### 6. Chart Container Shadow
**Applied to:** Chart/graph containers
```css
.incoming-calls-chart {
  box-shadow: rgba(0, 0, 0, 0.1) 0px 1px 3px 0px;
}
```
- **Color:** Black at 10% opacity
- **Offset:** 0px horizontal, 1px vertical
- **Blur:** 3px
- **Spread:** 0px

**Used on:**
`/call_tracking/incoming_calls` | Chart container |

---

### 7. Active Selection Shadow (Blue Glow)
**Applied to:** Selected/active interactive cards
```css
/* Post type card (active) */
.post-type-card.active {
  box-shadow: rgba(55, 125, 255, 0.3) 0px 6px 20px 0px;
}

/* CTA option (active) */
.cta-option.active {
  box-shadow: rgba(55, 125, 255, 0.2) 0px 2px 12px 0px;
}
```
- **Color:** Primary blue (#377DFF) at 20-30% opacity
- **Effect:** Blue glow indicating selection state

**Used on:**
/gmb/locations/{id}/local_posts/new` | Post type selector cards, CTA option buttons |

---

### 8. Audit Report Item Shadow (Border-like)
**Applied to:** Rating/comparison items in audit reports
```css
.type-rating-item {
  box-shadow: rgb(213, 218, 226) 0px 0px 0px 1px;
}
```
- **Color:** Gray (#D5DAE2) solid
- **Effect:** 1px border simulation using box-shadow
- **Offset:** None (all sides)

**Used on:**
`/audit_report_configurations/{id}/reports/{id}` | Type rating item cards |

---

### 9. Table Row Status Indicator (Inset)
**Applied to:** Table cells for suspended/flagged locations
```css
td.suspended {
  box-shadow: rgb(249, 174, 52) 4px 0px 0px 0px inset;
}
```
- **Color:** Orange (#F9AE34)
- **Effect:** 4px left border indicator (inset)
- **Usage:** Visual status indicator for suspended locations

**Used on:**
`/locations` | Table rows with suspended status |

---
