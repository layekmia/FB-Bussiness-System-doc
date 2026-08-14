<div align="center">

# 🛍️ F-Commerce Platform
### Master Project Documentation

![Next.js](https://img.shields.io/badge/Next.js-000000?style=for-the-badge&logo=next.js&logoColor=white)
![TypeScript](https://img.shields.io/badge/TypeScript-3178C6?style=for-the-badge&logo=typescript&logoColor=white)
![PostgreSQL](https://img.shields.io/badge/PostgreSQL-4169E1?style=for-the-badge&logo=postgresql&logoColor=white)
![Prisma](https://img.shields.io/badge/Prisma-2D3748?style=for-the-badge&logo=prisma&logoColor=white)
![Tailwind](https://img.shields.io/badge/TailwindCSS-06B6D4?style=for-the-badge&logo=tailwindcss&logoColor=white)
![shadcn/ui](https://img.shields.io/badge/shadcn%2Fui-000000?style=for-the-badge&logo=shadcnui&logoColor=white)

*A complete eCommerce operating platform for Bangladeshi Facebook-based & COD businesses*

</div>

---

## 📑 Table of Contents

- [🧭 01. Project Overview](#-01-project-overview)
- [📋 Master Feature List](#-master-feature-list)
- [🛠️ Feature Detailed Breakdown](#️-feature-detailed-breakdown)
  - [⚙️ Foundation & Technical Setup](#️-01-foundation--technical-setup-1)
  - [🗄️ Database Schema (Prisma)](#️-08-database-schema-prisma)
  - [🧩 Recommended Packages & Workflow](#-09-recommended-packages--workflow--per-module)
  - [🛍️ Customer-Facing Storefront](#️-02-customer-facing-storefront)
  - [🔐 Admin Dashboard](#-admin-dashboard-)
  - [🎯 Landing Page System](#-landing-page-system)
  - [🛡️ Fake Order Prevention](#️-fake-order-prevention)
  - [🚚 Courier Automation](#-courier-automation)

---

## 🧭 01. Project Overview

F-Commerce Platform is a complete eCommerce operating platform built for Bangladeshi online businesses, especially Facebook-based and COD businesses.

It will bring store management, product management, orders, customers, inventory, landing pages, fraud prevention, courier automation, and notifications into one centralized platform.

The main purpose is to reduce manual work, simplify daily eCommerce operations, and help businesses manage their entire sales process from one place.

The platform will be modular, scalable, customizable, and designed with client ownership and flexibility in mind.

### 🔄 Core Flow

> **Traffic** → **Landing/Store** → **Order** → **Verification** → **Fraud Check** → **Courier** → **Delivery** → **Customer History**


---

# 📋 Master Feature List

## ⚙️ 01. Foundation & Technical Setup

1. **Project Setup & Environment** — Project structure, environment configuration এবং development setup।
2. **Database Schema** — Users, products, variants, categories, orders, customers ইত্যাদির database structure।
3. **Authentication & Authorization** — Customer/Admin login, signup এবং role-based access control।
4. **API Structure** — Backend API structure এবং consistent API patterns তৈরি করা।
5. **Error Handling & Logging** — System-wide error handling এবং logging।
6. **Basic Security** — Input validation, rate limiting এবং basic security protection।
7. **Image Optimization & CDN** — Image upload, optimization এবং fast delivery setup।

---

---

# 🛠️ Feature Detailed Breakdown

## ⚙️ 01. Foundation & Technical Setup

### 01. Project Setup & Environment

---

### 1. Tech Stack & Dependencies

- Next.js
- React
- TypeScript
- Tailwind CSS
- shadcn/ui
- Lucide React
- PostgreSQL
- Prisma ORM
- Better Auth
- Zod
- TanStack Query
- React Hook Form
- zustand
- Other necessary production dependencies

> অপ্রয়োজনীয় dependency ব্যবহার করা হবে না। প্রয়োজন অনুযায়ী নতুন dependency যোগ করা যেতে পারে।

---

### 2. Project Folder Structure

Project-এর folder structure শুরুতেই নির্ধারণ ও final করা হবে। Structure এমন হবে যাতে application, UI, database, authentication, API এবং reusable logic আলাদা ও organized থাকে।

#### Root Structure

```text
project-root/
├── app/
├── components/
├── lib/
├── hooks/
├── types/
├── validations/
├── prisma/
├── public/
├── config/
├── providers/
├── services/
├── constants/
├── scripts/
├── tests/
├── .env
├── .env.example
├── package.json
├── pnpm-lock.yaml
├── prisma.config.ts
├── next.config.ts
├── tsconfig.json
└── components.json
```

### Folder Responsibilities

**`app/`**  
Application routes, pages, layouts, loading/error states এবং API routes।

**`components/`**  
Reusable UI components এবং application-specific components।

**`lib/`**  
Core utilities, database client, authentication helpers এবং অন্যান্য shared logic।

**`hooks/`**  
Reusable React hooks।

**`types/`**  
Shared TypeScript types এবং interfaces।

**`validations/`**  
Zod schemas এবং input validation rules।

**`prisma/`**  
Prisma schema, migrations এবং seed-related files।

**`public/`**  
Static assets।

**`config/`**  
Application configuration এবং centralized settings।

**`providers/`**  
Global React/context providers।

**`services/`**  
External services এবং business-related service integrations।

**`constants/`**  
Shared constants এবং fixed application values।

**`scripts/`**  
Development/maintenance-এর প্রয়োজনীয় scripts।

**`tests/`**  
Automated tests。


### Structure Rules

- প্রতিটি folder-এর নির্দিষ্ট responsibility থাকবে।
- একই ধরনের logic একাধিক জায়গায় duplicate করা যাবে না।
- অপ্রয়োজনীয় folder তৈরি করা হবে না।
- কোনো folder future requirement-এর কথা ভেবে অকারণে তৈরি করা হবে না।
- Project বড় হওয়ার সাথে প্রয়োজন অনুযায়ী existing structure-এর ভিতরে subfolder তৈরি করা যাবে।
- Major architectural change করার আগে documentation update করতে হবে।

> **Final Rule:** Development শুরু করার আগে এই folder structure review করে lock করা হবে। পরবর্তীতে নতুন requirement এলে আগে documentation update হবে, তারপর structure পরিবর্তন করা হবে।


---

## 03. Environment Configuration

Project-এর জন্য প্রয়োজনীয় environment variables এবং credentials:

- `DATABASE_URL`
- `BETTER_AUTH_SECRET`
- `BETTER_AUTH_URL`
- Payment gateway credentials
- Courier API credentials
- Email/SMS credentials
- Image storage/CDN credentials
- অন্যান্য third-party service credentials

> সব secret `.env`-এ থাকবে এবং `.env.example`-এ শুধু variable names থাকবে।


---

## 04. Database Setup

- PostgreSQL database setup
- Prisma ORM configuration
- Database connection
- Prisma Client setup
- Migration system
- Database seed setup যেখানে প্রয়োজন
- Development ও production database configuration

> Actual database models, relations, indexes এবং constraints **02. Database Schema**-এ বিস্তারিতভাবে document করা হবে।


---

## 05. Authentication Setup

**Better Auth** সম্পূর্ণ authentication system-এর foundation হিসেবে configure করা হবে।

এতে পরবর্তীতে প্রয়োজন অনুযায়ী:

- Customer authentication
- Admin authentication
- Role-based access

implement করার foundation থাকবে।

> Actual authentication flow, roles এবং permissions **03. Authentication & Authorization**-এ বিস্তারিতভাবে document করা হবে।


---

## 06. Core Application Setup

- Global styling
- shadcn/ui setup
- Reusable UI foundation
- Form handling
- Validation system
- API communication setup
- Error handling foundation
- Image handling
- Basic security configuration


---

## 07. Setup Completion Criteria

এই module complete ধরা হবে যখন:

- [ ] সব required dependencies installed এবং configured
- [ ] Project successfully runs locally
- [ ] PostgreSQL successfully connected
- [ ] Prisma successfully connected
- [ ] Migration system working
- [ ] Better Auth configured
- [ ] Environment configuration ready
- [ ] Required core libraries configured
- [ ] Final folder structure established
- [ ] Project foundation পরবর্তী feature development-এর জন্য ready

---

## 🗄️ 08. Database Schema (Prisma)

> এই schema পুরো project-এর সব feature (catalog, cart, order, coupon, review, fraud prevention, courier, landing page, CMS, notification, settings) cover করে। এটাই `prisma/schema.prisma`-এর base version — coding agent সরাসরি এই models দিয়ে শুরু করতে পারবে, প্রয়োজনে ছোট field যোগ করা যাবে কিন্তু structure/relations এটাই মূল ভিত্তি হিসেবে থাকবে।

```prisma
generator client {
  provider = "prisma-client-js"
}

datasource db {
  provider = "postgresql"
  url      = env("DATABASE_URL")
}

// ================= AUTH (Better Auth managed core + role extension) =================

model User {
  id            String    @id @default(cuid())
  name          String
  email         String?   @unique
  emailVerified Boolean   @default(false)
  phone         String?   @unique
  phoneVerified Boolean   @default(false)
  image         String?
  role          Role      @default(CUSTOMER)
  createdAt     DateTime  @default(now())
  updatedAt     DateTime  @updatedAt

  sessions      Session[]
  accounts      Account[]
  addresses     Address[]
  cartItems     CartItem[]
  wishlistItems WishlistItem[]
  orders        Order[]
  reviews       Review[]
}

enum Role {
  CUSTOMER
  ADMIN
  STAFF
}

model Session {
  id        String   @id @default(cuid())
  userId    String
  token     String   @unique
  expiresAt DateTime
  ipAddress String?
  userAgent String?
  user      User     @relation(fields: [userId], references: [id])
}

model Account {
  id                String  @id @default(cuid())
  userId            String
  providerId        String
  accountId         String
  passwordHash      String?
  user              User    @relation(fields: [userId], references: [id])
}

model Verification {
  id         String   @id @default(cuid())
  identifier String
  value      String
  expiresAt  DateTime
}

// ================= CATALOG =================

model Category {
  id          String     @id @default(cuid())
  name        String
  slug        String     @unique
  image       String?
  description String?
  parentId    String?
  parent      Category?  @relation("CategoryTree", fields: [parentId], references: [id])
  children    Category[] @relation("CategoryTree")
  products    Product[]
  createdAt   DateTime   @default(now())
}

model Brand {
  id       String    @id @default(cuid())
  name     String
  slug     String    @unique
  image    String?
  products Product[]
}

model Product {
  id             String           @id @default(cuid())
  name           String
  slug           String           @unique
  shortDesc      String?
  description    String?
  specifications Json?
  features       Json?
  price          Decimal
  oldPrice       Decimal?
  sku            String?          @unique
  stock          Int              @default(0)
  status         ProductStatus    @default(ACTIVE)
  categoryId     String
  brandId        String?
  videoUrl       String?
  ratingAvg      Float            @default(0)
  reviewCount    Int              @default(0)
  isFeatured     Boolean          @default(false)
  isNewArrival   Boolean          @default(true)
  createdAt      DateTime         @default(now())
  updatedAt      DateTime         @updatedAt

  category       Category         @relation(fields: [categoryId], references: [id])
  brand          Brand?           @relation(fields: [brandId], references: [id])
  images         ProductImage[]
  variants       ProductVariant[]
  reviews        Review[]
  cartItems      CartItem[]
  wishlistItems  WishlistItem[]
  orderItems     OrderItem[]
}

enum ProductStatus {
  ACTIVE
  DRAFT
  OUT_OF_STOCK
  ARCHIVED
}

model ProductImage {
  id        String  @id @default(cuid())
  productId String
  url       String
  altText   String?
  order     Int     @default(0)
  product   Product @relation(fields: [productId], references: [id])
}

model ProductVariant {
  id            String           @id @default(cuid())
  productId     String
  size          String?
  color         String?
  sku           String?          @unique
  stock         Int              @default(0)
  priceOverride Decimal?
  product       Product          @relation(fields: [productId], references: [id])
  cartItems     CartItem[]
  orderItems    OrderItem[]
}

// ================= CUSTOMER DATA =================

model Address {
  id            String      @id @default(cuid())
  userId        String
  recipientName String
  phone         String
  division      String
  district      String
  area          String
  fullAddress   String
  type          AddressType @default(HOME)
  isDefault     Boolean     @default(false)
  user          User        @relation(fields: [userId], references: [id])
  orders        Order[]
}

enum AddressType {
  HOME
  OFFICE
  OTHER
}

model WishlistItem {
  id        String   @id @default(cuid())
  userId    String
  productId String
  createdAt DateTime @default(now())
  user      User     @relation(fields: [userId], references: [id])
  product   Product  @relation(fields: [productId], references: [id])

  @@unique([userId, productId])
}

model CartItem {
  id        String          @id @default(cuid())
  userId    String?
  sessionId String?
  productId String
  variantId String?
  quantity  Int             @default(1)
  createdAt DateTime        @default(now())
  user      User?           @relation(fields: [userId], references: [id])
  product   Product         @relation(fields: [productId], references: [id])
  variant   ProductVariant? @relation(fields: [variantId], references: [id])
}

// ================= ORDERS =================

model Order {
  id             String        @id @default(cuid())
  orderNumber    String        @unique
  userId         String?
  guestName      String?
  guestPhone     String?
  guestEmail     String?
  addressId      String?
  subtotal       Decimal
  discountAmount Decimal       @default(0)
  deliveryCharge Decimal       @default(0)
  totalAmount    Decimal
  couponId       String?
  landingPageId  String?
  status         OrderStatus   @default(PENDING)
  paymentMethod  PaymentMethod
  paymentStatus  PaymentStatus @default(UNPAID)
  notes          String?
  createdAt      DateTime      @default(now())
  updatedAt      DateTime      @updatedAt

  user           User?               @relation(fields: [userId], references: [id])
  address        Address?            @relation(fields: [addressId], references: [id])
  coupon         Coupon?             @relation(fields: [couponId], references: [id])
  landingPage    LandingPage?        @relation(fields: [landingPageId], references: [id])
  items          OrderItem[]
  statusHistory  OrderStatusHistory[]
  riskFlag       OrderRiskFlag?
  shipment       Shipment?
}

enum OrderStatus {
  PENDING
  CONFIRMED
  PROCESSING
  SHIPPED
  OUT_FOR_DELIVERY
  DELIVERED
  CANCELLED
  RETURNED
}

enum PaymentMethod {
  COD
  ONLINE
}

enum PaymentStatus {
  UNPAID
  PAID
  FAILED
  REFUNDED
}

model OrderItem {
  id           String          @id @default(cuid())
  orderId      String
  productId    String
  variantId    String?
  productName  String
  variantLabel String?
  quantity     Int
  price        Decimal
  order        Order           @relation(fields: [orderId], references: [id])
  product      Product         @relation(fields: [productId], references: [id])
  variant      ProductVariant? @relation(fields: [variantId], references: [id])
}

model OrderStatusHistory {
  id        String      @id @default(cuid())
  orderId   String
  status    OrderStatus
  note      String?
  createdAt DateTime    @default(now())
  order     Order       @relation(fields: [orderId], references: [id])
}

model Coupon {
  id             String     @id @default(cuid())
  code           String     @unique
  type           CouponType
  value          Decimal
  minOrderAmount Decimal?
  usageLimit     Int?
  usedCount      Int        @default(0)
  expiresAt      DateTime?
  isActive       Boolean    @default(true)
  orders         Order[]
}

enum CouponType {
  PERCENTAGE
  FIXED
}

// ================= REVIEWS =================

model Review {
  id                 String       @id @default(cuid())
  productId          String
  userId             String
  rating             Int
  title              String?
  comment            String?
  images             Json?
  status             ReviewStatus @default(PENDING)
  isVerifiedPurchase Boolean      @default(false)
  createdAt          DateTime     @default(now())
  product            Product      @relation(fields: [productId], references: [id])
  user               User         @relation(fields: [userId], references: [id])

  @@unique([productId, userId])
}

enum ReviewStatus {
  PENDING
  APPROVED
  HIDDEN
}

// ================= FAKE ORDER PREVENTION =================

model RiskRule {
  id        String  @id @default(cuid())
  name      String
  field     String
  condition String
  weight    Int
  isActive  Boolean @default(true)
}

model OrderRiskFlag {
  id          String           @id @default(cuid())
  orderId     String           @unique
  riskScore   Int
  riskLevel   RiskLevel
  reasons     Json
  status      RiskReviewStatus @default(PENDING)
  reviewedBy  String?
  reviewNotes String?
  createdAt   DateTime         @default(now())
  order       Order            @relation(fields: [orderId], references: [id])
}

enum RiskLevel {
  LOW
  MEDIUM
  HIGH
}

enum RiskReviewStatus {
  PENDING
  APPROVED
  REJECTED
}

// ================= COURIER AUTOMATION =================

model CourierAccount {
  id          String     @id @default(cuid())
  courierName String
  apiKey      String
  apiSecret   String?
  status      String     @default("ACTIVE")
  isDefault   Boolean    @default(false)
  shipments   Shipment[]
}

model Shipment {
  id                String         @id @default(cuid())
  orderId           String         @unique
  courierAccountId  String
  consignmentId     String?
  bookingStatus     String         @default("PENDING")
  trackingStatus    String?
  trackingUrl       String?
  createdAt         DateTime       @default(now())
  order             Order          @relation(fields: [orderId], references: [id])
  courierAccount    CourierAccount @relation(fields: [courierAccountId], references: [id])
}

// ================= LANDING PAGE SYSTEM =================

model LandingPageTemplate {
  id           String        @id @default(cuid())
  name         String
  previewImage String?
  landingPages LandingPage[]
}

model LandingPage {
  id         String     @id @default(cuid())
  name       String
  slug       String     @unique
  templateId String
  productId  String?
  status     PageStatus @default(DRAFT)
  createdAt  DateTime   @default(now())
  updatedAt  DateTime   @updatedAt

  template   LandingPageTemplate  @relation(fields: [templateId], references: [id])
  sections   LandingPageSection[]
  orders     Order[]
}

enum PageStatus {
  DRAFT
  PUBLISHED
}

model LandingPageSection {
  id            String      @id @default(cuid())
  landingPageId String
  sectionType   String
  order         Int
  isEnabled     Boolean     @default(true)
  content       Json
  landingPage   LandingPage @relation(fields: [landingPageId], references: [id])
}

// ================= APPEARANCE / CMS =================

model Banner {
  id       String  @id @default(cuid())
  image    String
  link     String?
  position String
  order    Int     @default(0)
  isActive Boolean @default(true)
}

model MenuItem {
  id        String  @id @default(cuid())
  label     String
  url       String
  location  String
  order     Int     @default(0)
  parentId  String?
  isVisible Boolean @default(true)
}

model CmsPage {
  id      String @id @default(cuid())
  title   String
  slug    String @unique
  content String
}

// ================= NOTIFICATIONS =================

model NotificationTemplate {
  id      String @id @default(cuid())
  type    String
  channel String
  subject String?
  body    String
}

model NotificationLog {
  id        String   @id @default(cuid())
  type      String
  channel   String
  recipient String
  status    String
  sentAt    DateTime @default(now())
}

// ================= STORE SETTINGS =================

model StoreSetting {
  id             String   @id @default(cuid())
  storeName      String
  currency       String   @default("BDT")
  shippingCharge Decimal  @default(0)
  taxRate        Decimal  @default(0)
  socialLinks    Json?
  seoTitle       String?
  seoDescription String?
}
```

---

---

## 🧩 09. Recommended Packages & Workflow — Per Module

> Foundation section-এ যে core stack ঠিক করা হয়েছে (Next.js, Prisma, Better Auth, Zod, TanStack Query, React Hook Form, Zustand, shadcn/ui) সেটার উপর ভিত্তি করে প্রতিটা module কোন package/pattern দিয়ে implement হবে তার guide নিচে দেওয়া হলো — coding agent এই mapping অনুসরণ করে সরাসরি কাজ শুরু করতে পারবে।

| Module | Package / Approach | Workflow Note |
|---|---|---|
| Auth (customer + admin, role-based) | **Better Auth** | Role field (`CUSTOMER`/`ADMIN`/`STAFF`) দিয়ে middleware-এ route protect করা হবে; `app/(customer)` ও `app/(admin)` route groups আলাদা layout দিয়ে গার্ড করা হবে। |
| Forms (checkout, product, address, review, coupon) | **React Hook Form + Zod** | প্রতিটা form-এর Zod schema `validations/` folder-এ থাকবে, `zodResolver` দিয়ে RHF-এর সাথে যুক্ত হবে। |
| Server data fetching/caching (product list, orders, dashboard stats) | **TanStack Query** (client) + **Next.js Server Components** (initial load) | প্রথম page load SSR দিয়ে, পরের interaction (filter/sort/pagination) TanStack Query দিয়ে client-side। |
| Cart & guest wishlist state | **Zustand** | Guest state local persist (`localStorage` sync middleware); login হলে server-এর সাথে merge করে DB-তে সরানো হবে (`CartItem`/`WishlistItem` table)। |
| UI components | **shadcn/ui** | Cart drawer → `Sheet`; profile menu → `DropdownMenu`; admin tables → `Table` + `DataTable` pattern; search autocomplete → `Command` (cmdk); filters → `Accordion`/`Checkbox`। |
| Image upload & delivery | **UploadThing** বা **Cloudflare R2** + `next/image` | Product image, review photo, banner সব একই upload service দিয়ে হবে, URL DB-তে string হিসেবে save। |
| Payment gateway | **SSLCommerz** SDK/REST | `services/payment/sslcommerz.ts`-এ wrapper রাখা হবে; webhook দিয়ে `paymentStatus` update। |
| Courier integration | **Pathao Courier API + Steadfast API** | `services/courier/`-এ প্রতিটা courier-এর জন্য আলাদা adapter (common interface দিয়ে), booking/tracking/status-sync সব এখান থেকে call হবে। |
| Fake order risk check | Custom rule engine (কোনো external package লাগবে না) | `services/fraud/riskEngine.ts`-এ `RiskRule` table থেকে rule পড়ে score calculate করবে; order create হওয়ার সময় সিঙ্ক্রোনাসভাবে চলবে। |
| Notifications (email/SMS) | **Resend** (email) + local BD SMS gateway API (SMS) | `services/notification/`-এ template render করে পাঠানো হবে, `NotificationLog`-এ history save। |
| Landing page builder (template-based) | JSON-driven section content (`LandingPageSection.content: Json`) + dynamic route `app/lp/[slug]/page.tsx` | Drag-drop builder না — section list থেকে enable/disable + form দিয়ে content edit, render-টা predefined component per `sectionType` দিয়ে হবে। |
| Search autocomplete | TanStack Query (debounced) + Postgres `ILIKE`/full-text search বা Prisma `contains` | ছোট থেকে মাঝারি catalog-এর জন্য এটাই যথেষ্ট, বড় হলে পরে Meilisearch/Algolia যোগ করা যাবে। |

---

---

## 🛍️ 02. Customer-Facing Storefront

> **🔧 Implementation Guide**
> এই পুরো module Next.js App Router-এর public route group-এ থাকবে। Data fetch মূলত Server Component দিয়ে (SEO-friendly), interactive অংশ (cart, wishlist, filter) Client Component + TanStack Query/Zustand দিয়ে। UI shadcn/ui component দিয়ে গড়া হবে, form-guলো React Hook Form + Zod দিয়ে validate হবে।

#### Homepage: 
    1. Header / Navigation 
        01. Logo
        02. Navigation menu 
            Home , Shop , Categories , Offers/Best sellers , Track order , About us , contact
        03. Search Bar
            It will be like ghorerbazar search bar.
        04. Wishlist (Icon)
        05. Cart (Icon)
        06. User Profile (Icon) or Login/Signup (Button)
            6.1 Customers
                6.1 Profile 
                6.1.1 My Orders
                6.1.2 My Profile
                6.1.4 Address book
                6.1.3 Wishlist
                6.1.6 Logout
            6.2 Admin 
                shop name
                email 
                6.2.0 Dashboard - Admin dashboard 
                6.2.4 Logout
    2. Hero Section
        -------------
    3. Featured Categoires section
    4. Featured Product Section
    5. Promotional Banner (Optional)
    6. New Arrivals
    7. Best Sellers
    8. Testimonial
    9. Newsletter Subscription (Optional)
    10. Footer 
        ----------
        Shop Name
        Customer care
        Contact Info
        Social Links
        Policy 
        All necessary things that's should be in the footer.
    
## Shop / Collections Page

### 1. Page Header
- Page title
- Breadcrumb

### 2. Category / Collection Navigation
- All Products
- Product categories
- Selected collection

### 3. Filter
- Price range
- Category
- Brand
- Size
- Color
- Availability

### 4. Sort
- Featured
- Newest
- Price: Low to High
- Price: High to Low
- Best Selling

### 5. Product Listing
- Product image
- Product name
- Price
- Discount/old price
- Rating
- Wishlist
- Add to Cart

### 6. Pagination
- Page navigation
- Total/result count

### 7. Empty State
- No products found message
- Clear filters option


## Product Details Page
### 1. Product Information
- Product images/gallery
- Product name
- Rating & review count
- Short description
- Price
- Discount/old price
- Stock status

### 2. Product Options
- Size
- Color
- Other variants
- Quantity selector

### 3. Purchase Actions
- Add to Cart
- Buy Now
    Also will be add to cart and automatically redirect to the checkout page with this cart products.
- Add to Wishlist
- whatsapp message
- call for Order

### 4. Product Details
- Full description
- Specifications
- Features
- Product video (if available)

### 6. Trust Information
- Secure payment
- Return/Refund policy
- Customer support

### 7. Reviews & Ratings
- Average rating
- Rating breakdown
- Customer reviews
- Customer review images (if available)

### 8. Related Products
- Related products
- Recently viewed products
- Customers also bought

### 9. Product Sharing
- Copy product link
- Social sharing

### 10. Mobile Experience
- Sticky Add to Cart / Buy Now actions


## Wishlist Page

### 1. Wishlist Products
- Product image
- Product name
- Price
- Discount/old price
- Stock status
- Rating

### 2. Product Actions
- Add to Cart
- Remove from Wishlist
- View Product

### 3. Wishlist Management
- Total saved products
- Clear Wishlist
- Move product to Cart

### 4. Empty Wishlist
- Empty wishlist message
- Continue Shopping button

### 5. Wishlist Sync
- Wishlist sync for logged-in customers
- Guest wishlist stored locally
- Guest wishlist merge after login

## 05. Cart & Checkout ==========================

## Add to Cart

### 1. Add Product
- Add product to cart
- Add selected variant
- Add selected quantity
- Validate product/variant availability

### 2. Cart Update
- Increase quantity
- Decrease quantity
- Remove product
- Update quantity
- Recalculate subtotal automatically

### 3. Cart Drawer
- Product image
- Product name
- Selected variant
- Quantity
- Price
- Subtotal
- View Cart button
- Checkout button

### 4. Cart Validation
- Stock availability check
- Price update check
- Product availability check
- Variant availability check

### 5. Cart Persistence
- Guest cart stored locally
- Logged-in cart stored with customer account
- Guest cart merge after login

### 6. Cart Feedback
- Product added confirmation
- Out-of-stock message
- Quantity limit message

### 23. Coupon / Discount

- Discount code apply
- Percentage discount
- Fixed amount discount
- Coupon expiry
- Usage limit
- Minimum order amount
- Coupon validation
- Remove applied coupon

### 24. Checkout

- Customer information
- Phone number
- Delivery address
- Saved address selection
- Shipping method
- Delivery charge
- Order summary
- Coupon/discount summary
- Final payable amount
- Order notes
- Place Order


### 25. Payment Methods

- Cash on Delivery (COD)
- Online payment
- Payment method selection
- Payment status
- Payment verification
- Failed payment handling


### 26. Order Confirmation page

- Order success message
- Order number
- Order summary
- Customer information
- Delivery address
- Payment method
- Total amount
- Estimated delivery information
- View Order button
- Continue Shopping button

## My Orders Page

### 1. Order List
- Order number
- Order date
- Product summary
- Total amount
- Payment status
- Order status

### 2. Order Status
- Pending
- Confirmed
- Processing
- Shipped
- Delivered
- Cancelled
- Returned

### 3. Order Actions
- View Order
- Track Order
- Cancel Order (if eligible)
- Reorder

### 4. Order Details
- Product details
- Quantity
- Price
- Delivery address
- Payment method
- Order summary
- Order timeline

### 5. Order Filtering
- All Orders
- Active Orders
- Delivered
- Cancelled
- Returned

### 6. Empty State
- No orders message
- Continue Shopping button

## Order Tracking Page

### 1. Page Access
- Homepage navigation-এ Track Order menu
- Login ছাড়াই order tracking
- Direct URL দিয়ে access করা যাবে

### 2. Order Search
- Order number input
- Search / Track Order button
- Order number validation
- Invalid order number message
- Empty input validation

### 3. Empty State
Page open করলে কোনো order information দেখাবে না।

### 4. Order Tracking Result

Valid order number দিলে:

- Order number
- Order date
- Customer name
- Product summary
- Total amount
- Payment status
- Current order status

### 5. Order Status Timeline

Order-এর progress visual timeline আকারে দেখাবে:

- Order Placed
- Confirmed
- Processing
- Shipped
- Out for Delivery
- Delivered

প্রতিটি status-এর:
- Status name
- Date/time
- Current status indicator

### 7. Order Summary
- Ordered products
- Product quantity
- Product price
- Delivery charge
- Discount
- Total amount

### 8. Order Status Messages
বর্তমান status অনুযায়ী customer-কে short informative message দেখানো হবে।

### 9. Privacy & Security
- Login ছাড়া শুধু order number দিয়ে প্রয়োজনীয় tracking information দেখানো হবে।
- Sensitive customer information প্রকাশ করা হবে না।
- Invalid বা non-existent order number-এর ক্ষেত্রে order information দেখানো হবে না।

### 10. Mobile Experience
- পুরো tracking page mobile-friendly হবে।
- Search এবং tracking timeline mobile screen-এর জন্য optimized থাকবে।


### Guest Checkout & Automatic Account Creation

#### 1. Guest Checkout
- Logged-out user কোনো account ছাড়াই order করতে পারবে
- Checkout page-এ customer-এর প্রয়োজনীয় information দিতে পারবে
- Login বা account create করা বাধ্যতামূলক হবে না

#### 2. Checkout Information
- Customer name
- Phone number
- Email (optional/required based on store settings)
- Delivery address
- Shipping method
- Payment method
- Order summary

#### 3. Automatic Account Creation
- Guest checkout complete করার সময় customer-এর জন্য automatically account তৈরি হবে
- Customer-এর provided phone/email account-এর সাথে যুক্ত হবে
- Existing account থাকলে নতুন account তৈরি না করে existing account-এর সাথে order link হবে
- Customer-এর order automatically তার account-এর order history-তে যুক্ত হবে

#### 4. Account Access
- Order successfully placed হওয়ার পর customer account পাওয়ার information দেখানো হবে
- Customer পরবর্তীতে account-এ login করে order history, address এবং profile দেখতে পারবে
- Account access-এর জন্য প্রয়োজনীয় login/verification method ব্যবহার করা হবে

#### 5. Order Confirmation
- Order confirmation page দেখানো হবে
- Order number
- Order summary
- Delivery information
- Account access information

#### 6. Guest Order Security
- Guest order-এর customer information secure রাখতে হবে
- Duplicate account তৈরি prevent করতে হবে
- Existing customer account থাকলে সঠিক account identify করতে হবে

## Profile / Account Settings

### 1. Profile Information
- Profile image
- Name
- Email
- Phone number

### 2. Edit Profile
- Update name
- Update phone number
- Update email address
- Update profile image

### 3. Password & Security
- Change password
- Current password verification
- New password
- Confirm new password
- Password validation

### 4. Account Information
- Account creation date
- Account status

### 5. Account Actions
- Logout
- Delete account

## Address Book

### 1. Saved Addresses
- Address list
- Recipient name
- Phone number
- Full address
- Address type (Home/Office/Other)
- Default address indicator

### 2. Add Address
- Recipient name
- Phone number
- Division
- District
- Area/City
- Full address
- Address type
- Set as default address

### 3. Edit Address
- Update address information
- Change address type
- Set as default address

### 4. Address Actions
- Edit address
- Delete address
- Set as default

### 5. Default Address
- One default delivery address
- Automatically selected during checkout
- Customer can change default address

### 6. Empty State
- No saved address message
- Add New Address button

## Review & Rating

### 1. Review Eligibility
- শুধুমাত্র logged-in customer review দিতে পারবে
- যেকোনো product review করা যাবে
- Website থেকে product purchase করা বাধ্যতামূলক নয়
- একই customer একই product-এর জন্য একটি review দিতে পারবে

### 2. Submit Review
- Star rating (1–5)
- Review title
- Review comment
- Product photo upload
- Review submit button

### 3. Review Management
- Customer নিজের review দেখতে পারবে
- নিজের review edit করতে পারবে
- নিজের review delete করতে পারবে

### 4. Review Display
- Average rating
- Total review count
- Rating breakdown
- Customer name
- Rating
- Review date
- Review comment
- Review photos

### 5. Review Moderation
- নতুন review প্রথমে pending থাকবে
- Admin review approve/hide করতে পারবে
- Inappropriate review remove করতে পারবে

### 6. Review Sorting & Filtering
- Most recent
- Highest rating
- Lowest rating
- Photo reviews

### 7. Empty State
- কোনো review না থাকলে empty review message
- Write a Review button

### 8. Review Badge
- Website order থেকে verified purchase হলে review-এর পাশে **Verified Purchase** badge দেখানো হবে
- External purchase বা non-verified review-এ badge থাকবে না


---

## 🔐 Admin Dashboard

> **🔧 Implementation Guide**
> এই পুরো module `app/(admin)` route group-এ, Better Auth role check middleware দিয়ে protect করা থাকবে। সব list/table shadcn/ui `Table` + pagination pattern দিয়ে, mutation-গুলো Server Actions বা `app/api/admin/*` route handler দিয়ে হবে, TanStack Query দিয়ে client-side cache invalidate।

## Admin Dashboard Sidebar

### 1. Dashboard
### 1. Overview
Total sales, Total revenue, Total orders, Total customers, Total products, Pending orders, Low stock products
### 2. Sales Summary
Today's sales, Sales by date range, Order count, Average order value, Sales trend
### 3. Order Summary
Pending orders, Processing orders, Shipped orders, Delivered orders, Cancelled orders, Returned orders
### 4. Revenue Summary
Today's revenue, Revenue by date range, Order count, Total revenue
### 5. Low Stock Summary
Low stock products, Out-of-stock products, Current stock quantity, Stock threshold, View Product
### 6. Recent Orders
Order number, Customer name, Order date, Total amount, Payment status, Order status, View Order button
### 7. Quick Actions
Add Product, View Orders, Add Coupon, Create Landing Page

### 2. Orders
- All Orders
- Pending
- Processing
- Confirmed
- Shipped
- Delivered
- Cancelled
- Returned
- Order Search / Filters

### 3. Products
- All Products
- Add Product
- Categories
- Brands
- Product Variants
- Inventory
- Low Stock
- Bulk Import
- Media Library

### 4. Customers
- All Customers
- Customer Details
- Order History
- Customer Search / Filters

### 5. Fake Order Prevention
- Risky Orders
- Manual Review
- Verification Queue
- Fraud / Risk Rules
- Customer Risk History

### 6. Courier
- Courier Dashboard
- Courier Accounts
- Shipments
- Booking Queue
- Tracking
- Delivery Status
- Returned Orders

### 7. Landing Pages
- All Landing Pages
- Create Landing Page
- Templates
- Sections
- Drafts
- Published Pages

### 8. Reviews
- All Reviews
- Pending Reviews
- Approved Reviews
- Hidden Reviews

### 9. Discounts & Coupons
- All Coupons
- Create Coupon
- Active Coupons
- Expired Coupons

### Appearance / Storefront

- Banners & Sliders
  - Homepage banners
  - Promotional banners
  - Slider management

- Navigation / Menus
  - Header menu
  - Footer links
  - Menu order / visibility

- Pages (CMS)
  - About Us
  - Contact Us
  - Privacy Policy
  - Terms & Conditions
  - Other static pages

### 10. Reports & Analytics
- Sales Analytics
- Orders Analytics
- Product Performance
- Customer Analytics
- Revenue Reports
- Courier / Delivery Reports

### 11. Notifications
- Notification Center
- Notification Templates
- Notification Settings
- Notification History

### 13. Store Settings
- General Settings
- Store Information
- Currency
- Shipping Settings
- Payment Settings
- Tax Settings
- Notification Settings
- Social Links
- SEO Settings

### 14. Admin Profile
- My Profile
- Account Settings
- Security
- Logout


---

## 🎯 Landing Page System

> **🔧 Implementation Guide**
> `LandingPage` + `LandingPageSection` model ব্যবহার করে। Public render route: `app/lp/[slug]/page.tsx` (dynamic, SSR)। প্রতিটা `sectionType`-এর জন্য একটা fixed React component থাকবে (Hero, ProductHighlight, Features, Offer, Testimonial, FAQ, Video, Gallery, OrderForm, Footer) — section content শুধু JSON data হিসেবে আসবে, drag-drop builder লাগবে না।

### 43. Landing Page Template Library
- ৪–৫টি ready-made landing page design
- প্রতিটি template-এর আলাদা layout/design
- Template preview
- Template selection

### 44. Predefined Section Library
- প্রায় ১০টি reusable section
- Hero section
- Product section
- Features section
- Offer section
- Testimonial section
- FAQ section
- Video section
- Gallery section
- Order Form section
- Footer section

### 45. Landing Page Creation
- Landing page name
- Template selection
- Product selection
- Initial section setup
- Save as draft

### 46. Section Enable / Disable
- Available sections list
- Section enable
- Section disable
- Section visibility status

### 47. Section Content Editing
- Text editing
- Image selection/upload
- Product selection
- Offer information
- Button text/link
- Section-specific content

### 48. Landing Page Preview
- Desktop preview
- Mobile preview
- Full page preview
- Preview before publish

### 49. Custom Slug
- Custom URL slug
- Slug availability validation
- Duplicate slug prevention
- Slug update

### 50. Publish / Unpublish
- Publish landing page
- Unpublish landing page
- Draft status
- Published status
- Published page access

### 51. Landing Page Order Integration
- Landing page order form
- Customer information collection
- Product/order information
- Order creation
- Fraud-check integration
- Order processing integration
- Courier workflow integration

---

## 🛡️ Fake Order Prevention

> **🔧 Implementation Guide**
> `RiskRule` + `OrderRiskFlag` model ব্যবহার করে। Order create হওয়ার সময় `services/fraud/riskEngine.ts` synchronously রান হয়ে score বের করবে; threshold-এর উপরে গেলে order status "flagged" হয়ে Manual Review Queue-এ যাবে এবং customer-কে confirmation popup দেখানো হবে। External AI/ML লাগবে না, rule-based scoring যথেষ্ট।

### 35. Risk Check Engine
- Customer information check
- Phone number check
- Address information check
- Previous order history
- Previous return/cancel history
- Order pattern analysis
- Risk rule evaluation

### 36. Risk Score / Order Flagging
- Risk score calculation
- Risk level
- Risk reasons
- Order flagging
- Risk status

### 37. Manual Review Queue
- Flagged order list
- Risk details
- Customer/order information
- Approve order
- Reject order
- Review status
- Admin review notes

### 38. Customer Verification
- Verification request
- Phone verification
- Customer confirmation
- Verification status
- Verification result
- Verified / Failed status

---

## 🚚 Courier Automation

> **🔧 Implementation Guide**
> `CourierAccount` + `Shipment` model ব্যবহার করে। `services/courier/` folder-এ প্রতিটা courier (Pathao, Steadfast)-এর জন্য একটা common interface (`bookShipment()`, `getStatus()`) implement করা adapter থাকবে, যাতে ভবিষ্যতে নতুন courier যোগ করা সহজ হয়। Status sync একটা scheduled job/cron বা webhook দিয়ে হবে।

### 39. Courier Account Connection
- Courier selection
- Courier account/API credentials
- Connect courier account
- Connection status
- Disconnect courier account
- Multiple courier support

### 40. Courier Booking
- Eligible order selection
- Courier selection
- Automatic booking
- Booking status
- Consignment/tracking ID
- Booking failure handling

### 41. Courier Tracking
- Tracking ID
- Courier name
- Tracking status
- Shipment information
- Tracking link
- Delivery information

### 42. Courier Status Sync
- Courier status retrieval
- Automatic order status update
- Shipped status
- Out for delivery status
- Delivered status
- Cancelled/returned status
- Sync failure handling