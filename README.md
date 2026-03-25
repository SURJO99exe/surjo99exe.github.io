# 🚀 Dev Portfolio — Single-File Portfolio Website

A fully-featured, single-file personal developer portfolio with a built-in admin dashboard. No frameworks, no build tools, no backend — just one HTML file you can open in any browser or deploy anywhere in seconds.

---

## ✨ Features

### 🌐 Public Pages
| Page | Description |
|------|-------------|
| **Home** | Animated hero section with typing effect, live counters, and stats |
| **About** | Bio, animated skill bars, GitHub live activity, experience timeline |
| **Projects** | GitHub repos loaded live via API + custom projects you add manually |
| **Services** | Service cards with icon, description, and pricing |
| **Blog** | Blog posts loaded live from dev.to API |
| **Contact** | Contact form with validation, email copy, and social links |

### 🔒 Admin Dashboard (`/admin` — password: `admin123`)
| Tab | What You Can Edit |
|-----|-------------------|
| **Overview** | Analytics charts (visitors, traffic sources, page views), message count |
| **Profile** | Name, job title, bio, email, location, hours, GitHub & dev.to usernames |
| **Skills** | Add / edit / delete skill bars with custom percentages |
| **Projects** | Add custom projects with icon, description, tech stack, repo & live URL |
| **Services** | Add / edit / delete service cards with icon, title, description, pricing |
| **Links** | GitHub, LinkedIn, Twitter, Open Source, Talks & Events, CV URL |
| **CV** | Edit CV plain text content or set a direct download URL |
| **Messages** | View all contact form submissions with sender details |

> Every save instantly updates the live site. All data persists in `localStorage`.

---

## 🚀 Getting Started

### Option 1 — Open Locally
```bash
# Just open the file in your browser
open portfolio.html
# or double-click the file in your file manager
```

### Option 2 — Deploy to GitHub Pages
```bash
# 1. Create a new repo on GitHub
# 2. Upload portfolio.html and rename it to index.html
# 3. Go to Settings → Pages → Source: main branch
# 4. Your site is live at https://yourusername.github.io/repo-name
```

### Option 3 — Deploy to Netlify / Vercel
```bash
# Rename portfolio.html → index.html
# Drag & drop the file into netlify.com/drop
# Done — live URL in seconds
```

---

## ⚙️ Configuration

### Step 1 — Log in to Admin
Navigate to the **Admin** page (link in footer or mobile menu) and enter the password:
```
admin123
```

### Step 2 — Update Your Profile
Go to **Profile** tab and fill in:
- Your full name and job title
- Bio paragraphs
- Email, location, working hours
- **GitHub username** — this loads your real repos automatically
- **dev.to username** — this loads your real blog posts automatically

### Step 3 — Set Social Links
Go to **Links** tab and add:
- GitHub profile URL
- LinkedIn URL
- Twitter / X URL
- Open Source URL (shown in footer)
- Talks & Events URL (shown in footer)
- CV direct URL (optional — leave blank to auto-generate from CV text)

### Step 4 — Add Projects
Go to **Projects** tab to add custom projects with:
- Emoji icon + project name
- Description
- Tech stack (comma-separated)
- Card background color
- GitHub repo URL
- Live demo URL

### Step 5 — Customize Services
Go to **Services** tab to edit the default 8 services or add your own.

### Step 6 — Change Password
Find this line in the HTML and change `admin123` to your own password:
```html
if(document.getElementById('adminPwd').value==='admin123'){
```

---

## 🎨 Customization

### Change Accent Color
Find `:root` in the `<style>` block and update `--accent`:
```css
:root {
  --accent: #00d4aa;   /* teal (default) */
  --accent2: #0088ff;  /* blue */
  --accent3: #ff6b35;  /* orange */
}
```

### Change Fonts
The portfolio uses Google Fonts. Replace the font imports and CSS variables:
```css
--mono: "DM Mono", ui-monospace, monospace;
--serif: "DM Serif Display", Georgia, serif;
--sans: "Outfit", system-ui, sans-serif;
```

