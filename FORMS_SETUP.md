# Form Setup Guide (Formspree)

All contact and footer forms are wired to **Formspree** with honeypot spam protection. Before forms work, you must create Formspree accounts and replace the placeholders.

## Step 1: Create Formspree Account

1. Go to [formspree.io](https://formspree.io)
2. Sign up (free tier: 50 submissions/month)
3. Create **two forms** in your Formspree dashboard:
   - **Contact form** (for contact-one, contact-two, contact-three)
   - **Newsletter form** (for footer subscription)

## Step 2: Get Your Form IDs

After creating each form, Formspree gives you an endpoint like:

`https://formspree.io/f/xxxxxxxx`

Copy the form ID (the `xxxxxxxx` part).

## Step 3: Replace Placeholders

Search and replace in all HTML files:

| Placeholder | Replace with | Example |
|-------------|--------------|---------|
| `YOUR_CONTACT_FORM_ID` | Your contact form ID | `mzbjzokq` |
| `YOUR_NEWSLETTER_FORM_ID` | Your newsletter form ID | `xjvqyvpn` |

**Option A – Find & Replace in editor**
- Find: `YOUR_CONTACT_FORM_ID` → Replace with: your actual contact form ID
- Find: `YOUR_NEWSLETTER_FORM_ID` → Replace with: your actual newsletter form ID

**Option B – Terminal**
```bash
# From project root
find . -name "*.html" -exec sed -i '' 's/YOUR_CONTACT_FORM_ID/your_actual_id/g' {} \;
find . -name "*.html" -exec sed -i '' 's/YOUR_NEWSLETTER_FORM_ID/your_actual_id/g' {} \;
```

## Step 4: Set Up Formspree (Optional)

In your Formspree dashboard for each form:

1. **Notifications** – Ensure your email (`customerservice@expresspaymentsinc.com`) receives submissions
2. **Spam filtering** – Honeypot is already used; you can enable reCAPTCHA for extra protection
3. **Redirect** – Optional: add a `_next` hidden field to redirect users after success instead of Formspree’s thank-you page

## Forms Updated

- **Contact Form V1** – `contact-one.html`
- **Contact Form V2** – `contact-two.html` (Get a Quote)
- **Contact Form V3** – `contact-three.html` (Schedule Demo)
- **Footer Newsletter Form** – All pages with footer

## Spam Protection

- **Honeypot field** – Hidden `_gotcha` field; bots often fill it, submissions with it filled are discarded by Formspree
- **Formspree** – Built-in spam filtering
- **Optional** – Add reCAPTCHA in Formspree settings for more protection
