# F-Commerce Platform — Master Documentation

## 01. Project Overview

F-Commerce Platform is a complete eCommerce operating platform built for Bangladeshi online businesses, especially Facebook-based and COD businesses.

It will bring store management, product management, orders, customers, inventory, landing pages, fraud prevention, courier automation, and notifications into one centralized platform.

The main purpose is to reduce manual work, simplify daily eCommerce operations, and help businesses manage their entire sales process from one place.

The platform will be modular, scalable, customizable, and designed with client ownership and flexibility in mind.

### Core Flow

Traffic → Landing/Store → Order → Verification → Fraud Check → Courier → Delivery → Customer History


# 📋 Master Feature List

## 01. Foundation & Technical Setup

1. **Project Setup & Environment** — Project structure, environment configuration এবং development setup।
2. **Database Schema** — Users, products, variants, categories, orders, customers ইত্যাদির database structure।
3. **Authentication & Authorization** — Customer/Admin login, signup এবং role-based access control।
4. **API Structure** — Backend API structure এবং consistent API patterns তৈরি করা।
5. **Error Handling & Logging** — System-wide error handling এবং logging।
6. **Basic Security** — Input validation, rate limiting এবং basic security protection।
7. **Image Optimization & CDN** — Image upload, optimization এবং fast delivery setup।

---

# 🛠️ Feature Detailed Breakdown

## 01. Foundation & Technical Setup

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

## 02. Customer-Facing Storefront

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


## Admin Dashboard ===================================================
## Admin Dashboard Sidebar

### 1. Dashboard
- Overview
- Sales summary
- Order summary
- Revenue
- Low stock
- Recent orders
- Important alerts

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

