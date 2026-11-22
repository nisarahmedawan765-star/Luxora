# 💎 LUXORA MARKET — Full-Stack Luxury E-Commerce Marketplace

A complete, high-end, full-stack luxury e-commerce marketplace called **LUXORA MARKET** built with **HTML5, CSS3, Vanilla JavaScript ES6, and Supabase** (PostgreSQL, Authentication, Storage, and Row Level Security).

---

## 🎨 Luxury Brand & Color Palette

- **Deep Black**: `#0B0B0B`
- **Dark Charcoal**: `#151515`
- **Luxury Gold**: `#F2BD12` / `#C9A24D`
- **Action Green**: `#16A34A` / `#246B24`
- **Pure White**: `#FFFFFF`
- **Light Gray**: `#F5F5F5`

---

## 🏗️ Architecture & Technology Stack

- **Frontend**: Pure HTML5, Modular CSS3 (`style.css`, `components.css`, `responsive.css`, `admin.css`), Vanilla JavaScript ES6+ modules.
- **Backend & Database**: Supabase PostgreSQL with 28 relational tables, Supabase Auth, Supabase Storage, and granular Row Level Security (RLS) policies.
- **Client SDK**: Official `@supabase/supabase-js` via CDN.
- **Zero Framework Bloat**: No Node.js, no PHP, no Apache/XAMPP, no React required. Runs directly as a modern web application in any browser.

---

## 🚀 How to Set Up with Supabase

### Step 1: Create a Supabase Project
1. Go to [https://supabase.com](https://supabase.com) and create a free project.
2. Note your **Project URL** and **anon/public API key** from **Project Settings $\to$ API**.

### Step 2: Run Database Migrations in Supabase SQL Editor
1. In the Supabase Dashboard, open the **SQL Editor**.
2. Run `supabase/schema.sql` (Creates all 28 tables, triggers, indexes, and constraints).
3. Run `supabase/policies.sql` (Applies strict Row Level Security policies).
4. Run `supabase/seed.sql` (Inserts luxury categories, brands, products, coupons, and banners).

### Step 3: Connect Credentials in Frontend
Open `assets/js/supabase.js` and enter your Supabase Project URL and public anon key:

```javascript
const SUPABASE_CONFIG = {
  SUPABASE_URL: 'https://YOUR_PROJECT_ID.supabase.co',
  SUPABASE_ANON_KEY: 'YOUR_SUPABASE_ANON_KEY',
  PLATFORM_COMMISSION_PERCENT: 10.0,
  FREE_SHIPPING_THRESHOLD: 5000.0,
  STANDARD_SHIPPING_FEE: 250.0,
  EXPRESS_SHIPPING_FEE: 550.0
};
```

---

## 🔑 Demo & Test Accounts

| Role | Email | Password | Access Area |
| :--- | :--- | :--- | :--- |
| **Customer** | `customer@luxora.test` | `password123` | Storefront, Wishlist, Cart, 4-Step Checkout, Account Dashboard, Order Tracking |
| **Seller** | `seller@luxora.test` | `password123` | Seller Center, Product CRUD, Order Fulfillment, Earnings Ledger, Withdrawals |
| **Super Admin** | `admin@luxora.test` | `password123` | Super Admin Console, Product Approvals/Rejections, Customer Bans, Audit Logs |

> **Floating Role Switcher**: A floating widget is enabled at the bottom-left of the screen to instantaneously test and switch between Customer, Seller, and Admin personas in 1 click!

---

## 📂 Project Structure

```
luxora-market/
├── index.html                  # Luxury Homepage (Hero Carousel, Flash Deals, Categories)
├── shop.html                   # Catalog with multi-filter, search, price slider, sorting
├── product.html                # Product Details (Gallery zoom, variants, specs, reviews, Q&A)
├── cart.html                   # Dynamic shopping cart, coupon validator, free shipping meter
├── checkout.html               # 4-Step Checkout (Address, Shipping, Payment, Review & Order)
├── order-success.html          # Order confirmation and celebration screen
├── track-order.html            # Visual 6-stage order tracking timeline
├── wishlist.html               # Personal customer wishlist
├── deals.html                  # Flash Deals and discount promotions
├── best-sellers.html           # Best sellers collection
├── new-arrivals.html           # New arrival catalog
├── brands.html                 # Official brand directory
├── about.html                  # About Luxora Market
├── contact.html                # VIP 24/7 Concierge contact form
├── login.html                  # Customer & Merchant Sign In
├── register.html               # Customer Registration
├── account.html                # Customer profile, orders, addresses, settings
├── orders.html                 # Order history with cancellation & returns
│
├── seller/
│   ├── register.html           # Merchant onboarding application
│   ├── dashboard.html          # Seller dashboard, KPI cards, top selling products
│   ├── products.html           # Product catalog management (Publish modal, stock, delete)
│   ├── orders.html             # Order fulfillment (Processing -> Packed -> Shipped)
│   ├── earnings.html           # Financial ledger & 10% platform commission breakdown
│   └── withdrawals.html        # Payout request portal with available balance reserve logic
│
├── admin/
│   ├── login.html              # Staff administrative login
│   ├── dashboard.html          # Marketplace GMV, platform revenue, order metrics
│   ├── products.html           # Product moderation (Approve / Reject with reason dropdown)
│   ├── categories.html         # Categories taxonomy manager
│   ├── sellers.html            # Seller verification & custom commission overrides
│   ├── customers.html          # Customer moderation modal (Warning, Restrict, Suspend, Ban)
│   ├── orders.html             # Global orders management
│   ├── coupons.html            # Promotional coupon engine
│   ├── reviews.html            # Reviews moderation
│   └── settings.html           # Platform settings & immutable audit logs viewer
│
├── assets/
│   ├── css/
│   │   ├── style.css           # Global luxury variables, typography, buttons, cards
│   │   ├── components.css      # Header, mega menu, carousel, countdown, toasts, modal
│   │   ├── responsive.css      # Mobile drawer, bottom navigation, responsive grids
│   │   └── admin.css           # Dark sidebar, data tables, metrics cards, status badges
│   └── js/
│       ├── supabase.js         # Supabase client & fallback persistence engine
│       ├── auth.js             # Auth session handlers & role switcher
│       ├── products.js         # Products catalog, filters, search, and Quick View modal
│       ├── cart.js             # Cart management, coupon calculations, badges
│       ├── wishlist.js         # Wishlist management
│       ├── checkout.js         # 4-Step checkout state machine & order placement
│       ├── orders.js           # 6-Stage order tracking timeline & actions
│       ├── seller.js           # Seller portal dashboard, product CRUD, payouts
│       ├── admin.js            # Admin moderation, customer ban modal, audit logger
│       └── main.js             # App controller, live countdown timer, hero carousel
│
└── supabase/
    ├── schema.sql              # Complete PostgreSQL schema (28 relational tables)
    ├── policies.sql            # Granular Row Level Security (RLS) policies
    └── seed.sql                # Realistic luxury seed dataset
```

---

## 🛡️ Security & Integrity

- **Row Level Security**: Database operations are verified against caller UUID and roles.
- **Client-Side Safety**: No secret keys exposed.
- **Input Validation**: Server and client-side form validation.
- **Immutable Audit Logs**: Every administrative moderation action (Customer ban/suspension, Seller approval, Product rejection with reason code, Status changes) is logged with timestamp, staff name, target ID, and reason.
