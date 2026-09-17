# B&L Neeley Service Platform v1

This is the first mobile-first starter build for the separate TEST Supabase project.

## Included
- Responsive single-codebase design for phone, tablet, and desktop
- Customers -> Facilities -> Equipment structure
- Permanent, rental, and temporary equipment
- Add Equipment from Facility Setup
- Add Equipment while writing a service report
- Dynamic report forms based on facility equipment
- Boiler, water, and cooling-tower target logic
- Live Program Snapshot
- Save Draft demo behavior
- Complete + Generate PDF demo behavior
- GitHub Pages-friendly plain HTML/CSS/JS
- Supabase connection scaffold
- Existing service-platform SQL migration included under /supabase

## First test
Open `index.html` with `DEMO_MODE: true` in `config.js`.

## Connect the TEST Supabase project
1. Run `supabase/service_platform_v1.sql` in Supabase SQL Editor.
2. Create your Auth user.
3. Insert that user into `service_user_roles` as admin.
4. Update `config.js`:

```js
window.BLN_CONFIG = {
  SUPABASE_URL: "https://YOURPROJECT.supabase.co",
  SUPABASE_ANON_KEY: "YOUR_ANON_KEY",
  DEMO_MODE: false
};
```

## Important
This is v1 of the real app scaffold, not the final app. The next pass should finish:
- login screen/auth UI
- add customer/facility admin forms
- fully persisted report save/update flow
- revisions/audit history
- PDF upload/reopen/download
- targets read entirely from Supabase instead of JS defaults
- trend charts
- final B&L Neeley letterhead PDF styling


## v2 PDF / Boiler Update
- Fixed dynamic report readings not appearing in generated PDFs.
- Boiler Alkalinity is automatically calculated as Raw Conductivity minus Neutralized Conductivity.
- The report labels the calculated result simply as **Alkalinity**.
- OH Alkalinity remains a separate optional reading.
- Completed PDFs now include populated system tables, targets/statuses, notes, Program Snapshot, Summary & Recommendations, and page footers.
- Empty reports are blocked from completion.


## v2.2 PDF Polish
- Improved system-level page breaks so equipment sections stay together when practical.
- Repeats table headings on continuation pages.
- Uses PDF-safe target notation (`>=`) to prevent the greater-than-or-equal glyph from corrupting in jsPDF core fonts.
- Shortened footer to preserve clear separation from page numbering.
