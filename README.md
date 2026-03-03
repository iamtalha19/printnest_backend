<h1 align="center">🖨️ PrintNest</h1>
<p align="center">
  <strong>Modern Print-on-Demand E-Commerce Platform</strong><br/>
  Full-stack Next.js store with admin panel, AI descriptions, Stripe & PayPal payments, and email order notifications
</p>

<p align="center">
  <a href="https://nextjs.org"><img src="https://img.shields.io/badge/Next.js-16.1.6-black?logo=next.js" alt="Next.js"/></a>
  <a href="https://reactjs.org"><img src="https://img.shields.io/badge/React-19.2.3-61DAFB?logo=react&logoColor=black" alt="React"/></a>
  <a href="https://typescriptlang.org"><img src="https://img.shields.io/badge/TypeScript-5.x-3178C6?logo=typescript&logoColor=white" alt="TypeScript"/></a>
  <a href="https://mongoosejs.com"><img src="https://img.shields.io/badge/MongoDB-Mongoose-47A248?logo=mongodb&logoColor=white" alt="MongoDB"/></a>
  <a href="https://redux-toolkit.js.org"><img src="https://img.shields.io/badge/Redux_Toolkit-2.x-764ABC?logo=redux&logoColor=white" alt="Redux Toolkit"/></a>
  <a href="https://tailwindcss.com"><img src="https://img.shields.io/badge/Tailwind_CSS-4.x-06B6D4?logo=tailwindcss&logoColor=white" alt="Tailwind CSS"/></a>
  <a href="https://stripe.com"><img src="https://img.shields.io/badge/Stripe-Payment-635BFF?logo=stripe&logoColor=white" alt="Stripe"/></a>
  <a href="https://paypal.com"><img src="https://img.shields.io/badge/PayPal-Payment-00457C?logo=paypal&logoColor=white" alt="PayPal"/></a>
</p>

---

## ✨ Key Features

### 🛒 E-Commerce

- **Product Catalog** with quick view, comparison, and wishlist
- **Shopping Cart** with quantity controls and localStorage persistence
- **Wishlist** with Redux state management
- **Dynamic Product Categories** (T-shirts, Business Cards, Hoodies, Packaging)
- **Product Review System** with ratings and comments
- **Checkout** with billing, payment selection, and order confirmation

### � Payments

- **Stripe** — card payments via Stripe Checkout Sessions
- **PayPal** — PayPal Orders API (sandbox) with redirect-based flow
- Both payment methods redirect to `/thank-you` on success

### �🔐 Authentication & Users

- **Sign Up / Login** with bcrypt password hashing
- **JWT Authentication** via HTTP-only cookies
- **User Dashboard** with order history
- **Guest Checkout** support
- **Role-based Access** — admin vs standard user

### 🛠️ Admin Panel (`/admin`)

- **Dashboard** with charts: revenue, orders, top products, user stats
- **Product Management** — add, edit, delete products
- **Category Management** — manage product categories (slug + image)
- **Order Management** — view and update order statuses
- **User Management** — view, promote, delete users
- **Review Moderation** — view and manage all reviews
- **AI Description Generator** powered by Groq (Llama 3.1)
- **Image Upload** endpoint for products

### 🤖 AI Integration

- **AI Product Descriptions** via Groq API (Llama 3.1 8B Instant)
- Generates compelling 2–3 sentence product descriptions from a title

### 📧 Order & Email

- Orders saved to **MongoDB**
- Email confirmation sent to **customer and store** via Nodemailer (Gmail SMTP)
- Guest and authenticated order tracking

---

## 📋 Table of Contents

