# Evingo website — how to put it live

The whole site is one file, `index.html`. Waitlist signups are saved to a Google Sheet through a small Google Apps Script (`backend/Code.gs`). Everything here is free.

## 1. The waitlist database (already set up)

Signups go to a free **Google Form** ("Evingo Waitlist Form") that writes every response into the **Evingo Waitlist** Google Sheet, on the "Waitlist" tab. No servers, no accounts, no limits worth worrying about.

- Share the Sheet with your co-founder so the team can see signups.
- Repeat emails are highlighted orange in the Sheet. The site also tells a visitor "You're already on the list" if they sign up twice from the same browser.
- The form's IDs live in `CONFIG.GOOGLE_FORM` near the bottom of `index.html`. Don't edit the Form's questions (renaming is fine; deleting or reordering can break the link).
- Don't share the Form's own link publicly; people should sign up on the website.

`backend/Code.gs` is an optional upgrade (an Apps Script web app that checks duplicates on the server). It needs Google's app-permission screen, which was blocked on this account, so it isn't used right now.

## 2. Contact email

Optional: put an address in `CONTACT_EMAIL` in `index.html` to show a Contact link in the footer.

## 3. Host it

Easiest: go to **app.netlify.com/drop**, drag the folder with `index.html` onto the page. You get a live link in seconds; sign up (free) to keep it and connect a domain like evingo.ca later. GitHub Pages or Vercel work too.

## 4. Test it

Submit the form on the live site with your own details. A new row should appear in the Sheet within a few seconds.

Note: the Claude preview link can't send data to Google (it blocks outside connections), so the waitlist only saves on the hosted site.

## Logo
The `logo/` folder has your logo redrawn as clean vector SVGs (light and dark versions of the full logo, the E mark alone, the wordmark alone, and see-through lockups). Use these instead of the PDF on the web; they stay sharp at any size.

Your E mark now doubles as the E in EVINGO: use `evingo-wordmark-with-mark-*.svg` (name only) or `evingo-lockup-horizontal-*.svg` (with "AI CLINIC RECEPTION").

## Eva
The `eva/` folder has Eva, the Evingo character, as SVG files (idle, listening, happy, talk) for slides, social posts or stickers. On the site she only appears small: next to the example call and on the waitlist confirmation.

## Things to keep accurate
- The hardware is labelled a **conceptual prototype**. Don't add specs, prices or dates until they're real.
- The "8 of 10 clinics" stat and its 2026 date come from your own calls. Keep them exact.
- The "Where Evingo stands" section describes the prototype. Update it as features ship, and move items out of "Planned" only when they work.
