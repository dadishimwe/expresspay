# Google Analytics 4 Setup for Express Payments

The GA4 tracking snippet has been added to **all 42 HTML pages** across your site. To finish setup, replace the placeholder with your Measurement ID.

## Step 1: Get your GA4 Measurement ID

1. Go to [Google Analytics](https://analytics.google.com/) and sign in.
2. Click **Admin** (gear icon, bottom left).
3. In the **Property** column, create a new property or select an existing one for Express Payments.
4. Under **Data streams**, click your web stream (or create one for `www.expresspaymentsinc.com`).
5. Copy the **Measurement ID** (format: `G-CN5SVM5X1B`).

## Step 2: Replace the placeholder in your site

In every HTML file, replace `G-CN5SVM5X1B` with your actual Measurement ID in **two places** in the GA4 snippet:

1. In the script `src` URL: `...gtag/js?id=G-CN5SVM5X1B`
2. In the config call: `gtag('config', 'G-CN5SVM5X1B');`

**Option A – Find & replace in your editor**
- Find: `G-CN5SVM5X1B`
- Replace with: `G-ABC123XYZ` (use your real ID)
- Replace all occurrences across the project

**Option B – Terminal (from the site root)**

```bash
# Replace G-CN5SVM5X1B with your actual ID, e.g. G-ABC123XYZ
find . -name "*.html" -exec sed -i '' 's/G-CN5SVM5X1B/G-YOUR_ID_HERE/g' {} \;
```

## Step 3: Verify tracking

1. Deploy the updated site (e.g. push to GitHub for Pages).
2. In GA4, open **Reports → Realtime**.
3. Visit your site in another tab.
4. Confirm your visit appears in Realtime within ~30 seconds.

## What GA4 tracks (automatic)

- **Page views** – Every page visited
- **Sessions** – How often people visit
- **Engagement time** – Time on each page / site
- **Traffic sources** – Where visitors come from (search, direct, referral)
- **Device & location** – Basic geography and device type

No further code changes are needed. GA4 will collect this data automatically once the Measurement ID is set.

---

Next: See `FORMS_SETUP.md` for Formspree form configuration.