- [Tech Stack](#%EF%B8%8F-tech-stack)
- [Package Installation](#-package-installation-commands)
- [Project Structure](#-project-structure)
- [Getting Started](#-getting-started)
- [Environment Variables](#-environment-variables)
- [API Routes](#-api-routes)
- [Database & Models](#%EF%B8%8F-database--models)
- [Redux Store](#-redux-store)
- [Admin Panel](#%EF%B8%8F-admin-panel-1)
- [Pages & Routes](#-pages--routes)
- [Deployment](#-deployment)

---

## 🛠️ Tech Stack

| Category             | Technology                   |
| -------------------- | ---------------------------- |
| **Framework**        | Next.js 16.1.6 (App Router)  |
| **Frontend**         | React 19.2.3                 |
| **Language**         | TypeScript 5.x               |
| **Database**         | MongoDB via Mongoose 9.x     |
| **Styling**          | Tailwind CSS 4.x             |
| **Animations**       | Framer Motion 12.x           |
| **State Management** | Redux Toolkit 2.x            |
| **Icons**            | Lucide React                 |
| **Authentication**   | JWT + bcryptjs               |
| **Email**            | Nodemailer (Gmail SMTP)      |
| **AI**               | Groq API (Llama 3.1 8B)      |
| **Payments**         | Stripe + PayPal (REST API)   |
| **Utilities**        | clsx, tailwind-merge, cookie |

---

## 📦 Package Installation Commands

### Install All at Once

```bash
npm install
```

### Production Dependencies

```bash
npm install @google/generative-ai @reduxjs/toolkit @stripe/stripe-js bcryptjs clsx cookie framer-motion jsonwebtoken lucide-react mongoose next nodemailer react react-dom react-redux stripe tailwind-merge
```

<details>
<summary>Install individually by category</summary>

#### Framework & Core

```bash
npm install next@16.1.6
npm install react@19.2.3
npm install react-dom@19.2.3
```

#### Database

```bash
npm install mongoose@^9.2.1
```

#### State Management

```bash
npm install @reduxjs/toolkit@^2.11.2
npm install react-redux@^9.2.0
```

#### Authentication & Security

```bash
npm install bcryptjs@^3.0.3
npm install jsonwebtoken@^9.0.3
npm install cookie@^1.1.1
```

#### Payments

```bash
npm install stripe@^20.4.0           # Stripe server SDK
npm install @stripe/stripe-js@^8.8.0  # Stripe client SDK
# PayPal uses the REST API via fetch — no package needed
```

#### UI & Styling

```bash
npm install framer-motion@^12.30.0
npm install lucide-react@^0.563.0
npm install clsx@^2.1.1
npm install tailwind-merge@^3.4.0
```

#### Email & AI

```bash
npm install nodemailer@^7.0.13
npm install @google/generative-ai@^0.24.1
```

</details>

### Development Dependencies

```bash
npm install -D @tailwindcss/postcss @types/bcryptjs @types/cookie @types/jsonwebtoken @types/node @types/nodemailer @types/react @types/react-dom babel-plugin-react-compiler eslint eslint-config-next tailwindcss typescript
```

<details>
<summary>Install individually by category</summary>

#### TypeScript & Types

```bash
npm install -D typescript@^5
npm install -D @types/node@^20
npm install -D @types/react@^19
npm install -D @types/react-dom@^19
npm install -D @types/bcryptjs@^2.4.6
npm install -D @types/cookie@^0.6.0
npm install -D @types/jsonwebtoken@^9.0.10
npm install -D @types/nodemailer@^7.0.9
```

#### CSS & Build Tools

```bash
npm install -D tailwindcss@^4
npm install -D @tailwindcss/postcss@^4
npm install -D eslint@^9
npm install -D eslint-config-next@16.1.6
npm install -D babel-plugin-react-compiler@1.0.0
```

</details>

### Package Purposes

| Package                 | Purpose                                           |
| ----------------------- | ------------------------------------------------- |
| `@google/generative-ai` | Google AI SDK (installed alongside Groq)          |
| `@reduxjs/toolkit`      | Simplified Redux with createSlice, configureStore |
| `@stripe/stripe-js`     | Stripe client-side SDK (redirect to Checkout)     |
| `bcryptjs`              | Secure password hashing                           |
| `clsx`                  | Conditional className utility                     |
| `cookie`                | HTTP cookie parsing                               |
| `framer-motion`         | Page and component animations                     |
| `jsonwebtoken`          | JWT creation and verification                     |
| `lucide-react`          | Icon component library                            |
| `mongoose`              | MongoDB ODM for data modeling                     |
| `next`                  | React framework (SSR, routing, API)               |
| `nodemailer`            | Send order confirmation emails                    |
| `react` / `react-dom`   | UI library and DOM renderer                       |
| `react-redux`           | Redux bindings for React                          |
| `stripe`                | Stripe server SDK for creating Checkout Sessions  |
| `tailwind-merge`        | Merge Tailwind classes without conflicts          |
| `tailwindcss`           | Utility-first CSS framework                       |
| `typescript`            | Static typing for JavaScript                      |

---

## 📁 Project Structure

```
printnest/
├── src/
│   ├── app/                              # Next.js App Router
│   │   ├── api/                          # API Routes
│   │   │   ├── admin/                    # Admin-only endpoints
│   │   │   │   ├── ai-description/       # POST - AI product description (Groq)
│   │   │   │   ├── categories/           # GET/POST - Manage categories
│   │   │   │   │   └── [id]/             # DELETE/PATCH - Edit or delete category
│   │   │   │   ├── orders/               # GET/PATCH - Manage all orders
│   │   │   │   ├── products/             # GET/POST/DELETE - Manage products
│   │   │   │   ├── stats/                # GET - Dashboard analytics
│   │   │   │   └── users/                # GET/DELETE/PATCH - Manage users
│   │   │   ├── auth/                     # Authentication endpoints
│   │   │   │   ├── login/route.ts
│   │   │   │   ├── logout/route.ts
│   │   │   │   ├── me/route.ts
│   │   │   │   └── signup/route.ts
│   │   │   ├── paypal/
│   │   │   │   └── checkout/route.ts     # POST - Create PayPal order
│   │   │   ├── public/                   # Public data endpoints
│   │   │   │   ├── content/route.ts      # db.json content
│   │   │   │   ├── orders/route.ts       # User orders
│   │   │   │   ├── place-order/route.ts  # Submit order + email
│   │   │   │   └── reviews/              # GET/POST reviews
│   │   │   ├── stripe/
│   │   │   │   └── checkout/route.ts     # POST - Create Stripe Checkout Session
│   │   │   └── upload/route.ts           # Image upload
│   │   │
│   │   ├── admin/                        # Admin pages
│   │   │   ├── dashboard/page.tsx        # Analytics dashboard
│   │   │   ├── products/page.tsx         # Product management
│   │   │   ├── reviews/page.tsx          # Review moderation
│   │   │   └── types.ts                  # Admin TypeScript types
│   │   │
│   │   ├── account/page.tsx              # User dashboard
│   │   ├── blog/[slug]/page.tsx          # Blog post detail
│   │   ├── cart/page.tsx                 # Shopping cart
│   │   ├── category/[slug]/page.tsx      # Category products
│   │   ├── checkout/page.tsx             # Checkout form (Stripe + PayPal)
│   │   ├── login/page.tsx                # Login page
│   │   ├── product/[slug]/page.tsx       # Product detail
│   │   ├── shop/page.tsx                 # All products
│   │   ├── signup/page.tsx               # Registration
│   │   ├── thank-you/page.tsx            # Order confirmation
│   │   ├── wishlist/page.tsx             # Wishlist
│   │   ├── layout.tsx                    # Root layout
│   │   ├── loading.tsx                   # Global loading state
│   │   ├── page.tsx                      # Home page
│   │   └── globals.css
│   │
│   ├── components/                       # Reusable Components
│   │   ├── sections/                     # Home page sections
│   │   │   ├── Hero.tsx
│   │   │   ├── Products.tsx
│   │   │   ├── Categories.tsx
│   │   │   ├── Blog.tsx
│   │   │   ├── About.tsx
│   │   │   ├── HowItWorks.tsx
│   │   │   ├── WhyUs.tsx
│   │   │   ├── Packaging.tsx
│   │   │   ├── Price.tsx
│   │   │   ├── Testimonials.tsx
│   │   │   └── Social.tsx
│   │   ├── admin/                        # Admin UI components
│   │   │   ├── charts/                   # Chart components (8)
│   │   │   ├── tables/                   # Data tables (6)
│   │   │   ├── modals/                   # Modal dialogs (5)
│   │   │   ├── lists/                    # List components (2)
│   │   │   ├── layout/                   # Admin layout (1)
│   │   │   └── ui/                       # Admin UI elements (2)
│   │   ├── auth/                         # Auth components
│   │   ├── layout/                       # Navbar, Footer, etc.
│   │   ├── products/                     # ProductCard, QuickView, etc.
│   │   └── ui/                           # Shared UI components
│   │
│   ├── lib/                              # Utilities & DB
│   │   ├── db.ts                         # DB connection + interfaces
│   │   ├── env.ts                        # Environment variable exports
│   │   └── models/                       # Mongoose models
│   │       ├── User.ts
│   │       ├── Product.ts
│   │       ├── Category.ts
│   │       ├── Order.ts
│   │       └── Review.ts
│   │
│   ├── redux/                            # Redux Store
│   │   ├── Store.tsx
│   │   ├── CartSlice.tsx
│   │   ├── WishListSlice.tsx
│   │   ├── AuthSlice.tsx
│   │   └── Provider.tsx
│   │
│   └── data/                             # Static data files
│
├── public/                               # Static assets
├── orders.json                           # Local orders snapshot
├── .env.local                            # Environment variables
├── package.json
├── tsconfig.json
├── tailwind.config.ts
└── next.config.ts
```

---

## 🚀 Getting Started

### Prerequisites

- **Node.js** 18.0 or higher
- **MongoDB** database (Atlas or local)
- **Groq API key** (for AI descriptions)
- **Gmail** account (for email notifications)
- **Stripe** account (for card payments)
- **PayPal** developer account (for PayPal payments)

### Installation

1. **Clone the repository**

   ```bash
   git clone <your-repo-url>
   cd printnest
   ```

2. **Install dependencies**

   ```bash
   npm install
   ```

3. **Create `.env.local`** (see [Environment Variables](#-environment-variables))

4. **Run development server**

   ```bash
   npm run dev
   ```

5. **Open in browser**

   ```
   http://localhost:3000
   ```

### Scripts

| Command         | Description              |
| --------------- | ------------------------ |
| `npm run dev`   | Start development server |
| `npm run build` | Build for production     |
| `npm start`     | Start production server  |
| `npm run lint`  | Run ESLint               |

---

## 🔐 Environment Variables

Create `.env.local` in the project root:

```env
# MongoDB
MONGODB_URI=mongodb+srv://<user>:<password>@cluster.mongodb.net/printnest

# JWT Authentication
JWT_SECRET=your-secret-key-minimum-32-characters

# Email (Gmail SMTP)
EMAIL_USER=your-email@gmail.com
EMAIL_PASS=your-gmail-app-password

# AI Descriptions (Groq)
GROQ_API_KEY=your-groq-api-key

# App URL (used in payment redirect URLs)
NEXT_PUBLIC_APP_URL=http://localhost:3000

# Stripe
NEXT_PUBLIC_STRIPE_PUBLISHABLE_KEY=pk_test_...
STRIPE_SECRET_KEY=sk_test_...

# PayPal (Sandbox)
PAYPAL_CLIENT_ID=your-paypal-client-id
PAYPAL_SECRET=your-paypal-secret
```

> **Required:** `MONGODB_URI` and `JWT_SECRET` — the app will throw on startup if missing.

### Getting API Keys

| Service                | URL                                                                            |
| ---------------------- | ------------------------------------------------------------------------------ |
| **MongoDB Atlas**      | [cloud.mongodb.com](https://cloud.mongodb.com)                                 |
| **Groq API**           | [console.groq.com](https://console.groq.com)                                   |
| **Gmail App Password** | [myaccount.google.com/apppasswords](https://myaccount.google.com/apppasswords) |
| **Stripe Dashboard**   | [dashboard.stripe.com/apikeys](https://dashboard.stripe.com/apikeys)           |
| **PayPal Developer**   | [developer.paypal.com/dashboard](https://developer.paypal.com/dashboard)       |

---

## 📡 API Routes

### Auth Routes

| Endpoint           | Method | Description                    |
| ------------------ | ------ | ------------------------------ |
| `/api/auth/signup` | `POST` | Register new user              |
| `/api/auth/login`  | `POST` | Login and receive JWT cookie   |
| `/api/auth/me`     | `GET`  | Get current authenticated user |
| `/api/auth/logout` | `POST` | Clear auth cookie              |

### Public Routes

| Endpoint                  | Method | Description                   |
| ------------------------- | ------ | ----------------------------- |
| `/api/public/content`     | `GET`  | All site content from db.json |
| `/api/public/place-order` | `POST` | Submit order + send emails    |
| `/api/public/orders`      | `GET`  | Get orders for current user   |
| `/api/public/reviews`     | `GET`  | Get product reviews           |
| `/api/public/reviews`     | `POST` | Submit a new review           |

### Payment Routes

| Endpoint               | Method | Description                                            |
| ---------------------- | ------ | ------------------------------------------------------ |
| `/api/stripe/checkout` | `POST` | Create Stripe Checkout Session, returns redirect `url` |
| `/api/paypal/checkout` | `POST` | Create PayPal order, returns PayPal approval `url`     |

### Admin Routes (🔒 Admin only)

| Endpoint                     | Method                    | Description                     |
| ---------------------------- | ------------------------- | ------------------------------- |
| `/api/admin/stats`           | `GET`                     | Dashboard analytics & charts    |
| `/api/admin/products`        | `GET` / `POST` / `DELETE` | Manage product catalog          |
| `/api/admin/categories`      | `GET` / `POST`            | List or create categories       |
| `/api/admin/categories/[id]` | `DELETE` / `PATCH`        | Edit or delete a category       |
| `/api/admin/orders`          | `GET` / `PATCH`           | View and update orders          |
| `/api/admin/users`           | `GET`                     | List all users                  |
| `/api/admin/users/[id]`      | `DELETE` / `PATCH`        | Delete or promote users         |
| `/api/admin/ai-description`  | `POST`                    | Generate AI product description |
| `/api/upload`                | `POST`                    | Upload product image            |

---

## 🗄️ Database & Models

The app uses **MongoDB** with Mongoose. Connection is cached globally for serverless efficiency.

### Models

#### User

```typescript
{ name, email, password, phone, address, city, country, cart[], wishlist[], isAdmin }
```

#### Product

```typescript
{
  (id, title, price, oldPrice, image, badge, printText, createdAt, updatedAt);
}
```

#### Category

```typescript
{
  (name, slug, image, createdAt, updatedAt);
}
```

#### Order

```typescript
{ id, userId, date, status, total, items[], customer }
```

#### Review

```typescript
{
  (productId, userId, userName, userImage, rating, comment, date, createdAt);
}
```

> The user matching the `EMAIL_USER` env var is automatically granted admin on each DB connection.

---

## 🏪 Redux Store

### Cart (`CartSlice.tsx`)

```typescript
// State
{ cartItems: CartItem[], totalQuantity: number, totalAmount: number }

// Actions
addToCart(item)         // Add or increment quantity
removeFromCart(id)      // Decrement by 1
deleteItem(id)          // Remove entirely
initializeCart(state)   // Restore from localStorage
```

### Wishlist (`WishListSlice.tsx`)

```typescript
// State
{ items: WishlistItem[] }

// Actions
toggleWishlist(item)    // Add or remove
```

### Auth (`AuthSlice.tsx`)

```typescript
// State
{ isAuthenticated: boolean, user: User | null, token: string | null }

// Actions
loginSuccess({ user, token })
logout()
```

---

## 🛠️ Admin Panel

Access at `/admin/dashboard` (requires admin account).

### Dashboard Analytics

- **KPI Cards** — Total users, orders, revenue, reviews
- **Revenue Chart** — Daily revenue over a date range
- **Order Trend** — Orders per day
- **Top Products** — Best-selling items
- **Category Sales** — Revenue breakdown by category
- **Order Velocity** — Orders by hour of day
- **Review Stats** — Rating distribution and sentiment analysis

### Product Management

- Add products with title, price, image, and badge
- **AI description generator** — auto-generate from title using Groq
- Edit and delete existing products
- Image upload support

### Category Management

- Create, edit, and delete product categories
- Each category has a `name`, `slug`, and optional `image`
- Categories are stored in MongoDB and used on the shop/category pages

### User & Order Management

- View all users with order counts
- Promote/demote admin status
- Delete users
- Update order statuses

---

## 📄 Pages & Routes

### Public Pages

| Route              | Description                                          |
| ------------------ | ---------------------------------------------------- |
| `/`                | Home (Hero, Products, Categories, Blog, etc.)        |
| `/shop`            | All products grid                                    |
| `/product/[slug]`  | Product detail with reviews                          |
| `/category/[slug]` | Category-filtered products                           |
| `/blog/[slug]`     | Blog post                                            |
| `/cart`            | Shopping cart                                        |
| `/wishlist`        | Saved products                                       |
| `/login`           | Login                                                |
| `/signup`          | Registration                                         |
| `/thank-you`       | Order confirmation (Stripe + PayPal redirect target) |

### Protected Pages

| Route       | Description                                     |
| ----------- | ----------------------------------------------- |
| `/account`  | User dashboard + order history                  |
| `/checkout` | Checkout with Stripe and PayPal payment options |

### Admin Pages

| Route              | Description             |
| ------------------ | ----------------------- |
| `/admin/dashboard` | Analytics & data charts |
| `/admin/products`  | Product management      |
| `/admin/reviews`   | Review moderation       |

### Dynamic Route Slugs

```
"Print Mug"  →  /product/print-mug
"T-shirts"   →  /category/t-shirts
```

---

## 🌐 Deployment

### Vercel (Recommended)

1. Push code to GitHub
2. Import project on [vercel.com](https://vercel.com)
3. Add **all** environment variables in the Vercel dashboard (including Stripe and PayPal keys)
4. Deploy — Next.js is detected automatically

> ⚠️ Vercel's filesystem is ephemeral. All data **must** be stored in MongoDB.

### Other Platforms

Works on any Node.js 18+ host (Railway, Render, DigitalOcean, AWS):

```bash
npm run build
npm start
```

---

## 🤝 Contributing

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/my-feature`)
3. Commit your changes (`git commit -m 'feat: add my feature'`)
4. Push to the branch (`git push origin feature/my-feature`)
5. Open a Pull Request

---

## 📝 License

This project is open source and available under the [MIT License](LICENSE).

---

<p align="center"><strong>Made with ❤️ for the printing community</strong> 🖨️✨</p>
