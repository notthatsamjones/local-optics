# Top Navigation Padding

## Visual Spacing

| Side | Spacing | Source |
|------|---------|--------|
| **Left** | **8px** | `.navbar-brand` margin-left |
| **Right** | **16px** | `.user-menu` margin-right |

---

## Details

The navbar itself has **0px padding**. The left/right spacing is created by margins on the first and last child elements:

### Left Side
```css
.navbar-brand {
  margin-left: 8px;
  padding-left: 11px;
  padding-right: 11px;
}
```
- Visual edge spacing: **8px** (from margin)

### Right Side
```css
.dropdown.user-menu {
  margin-right: 16px;
  padding-left: 9px;
  padding-right: 9px;
}
```
- Visual edge spacing: **16px** (from margin)

---

## Note

The left and right spacing are **asymmetrical**:
- Left: 8px
- Right: 16px