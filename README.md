# 💸 Deal Drop — Never Miss a Price Drop

**Deal Drop** is a full-stack price tracking platform that watches product prices across any e-commerce site and instantly alerts you the moment they drop below your target — so you never overpay again.

🔗 **Live App:** [dealdrop-smart.vercel.app](https://dealdrop-smart.vercel.app)

---

## ✨ Overview

Prices change constantly, but nobody has time to manually refresh product pages hoping for a discount. **Deal Drop** automates that entirely: paste a product URL, set your target price, and let the platform track it in the background — even on JavaScript-heavy sites with anti-bot protection — using **Firecrawl** to reliably extract live pricing data. When the price drops, you get an email the moment it happens.

---

## 🚀 Key Features

- 🔗 **Track Any Product** — Add a URL from virtually any e-commerce site and start tracking instantly
- ⚡ **Lightning-Fast Extraction** — Powered by Firecrawl, handling JavaScript-rendered and dynamic content in seconds
- 🛡️ **Reliable Across Sites** — Built-in anti-bot handling means tracking keeps working where basic scrapers fail
- 🔔 **Smart Price-Drop Alerts** — Get notified by email the instant a tracked price falls below your target
- ⏱️ **Automated Background Checks** — Scheduled cron jobs continuously re-check tracked prices with no manual refresh needed
- 🔐 **Secure Authentication** — User accounts and sessions managed via Supabase Auth
- 🎨 **Clean, Modern UI** — Built with shadcn/ui for a fast, accessible experience
- 🗄️ **Reliable Data Layer** — Supabase (PostgreSQL) stores tracked products, price history, and alert preferences

---

## 🧱 Tech Stack

| Layer | Technology |
|---|---|
| Frontend | [React](https://react.dev/) + [Next.js](https://nextjs.org/) |
| UI Components | [shadcn/ui](https://ui.shadcn.com/) + Tailwind CSS |
| Auth | [Supabase Auth](https://supabase.com/auth) |
| Database | [Supabase](https://supabase.com/) (PostgreSQL) |
| Price Extraction / Scraping | [Firecrawl](https://www.firecrawl.dev/) |
| Email Alerts | Resend (email delivery) |
| Scheduled Jobs | Vercel Cron |
| Hosting / Deployment | [Vercel](https://vercel.com/) |

---

## 🏗️ How It Works

1. **Sign in** via Supabase Auth
2. **Paste a product URL** you want to track and set your target price
3. **Firecrawl extracts** the current price, even from JS-rendered or bot-protected pages
4. A **scheduled cron job** periodically re-checks the price in the background
5. The moment the price drops below your target, **an email alert** is sent instantly
6. Track price history over time and manage all your tracked products from one dashboard

---

## 🛠️ Getting Started

### Prerequisites
- Node.js (v18+)
- A Supabase project (PostgreSQL + Auth enabled)
- A Firecrawl API key
- An email provider API key (e.g. Resend) for alerts

### Installation

```bash
# Clone the repository
git clone https://github.com/<your-username>/dealdrop.git
cd dealdrop

# Install dependencies
npm install

# Set up environment variables
cp .env.example .env.local
# then fill in your keys (see below)

# Run the development server
npm run dev
```

Visit `http://localhost:3000` to see it running locally.

---

## 🔑 Environment Variables

Create a `.env.local` file with the following:

```env
# Supabase
NEXT_PUBLIC_SUPABASE_URL=
NEXT_PUBLIC_SUPABASE_ANON_KEY=
SUPABASE_SERVICE_ROLE_KEY=

# Firecrawl
FIRECRAWL_API_KEY=

# Email (Resend)
RESEND_API_KEY=

# Cron secret (to protect scheduled endpoint)
CRON_SECRET=
```

---

## 📁 Project Structure

```
dealdrop/
├── app/                 # Next.js App Router pages & API routes
├── components/          # Reusable UI components (shadcn/ui based)
├── lib/                 # Utility functions, service clients (Firecrawl, Supabase, email)
├── cron/ or app/api/cron/  # Scheduled price-check endpoint
└── public/              # Static assets
```

---

## 🗺️ Roadmap

- [ ] Price history charts per product
- [ ] Multi-channel alerts (SMS, push notifications)
- [ ] Browser extension for one-click tracking
- [ ] Price prediction / "best time to buy" insights
- [ ] Shared/public wishlists

---

## 🤝 Contributing

Contributions, issues, and feature requests are welcome! Feel free to open an issue or submit a PR.

---

## 📄 License

This project is licensed under the MIT License.

---

## 📬 Contact

Built with ❤️ by **Rohan Dey** — feel free to reach out for feedback, collaboration, or questions.
