# vent.
### A safe space to be heard. No judgment. No advice. Just space.

---

## Deploying to Vercel — No Build Step Required

This version deploys as a static HTML file — no npm, no build process, no errors.

---

### Step 1 — Get an Anthropic API Key

1. Go to [console.anthropic.com](https://console.anthropic.com)
2. Sign in → **API Keys** → **Create Key**
3. Copy the key — you'll need it in Step 4

---

### Step 2 — Upload to GitHub

1. Go to [github.com](https://github.com) → create a free account if needed
2. Click **New repository** → name it `vent-app` → **Create**
3. Upload all files from this folder (drag and drop into GitHub)
4. Click **Commit changes**

---

### Step 3 — Deploy on Vercel

1. Go to [vercel.com](https://vercel.com) → sign up with GitHub
2. Click **Add New → Project** → select your `vent-app` repo
3. **Important:** In the build settings, set:
   - **Framework Preset:** Other
   - **Build Command:** *(leave empty)*
   - **Output Directory:** *(leave empty or set to `.`)*
4. Click **Deploy**

---

### Step 4 — Add your API Key

1. In Vercel → your project → **Settings** → **Environment Variables**
2. Add:
   - **Name:** `ANTHROPIC_API_KEY`
   - **Value:** your key from Step 1
3. Click **Save**
4. Go to **Deployments** → three dots → **Redeploy**

Your app is live at `your-project.vercel.app` — share this link with beta testers.

---

### Step 5 — Custom Domain (Optional)

In Vercel → **Settings** → **Domains** → add your domain and follow DNS instructions.

---

## Collecting Waitlist Emails

When users hit the free limit and enter their email, it currently logs to console only.
To capture them for real, the simplest approach with no code changes needed:

1. Create a free [Mailchimp](https://mailchimp.com) or [ConvertKit](https://convertkit.com) account
2. Create a form and get the form action URL
3. In `index.html`, find `handleWaitlistSubmit` and replace the `console.log` line with a fetch POST to your form URL

---

## Files in this package

```
index.html        — The entire app (React via CDN, no build needed)
api/chat.js       — Serverless function that proxies Anthropic API calls
vercel.json       — Vercel routing config
README.md         — This file
```

---

*vent. is not a substitute for professional mental health care. Crisis support is always free.*
