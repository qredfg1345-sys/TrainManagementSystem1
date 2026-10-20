# Train Management — Independent Copy

## Before publishing

1. Open `config.js`. Replace `PASTE_YOUR_SUPABASE_PUBLISHABLE_KEY_HERE` with the **full** `sb_publishable_...` value from Supabase → Project Settings → API Keys. The project URL is already set to your new project. **Never use a secret/service_role key.**
2. Upload **all files from this folder** to the root of your GitHub repository (keep the names exactly, including `Schedule.html`). Do not upload any `(1)` suffixes.
3. In Supabase Authentication → URL Configuration, set **Site URL** to your published GitHub Pages URL and add the exact URL as an allowed **Redirect URL** (also allow the corresponding `/index.html` callback). This is required for email confirmation links.
4. In Supabase Authentication, leave Email and Signups enabled. If email confirmation is on, verify your email provider's ability to send to the intended users; default Supabase SMTP may limit recipients/rate.
5. Visit your GitHub Pages URL, choose Create an account, confirm email, and log in.

## Access model
- All authenticated users can read/change/delete demo trains, schedules, passengers and bookings based on the RLS policies already run in your Supabase project.
- Never put real passenger information in a publicly sign-up-enabled demo: any person who registers can access and change it.
- `public.users` is not used for role checks in this version; all signed-in people see the same dashboard features.
- The original project's Supabase URL/key have been removed from all supplied HTML files. The full original repository history is not copied.

## Known limitations / checks
- The source site's functions were written for its previous database. Some advanced workflow edge cases, transactional seat updates, restoration and reports may need additional improvements; **the bundle was statically checked, not run against your live Supabase**.
- No new SQL migration is required for the 5 basic tables you created earlier, but verify table grants/RLS in Supabase if API says 'permission denied'.
- GitHub Pages deployment must be HTTPS; confirm the URL of the repository under Settings → Pages.
