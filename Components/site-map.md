# Site Map: locations.linda.co

## Root
├── / (redirects to /locations)
├── /dashboard

## Main Navigation
├── /locations
├── /reviews_dashboard
├── /scheduled_geogrids_index
├── /live_geogrids_index
├── /reports
├── /gallery
├── /google_accounts
└── /facebook_accounts

## User Menu (Upper Right Dropdown)
├── /google_accounts
└── /facebook_accounts

## Locations (155+ location pages)
├── /locations
│   ├── /locations/{location_id}                    # Location Dashboard
│   ├── /locations/{location_id}/automation         # Automation Dashboard
│   ├── /locations/{location_id}/change_log         # Change Log
│   └── /locations/{location_id}/keywords           # Keyword Tracking
│
│   # Individual location IDs (155 total, examples):
│   ├── /locations/5j66x7jl
│   ├── /locations/lvjj3vml
│   ├── /locations/59yykpez
│   └── ... (152 more)

## GMB (Google My Business) Location Pages
├── /gmb/locations/{gmb_id}/edit                    # Edit Location Data
├── /gmb/locations/{gmb_id}/media/identity          # Media - Identity
├── /gmb/locations/{gmb_id}/media/additional        # Media - Additional
├── /gmb/locations/{gmb_id}/media/customers         # Media - Customers
├── /gmb/locations/{gmb_id}/media/new               # Add Media
├── /gmb/locations/{gmb_id}/media/{media_id}/edit   # Edit Media Item
├── /gmb/locations/{gmb_id}/local_posts             # Posts List
├── /gmb/locations/{gmb_id}/local_posts/new         # New Post
├── /gmb/locations/{gmb_id}/local_posts/{post_id}/edit  # Edit Post
├── /gmb/locations/{gmb_id}/reviews                 # Reviews
├── /gmb/locations/{gmb_id}/questions               # Q&A
└── /gmb/locations/{gmb_id}/notification_settings/edit  # Notifications

## Reports
├── /reports
├── /audit_reports
├── /audit_report_configurations
│   ├── /audit_report_configurations/new
│   ├── /audit_report_configurations/{config_id}/edit
│   └── /audit_report_configurations/{config_id}/reports/{report_id}

## GeoGrid Search
├── /scheduled_geogrids_index
│   ├── /scheduled_geogrids/{config_id}/public_links
│   └── /scheduled_geogrids_show?config_id={config_id}
├── /live_geogrids_index
├── /geogrids/{geogrid_id}
└── /geogrids/{geogrid_id}/csv_export

## Check Ins (gb/)
├── /gb/moments
├── /gb/about
├── /gb/businesses
│   └── /gb/businesses/new
└── /gb/widgets
    └── /gb/widgets/new

## Call Tracking
├── /call_tracking/incoming_calls
├── /call_tracking/phone_numbers
│   └── /call_tracking/phone_numbers/new
├── /call_tracking/telephony_accounts
│   └── /call_tracking/telephony_accounts/new
├── /call_tracking/abouts
└── /call_tracking/blocklist/edit

## Google Accounts
├── /google_accounts
│   ├── /google_accounts/new
│   ├── /google_accounts/{account_id}/
│   ├── /google_accounts/{account_id}/edit
│   └── /google_accounts/{account_id}/sync

## Facebook Accounts
└── /facebook_accounts

## API & RSS Endpoints
├── /api/organizations_locations/enable?oids=all
├── /api/organizations_locations/disable?oids=all
├── /api/gmb/locations/{gmb_id}/media/{media_id}
├── /sy/google_accounts/{account_id}/local_posts.rss
└── /sy/locations/{gmb_id}/local_posts.rss