### Modify Typing Phrases
Find the `TL` array in the `<script>` block:
```js
const TL = [
  "Full Stack Developer",
  "Open Source Contributor",
  "UI/UX Enthusiast",
  "Problem Solver",
  "Coffee-Driven Coder ☕"
];
```

### Edit Default Data
All site content lives in the `SD` object near the top of the `<script>` block. You can edit defaults directly there before deploying.

---

## 🔌 Live API Integrations

| API | What It Provides | How to Enable |
|-----|-----------------|---------------|
| **GitHub API** | Real repos, star counts, follower count, contribution grid | Set GitHub username in Admin → Profile |
| **dev.to API** | Real blog posts with cover images, tags, read time | Set dev.to username in Admin → Profile |

Both APIs are free and require no API key for basic usage.

> **Note:** GitHub API has a rate limit of 60 requests/hour for unauthenticated requests. This is more than enough for a personal portfolio.

---

## 📦 Tech Stack

| Technology | Usage |
|-----------|-------|
| **Vanilla HTML/CSS/JS** | Zero dependencies, zero build step |
| **Chart.js** | Admin dashboard analytics charts (CDN) |
| **Google Fonts** | DM Serif Display, DM Mono, Outfit (CDN) |
| **GitHub REST API** | Live repository data |
| **dev.to API** | Live blog posts |
| **localStorage** | Persistent admin edits |

---

## 📁 File Structure

```
portfolio.html          ← The entire website (single file)
README.md               ← This file
```

That's it. One file.

---

## 🛡️ Security Notes

- The admin password is stored in plain text in the HTML. This is intentional for simplicity — the admin panel only edits `localStorage` data, so there is no server-side risk.
- For production use, consider moving to a backend-based CMS or environment variable if you need real authentication.
- GitHub and dev.to API calls are read-only and unauthenticated.

---

## 📱 Browser Support

| Browser | Status |
|---------|--------|
| Chrome / Edge | ✅ Full support |
| Firefox | ✅ Full support |
| Safari | ✅ Full support |
| Mobile (iOS/Android) | ✅ Responsive design |

---

## 🗂️ Pages Reference

```
Home        →  Hero, stats counters, typing animation
About       →  Bio, skill bars, GitHub activity, timeline
Projects    →  GitHub repos + custom projects, filter by language
Services    →  Service cards + testimonials
Blog        →  dev.to posts (live) or placeholder cards
Contact     →  Form with validation + social links
Admin       →  Full dashboard (password protected)
```

---

## 💾 Data Persistence

All admin edits are saved to `localStorage` under the key `_pSD3`. This means:
- ✅ Changes persist across page refreshes
- ✅ Works completely offline after first load
- ❌ Changes are browser/device specific (not synced across devices)
- ❌ Clearing browser data will reset to defaults

To back up your data, open browser DevTools → Application → Local Storage → copy the `_pSD3` value.

---

## 🧩 Default Services Included

1. 🌐 Web Development — From $2,500
2. 📱 Mobile Apps — From $4,000
3. 🔗 API Development — From $1,500
4. ☁️ Cloud & DevOps — From $1,200
5. 🎨 UI/UX Design — From $800
6. 🚀 Performance Audit — From $500
7. 🤖 AI Integration — From $3,000
8. 🛡️ Security Audit — From $1,000

All editable from Admin → Services.

---

## 📬 Contact Form

Submissions are stored in `localStorage` and viewable in Admin → Messages. To receive emails, integrate a service like:
- [Formspree](https://formspree.io) — free tier available
- [EmailJS](https://emailjs.com) — free tier available
- [Web3Forms](https://web3forms.com) — free tier available

Replace the form submit handler in the script with the chosen service's API call.

---

## 📄 License

Free to use for personal and commercial portfolios. Attribution appreciated but not required.

---

## 🙏 Credits

- Fonts: [Google Fonts](https://fonts.google.com)
- Charts: [Chart.js](https://chartjs.org)
- Icons: Emoji (no icon library needed)
- Data: [GitHub API](https://docs.github.com/en/rest) · [dev.to API](https://developers.forem.com/api)

---

*Built with ❤️ and lots of ☕ — v3.0.0*
