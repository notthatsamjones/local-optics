# Page Header Standardization Plan

Significant header styling inconsistency across ten major pages in terms of height, margins, and font size/weight.

---

## Current State

### Plain Header

| Page               | Height | Font Size | Font Weight | Line Height | Margin Bottom | Text Color RGB  |
| ------------------ | ------ | --------- | ----------- | ----------- | ------------- | --------------- |
| Reviews            | 30.8px | 28px      | 600         | 30.8px      | 16px          | rgb(50, 50, 50) |
| Reports            | 35.2px | 32px      | 600         | 35.2px      | 0px           | rgb(61, 69, 77) |
| Moments            | 30.8px | 28px      | 600         | 30.8px      | 0px           | rgb(50, 50, 50) |
| Telephony Accounts | 30.8px | 28px      | 600         | 30.8px      | 0px           | rgb(50, 50, 50) |

### Header with Button

| Page               | Height | Font Size | Font Weight | Line Height | Margin Bottom | Text Color RGB  |
| ------------------ | ------ | --------- | ----------- | ----------- | ------------- | --------------- |
| Incoming Calls     | 40px   | 32px      | 600         | 40px        | 12.3px        | rgb(61, 69, 77) |
| Keywords           | 30.8px | 28px      | 600         | 30.8px      | 12.3px        | rgb(34, 34, 34) |
| Phone Numbers      | 30.8px | 28px      | 600         | 30.8px      | 0px           | rgb(50, 50, 50) |
| Blocklist          | 24px   | 32px      | 700         | 24px        | 12.3px        | rgb(61, 69, 77) |

### Custom Header

| Page               | Height | Font Size | Font Weight | Line Height | Margin Bottom | Text Color RGB  |
| ------------------ | ------ | --------- | ----------- | ----------- | ------------- | --------------- |
| Live Geogrids      | 44px   | 40px      | 500         | 44px        | 12.3px        | rgb(50, 50, 50) |
| Automation         | 36.4px | 28px      | 600         | 36.4px      | 0px           | rgb(0, 0, 0)    |

## Proposed State

| Property | Token Path | Value |
|----------|-----------|-------|
| Font-size | `font.headings.h1.fontSize` | 28px |
| Font-weight | `font.headings.h1.fontWeight` | 600 (semibold) |
| Color | `text.default.heading` → `slate.900` | #222222 |
| Text case | - | Title Case |
| Margin-bottom | - | 0px |

## Migration Checklist

### Plain Header

| Page               | Route                             | CSS to Remove                              |
| ------------------ | --------------------------------- | ------------------------------------------ |
| Reviews            | /reviews_dashboard                | `.h3.mb-3.font-weight-semi-bold.text-dark` |
| Reports            | /reports                          | `.h2.m-0.font-weight-semi-bold.color-dark` |
| Moments            | /gb/moments                       | `.h3.font-weight-semi-bold.text-dark.m-0`  |
| Telephony Accounts | /call_tracking/telephony_accounts | `.h3.font-weight-semi-bold.text-dark.m-0`  |

### Header with Button

| Page               | Route                             | CSS to Remove                              |
| ------------------ | --------------------------------- | ------------------------------------------ |
| Incoming Calls     | /call_tracking/incoming_calls     | `.incoming-calls__title`                   |
| Keywords           | /locations/:id/keywords           | `.page-title`                              |
| Phone Numbers      | /call_tracking/phone_numbers      | `.h3.font-weight-semi-bold.text-dark.m-0`  |
| Blocklist          | /call_tracking/blocklist/edit     | `.blocklist__title`                        |

### Custom Header

| Page               | Route                             | CSS to Remove                              |
| ------------------ | --------------------------------- | ------------------------------------------ |
| Live Geogrids      | /live_geogrids_index              | `.text-dark`                               |
| Automation         | /locations/:id/automation         | (none)                                     |

### QA Steps
1. Confirm font size is 28px, weight 600 (semibold)
2. Check text color matches #222222 (slate.900)
3. Ensure no margin-bottom spacing
4. Verify page title uses Title Case
