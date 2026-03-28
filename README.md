# Mahesh — Portfolio (Next.js 14 + Framer Motion)

A clean, editorial portfolio built with **Next.js 14 App Router**, **Framer Motion** animations, and a **real contact form** powered by Resend.

## Tech Stack

| Layer | Tech |
|-------|------|
| Framework | Next.js 14 (App Router) |
| Animations | Framer Motion 11 |
| Styles | CSS Modules + CSS Variables |
| Email | Resend API (free tier) |
| Deploy | Vercel (free) |

## Project Structure

```
app/
  layout.js              ← Root layout (Nav + Footer)
  globals.css            ← Design tokens & shared styles
  page.js                ← Home / Hero (Framer Motion)
  about/page.js          ← About Me + Timeline
  projects/page.js       ← Projects grid
  skills/page.js         ← Skills with animated bars
  contact/page.js        ← Contact form + links
  api/contact/route.js   ← Contact API → Resend email
components/
  Nav.js                 ← Sticky nav, active link highlight
  Footer.js              ← Footer
  ProjectCard.js         ← Animated card (whileInView)
  SkillBar.js            ← Intersection Observer bar animation
  ContactForm.js         ← Controlled form → real API call
```

## Getting Started

```bash
# 1. Install dependencies
npm install

# 2. Copy env file and fill in your values
cp .env.local.example .env.local

# 3. Run dev server
npm run dev

# Open http://localhost:3000
```

## Setting Up the Contact Form (Resend)

1. Sign up at **[resend.com](https://resend.com)** — free tier gives 3,000 emails/month
2. Create an API key
3. Edit `.env.local`:

```env
RESEND_API_KEY=re_your_key_here
CONTACT_EMAIL=your@email.com
```

> **Without the key set**, the form still works in dev — submissions are logged to the console instead of emailed.

## Deploy to Vercel (Free)

```bash
npm i -g vercel
vercel
```

Or push to GitHub → connect at **vercel.com** → add env vars in the Vercel dashboard.

## Customise

| What | Where |
|------|-------|
| Bio / details | `app/about/page.js` |
| Projects | `app/projects/page.js` → `projects` array |
| Skill levels | `app/skills/page.js` → skill arrays |
| Contact links | `app/contact/page.js` → `links` array |
| Colors / fonts | `app/globals.css` → `:root` variables |
| Animation speed | Each component's `transition` props |
