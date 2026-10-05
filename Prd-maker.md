 Perfume Store — Product Requirements Document

---

## SECTION 1 — Project Identity

| Field | Value |
|-------|-------|
| **Project Name** | Perfume Store |
| **Project Type** | E-commerce |
| **Project ID** | PRD-001 |
| **Version** | v1.0 |
| **Status** | Draft |
| **Priority** | High |
| **Created Date** | 2026-10-05 |
| **Last Updated** | 2026-10-05 |
| **Owner** | Yousef Abdallah |
| **Team Members** | Frontend Developer, Backend Developer, Database Specialist, QA Engineer |
| **Tech Stack** | Next.js + TypeScript + Tailwind CSS (Frontend), Node.js + Express + TypeScript + Prisma (Backend), PostgreSQL + Redis, VPS Hosting, Cloudflare CDN |
| **Repository** | [TBD] |
| **Git Branch Prefix** | PRD-feature-name |
| **PRD File Path** | docs/PRD.md |

---

## SECTION 2 — Problem & Purpose

**Problem Statement**

Customers in Egypt currently lack a reliable and user-friendly online platform to purchase authentic perfumes with guaranteed quality and secure return policies. Existing options are fragmented, non-transparent, and lack proper verification of product authenticity. This creates friction in the purchase journey and reduces customer confidence in online perfume retail.

**Project Purpose**

Perfume Store is a dedicated e-commerce platform designed to solve this problem by providing a curated collection of authentic perfumes with transparent product information, secure payment options (including Cash on Delivery), and clear return policies. The platform targets fragrance enthusiasts across Egypt with a seamless shopping experience.

**Business Value**

- Direct revenue generation through product sales
- Building a trusted brand in the Egyptian perfume retail market
- Capturing market share in the growing e-commerce sector in Egypt
- Establishing customer loyalty through quality and service

**Opportunity**

The Egyptian e-commerce market is growing rapidly. There is untapped demand for specialized, trustworthy perfume retailers. A platform that emphasizes authenticity and ease of purchase can capture significant market share in this vertical.

---

## SECTION 3 — Goals & Objectives

**Primary Goal**

Launch a fully functional e-commerce platform with 1,000 perfume products across 20 categories, a secure payment system (including Cash on Delivery), an admin dashboard for complete product and order management, and a coupon system for targeted discounts — all within 8 weeks.

**Objectives**

1. Establish a scalable e-commerce platform capable of handling 100,000 monthly visitors with peaks of 1,000,000 during promotional periods
2. Implement a comprehensive product management system supporting 1,000+ SKUs across 20 categories with subcategories
3. Create a secure user authentication system with email verification and Google Sign-In integration
4. Develop an admin dashboard enabling independent product and order management, coupon creation, and basic analytics
5. Achieve 99.9% uptime and sub-500ms API response times

**Success Definition**

- All P0 features deployed and working without critical bugs
- Platform handles 100,000 monthly users with 99.9% uptime
- Admin can manage all 1,000 products without performance degradation
- Customers complete purchase flow with zero friction points
- Coupon system drives measurable conversion uplift

**Non-Goals**

- Mobile native app (responsive web design only for v1)
- Marketplace or third-party seller integration
- Advanced AI-driven recommendations
- Live chat or telephone support
- Wishlist or saved items
- Subscription or membership programs

---

## SECTION 4 — Scope

**In Scope for v1**

- User authentication (email registration, email verification, Google Sign-In)
- Product catalog management (1,000 products, 20 categories, subcategories)
- Product search and filtering (by category, price, rating)
- Shopping cart and checkout workflow
- Cash on Delivery (COD) payment integration
- Admin dashboard for:
  - Product management (create, read, update, delete)
  - Order management (view, status updates, fulfillment tracking)
  - Coupon code creation and management
  - Basic sales analytics
- Two-tier user roles (Admin, User) with role-based permissions
- Email notifications (order confirmation, shipment updates)
- Order history and tracking for customers

**Out of Scope for v1**

- Native mobile applications (iOS/Android)
- Third-party payment gateways (Stripe, Payfort) — COD only for v1
- Marketplace or seller functionality
- Advanced recommendation engine
- Live chat or customer support system
- Wish list or saved items
- Loyalty programs or referral system
- Accounting/invoice management
- Multi-vendor marketplace
- Automated refund processing

**Assumptions**

- All products are owned and managed by the store owner (Yousef)
- Payment method starts with Cash on Delivery; online payment gateways deferred to v2
- Customers will accept 2-3 business days for delivery to major cities
- SEO optimization and organic traffic will be a secondary focus; initial traffic from social media marketing
- Email deliverability is handled by a third-party service (SendGrid, Mailgun, etc.)

**Constraints**

- 8-week deadline for MVP launch
- Single owner managing all administrative functions initially
- Must handle traffic spikes up to 1,000,000 monthly users
- VPS hosting with limited server resources initially; auto-scaling required
- All product data imported manually or via CSV for v1

**Dependencies**

- Third-party email service provider (SendGrid, Mailgun, or similar)
- Cloudflare CDN availability and configuration
- PostgreSQL and Redis hosting availability
- Google OAuth credentials and setup
- VPS provider setup and infrastructure provisioning

---

## SECTION 5 — Users & Personas

**Primary Users**

**End Customers**
- Fragrance enthusiasts and regular perfume buyers
- Age range: 18–55 years
- Located across Egypt
- Purchase frequency: weekly to monthly
- Tech-savvy enough to browse e-commerce platforms

**Admin (Store Owner)**
- Yousef Abdallah
- Manages all products, orders, and business operations
- Needs a simple, efficient dashboard for daily operations

**Secondary Users**

**Analytics/Reporting Users** (future)
- Business analyst reviewing sales trends
- Deferred to v2

---

### User Roles & Permissions

| Role | Access Level | Key Permissions |
|------|--------------|-----------------|
| **Admin** | Full | Create/Edit/Delete products, manage orders, create coupons, view analytics, manage user permissions |
| **User** | Limited | Browse catalog, add to cart, checkout, view own orders, manage profile |
| **Guest** | Minimal | Browse catalog, view product details (no checkout) |

---

### Full Personas

**Persona 1: The Regular Buyer**

- **Name:** Amira
- **Role:** End Customer
- **Goal:** Purchase authentic perfumes with confidence, discover new scents, receive quality products quickly
- **Pain Point:** Currently buys perfumes from unreliable sources; worries about authenticity and quality; no easy way to compare prices or read reviews
- **Tech Level:** Medium-High (comfortable with e-commerce)
- **Frequency:** Browses weekly, buys 2–3 times monthly
- **Success Definition:** Find desired perfume, complete purchase in under 5 minutes, receive order confirmation and tracking updates
- **Demographics:** Female, 25–40 years old, employed, willing to spend 200–500 EGP per purchase

**Persona 2: The Store Owner (Admin)**

- **Name:** Yousef Abdallah
- **Role:** Admin / Store Owner
- **Goal:** Manage inventory of 1,000+ products efficiently, create promotions to drive sales, process orders, track performance
- **Pain Point:** Manual management is time-consuming and error-prone; needs an intuitive dashboard to control everything independently
- **Tech Level:** High (developer background)
- **Frequency:** Daily dashboard access
- **Success Definition:** Manage 1,000 products, create coupon campaigns, process 50–100 orders daily without system slowdowns
- **Responsibilities:** Product uploads, order fulfillment, customer communication, pricing strategy

---

## SECTION 6 — MoSCoW Feature Prioritization

### Must Have — P0

| ID | Feature | Status | Description | Assigned To | Sprint |
|----|---------|---------|--------------|----|--------|
| P0-F001 | User Authentication | TODO | Email registration, email verification, password management, Google Sign-In integration |  | Phase 1 |
| P0-F002 | Product Catalog | TODO | Store and display 1,000+ perfume products with details (name, description, price, images, category, subcategory) |  | Phase 1 |
| P0-F003 | Category & Subcategory Management | TODO | Organize products into 20 main categories with internal subcategories; admin can create/edit categories |  | Phase 1 |
| P0-F004 | Shopping Cart | TODO | Add/remove products, update quantities, persist cart data, calculate totals |  | Phase 2 |
| P0-F005 | Checkout & Order Creation | TODO | Collect shipping address, confirm order, create order record in database |  | Phase 2 |
| P0-F006 | Cash on Delivery Payment | TODO | Mark order as pending payment, provide delivery instructions, track payment status |  | Phase 2 |
| P0-F007 | Order Management (Admin) | TODO | View all orders, update status (pending, shipped, delivered, cancelled), manage fulfillment |  | Phase 2 |
| P0-F008 | Product Management (Admin) | TODO | Create, read, update, delete products; bulk import via CSV; upload product images |  | Phase 1 |
| P0-F009 | Coupon Code System | TODO | Admin creates coupon codes with discount %, apply to specific products or cart-wide, track usage |  | Phase 2 |
| P0-F010 | User Profile & Order History | TODO | Customers view past orders, order details, track current shipments, manage account settings |  | Phase 2 |
| P0-F011 | Admin Dashboard | TODO | Central hub for product management, order management, coupon management, basic analytics |  | Phase 1 |
| P0-F012 | Email Notifications | TODO | Order confirmation, shipment updates, delivery confirmation sent to customer email |  | Phase 3 |

### Should Have — P1

| ID | Feature | Status | Description | Assigned To | Sprint |
|----|---------|---------|--------------|----|--------|
| P1-F001 | Product Search | TODO | Full-text search across product names and descriptions; suggestions as user types |  | Phase 2 |
| P1-F002 | Product Filtering | TODO | Filter by category, price range, rating, availability |  | Phase 2 |
| P1-F003 | Product Reviews & Ratings | TODO | Customers leave reviews (text + star rating) on purchased products; admin can moderate |  | Phase 3 |
| P1-F004 | Sorting Options | TODO | Sort by price (asc/desc), popularity, newest, rating |  | Phase 2 |
| P1-F005 | Basic Analytics Dashboard | TODO | Admin views total sales, top products, customer count, daily/weekly/monthly trends |  | Phase 3 |
| P1-F006 | User Account Recovery | TODO | Forgot password flow with email reset link |  | Phase 2 |

### Could Have — P2

| ID | Feature | Status | Description | Assigned To | Sprint |
|----|---------|---------|--------------|----|--------|
| P2-F001 | Dark Mode | TODO | Toggle dark/light theme site-wide |  | Phase 4 |
| P2-F002 | Keyboard Shortcuts (Admin) | TODO | Quick navigation in admin dashboard using keyboard |  | Phase 4 |
| P2-F003 | Bulk Order Actions | TODO | Admin bulk export orders, bulk status update |  | Phase 4 |
| P2-F004 | Multi-language Support (AR/EN) | TODO | Support Arabic and English interface and product descriptions |  | Phase 4 |

### Won't Have — P3

| ID | Feature | Status | Description | Assigned To | Sprint |
|----|---------|---------|--------------|----|--------|
| P3-F001 | Native Mobile App | TODO | iOS/Android app deferred; responsive web first |  | v2 |
| P3-F002 | Marketplace/Third-Party Sellers | TODO | Multiple sellers; deferred to v2 or later |  | v2 |
| P3-F003 | Advanced AI Recommendations | TODO | Machine learning product suggestions; deferred |  | v2 |
| P3-F004 | Live Chat Support | TODO | Real-time customer support; email-based support for v1 |  | v2 |
| P3-F005 | Wish List / Saved Items | TODO | Deferred to v2 |  | v2 |
| P3-F006 | Subscription/Membership Plans | TODO | Loyalty programs deferred |  | v2 |

---

## SECTION 7 — Functional Requirements

### P0-F001: User Authentication

**Description**
Users can create an account via email/password or sign in with Google. All accounts must verify email before accessing the platform.

**User Story**
As a customer, I want to sign up securely and log in quickly so I can start shopping without friction.

**Trigger**
- User clicks "Sign Up" or "Sign In"
- User clicks "Continue with Google"

**Pre-conditions**
- Email service is available
- Google OAuth credentials are configured

**Post-conditions**
- User account created and stored in database
- Verification email sent
- User authenticated and logged in
- Session/JWT token issued

**Main Flow**
1. User clicks "Sign Up"
2. User enters email, password, name
3. Validation: email format, password strength (min 8 chars, 1 uppercase, 1 number)
4. Account created, marked as unverified
5. Verification email sent
6. User clicks verification link in email
7. Account marked as verified
8. User redirected to login page
9. User enters email and password
10. System validates credentials
11. JWT token issued, user logged in

**Alternate Flow: Google Sign-In**
1. User clicks "Continue with Google"
2. Google OAuth dialog opens
3. User authenticates with Google account
4. Email verified automatically via Google
5. Account created if new user, linked if existing
6. User logged in, redirected to dashboard

**Alternate Flow: Password Reset**
1. User clicks "Forgot Password?"
2. User enters email
3. Reset link sent via email
4. User clicks link, enters new password
5. Password updated, user redirected to login

**Acceptance Criteria**
- [ ] Email validation confirms valid email format
- [ ] Password validation enforces minimum requirements
- [ ] Verification email sent within 1 second
- [ ] Verification link expires after 24 hours
- [ ] User cannot access catalog/checkout until verified
- [ ] Google Sign-In works without errors
- [ ] Session persists for 30 days on "Remember me"
- [ ] Logout clears session immediately

---

### P0-F002: Product Catalog

**Description**
The platform displays 1,000+ perfume products with detailed information including name, description, price, images, category, and ratings.

**User Story**
As a customer, I want to browse all available perfumes so I can discover options and compare prices.

**Trigger**
- User visits homepage
- User navigates to catalog page

**Pre-conditions**
- Product data is loaded into database
- Images are uploaded to CDN

**Post-conditions**
- User sees paginated product list
- User can view product details by clicking a product

**Main Flow**
1. User lands on homepage
2. System loads featured products (top 20 by rating/sales)
3. Homepage displays product grid with images, names, prices, ratings
4. User clicks "Browse All" or "Shop Now"
5. System loads full catalog page
6. Products paginated (20 per page)
7. User scrolls or clicks next page to see more
8. User clicks on product card to view details
9. Product detail page shows full description, images, reviews, add-to-cart button

**Alternate Flow: Empty State**
1. User views a category with no products
2. System displays "No products available" message
3. User sees suggested categories or popular products instead

**Acceptance Criteria**
- [ ] Homepage loads in under 2 seconds
- [ ] Product grid displays 20 products per page
- [ ] Images lazy-load without blocking page render
- [ ] Product detail page loads in under 500ms
- [ ] Product descriptions truncated appropriately
- [ ] Prices displayed clearly with currency (EGP)
- [ ] Ratings calculated correctly from reviews
- [ ] Out-of-stock products marked clearly

---

### P0-F003: Category & Subcategory Management

**Description**
Products are organized into 20 main categories (e.g., Fragrances, Brands, Fragrance Types) with internal subcategories. Admins can manage categories from the dashboard.

**User Story (Customer)**
As a customer, I want to filter products by category so I can quickly find what I'm looking for.

**User Story (Admin)**
As an admin, I want to organize products into categories and create subcategories so customers can find products easily and I can manage inventory effectively.

**Trigger (Customer)**
- User clicks category link on homepage
- User uses category filter in product list

**Trigger (Admin)**
- Admin clicks "Manage Categories" in dashboard

**Pre-conditions**
- Categories exist in database (pre-populated for v1)
- Admin is authenticated

**Post-conditions (Customer)**
- Product list filtered by selected category
- Subcategories displayed for selection

**Post-conditions (Admin)**
- New category/subcategory saved
- Category list updated
- Products can be assigned to categories

**Main Flow (Customer)**
1. User visits homepage
2. Category menu visible (sidebar or header)
3. User clicks a category (e.g., "Floral")
4. System filters products to show only Floral fragrances
5. Subcategories displayed (e.g., "Light Floral", "Oriental Floral")
6. User selects subcategory
7. Product list narrows further

**Main Flow (Admin)**
1. Admin logs in
2. Clicks "Manage Categories" in dashboard
3. Sees list of 20 existing categories
4. Can create new category: enters name, description, slug
5. Can add subcategories to category: enters name, slug
6. Changes saved to database
7. Admin can delete or archive categories (with confirmation)

**Acceptance Criteria**
- [ ] All 20 categories display on homepage
- [ ] Category filters update product list instantly (under 500ms)
- [ ] Subcategories load when category is selected
- [ ] Admin can CRUD categories without page reload
- [ ] Categories properly associated with products
- [ ] Subcategories inherit from parent category correctly
- [ ] Deleted categories handled gracefully (orphaned products reassigned)

---

### P0-F004: Shopping Cart

**Description**
Users add products to a shopping cart, update quantities, and review items before checkout. Cart data persists across sessions.

**User Story**
As a customer, I want to add multiple products to my cart, adjust quantities, and review my selection before paying.

**Trigger**
- User clicks "Add to Cart" on product page
- User clicks cart icon in header

**Pre-conditions**
- Product exists and is in stock
- User is logged in (or cart stored in localStorage for guests)

**Post-conditions**
- Product added to cart
- Cart quantity badge updated
- Cart data persisted

**Main Flow**
1. User browses products
2. User clicks "Add to Cart" on a product
3. System adds product to cart with quantity = 1
4. Toast notification: "Added to cart"
5. Cart badge in header updates (e.g., "3 items")
6. User continues shopping or clicks cart icon
7. Cart page loads showing all items
8. User can increase/decrease quantities
9. User can remove individual items
10. Cart total calculated (subtotal + shipping estimate)
11. User proceeds to checkout

**Alternate Flow: Out of Stock**
1. User clicks "Add to Cart" on out-of-stock product
2. System shows error: "Product temporarily out of stock"
3. User offered option to add to waitlist (deferred to v2)

**Alternate Flow: Quantity Exceeds Stock**
1. User attempts to add 100 units of product with only 10 in stock
2. System caps quantity to available stock
3. Warning message: "Limited quantity available"

**Acceptance Criteria**
- [ ] Add-to-cart button disables during processing
- [ ] Toast notification appears within 1 second
- [ ] Cart persists after page refresh
- [ ] Quantity input validated (numeric, positive, ≤ stock)
- [ ] Remove button works instantly
- [ ] Cart total calculated accurately
- [ ] Empty cart shows helpful message with shop link
- [ ] Cart data cleared after successful checkout

---

### P0-F005: Checkout & Order Creation

**Description**
Users enter shipping details, review order, and create an order record. Order confirmation sent via email.

**User Story**
As a customer, I want to enter my shipping address and confirm my purchase so I know my order is being processed.

**Trigger**
- User clicks "Proceed to Checkout" from cart

**Pre-conditions**
- Cart contains at least one item
- User is logged in
- Email service available

**Post-conditions**
- Order created in database
- Order assigned unique ID
- Order confirmation email sent
- User redirected to order confirmation page

**Main Flow**
1. User navigates to checkout
2. Shipping address form displayed (pre-filled from profile if available)
3. User enters/confirms: full name, phone, address, city, postal code
4. Form validation: all fields required, phone format, address length
5. User selects payment method (COD only for v1)
6. Order summary displayed: items, quantities, prices, shipping estimate, total
7. User clicks "Confirm Order"
8. System creates order record with status = "Pending Payment"
9. Order confirmation email sent
10. User redirected to confirmation page showing order ID and tracking info
11. User can view order in "My Orders" page

**Alternate Flow: Address Validation Fails**
1. User enters incomplete or invalid address
2. System displays field-specific error messages
3. User corrects and resubmits

**Alternate Flow: Save Address for Future**
1. User checks "Save this address to my profile"
2. Address saved to user account
3. Displayed in future checkouts for quick selection

**Acceptance Criteria**
- [ ] All required fields validated before submission
- [ ] Phone number format validated (Egyptian format)
- [ ] Confirmation email sent within 5 seconds of order creation
- [ ] Order ID generated and displayed
- [ ] Order status initialized to "Pending Payment"
- [ ] Cart emptied after successful order
- [ ] Order confirmation page accessible from email link
- [ ] Duplicate order prevention (prevent double-click submit)

---

### P0-F006: Cash on Delivery Payment

**Description**
Orders are marked as "Pending Payment" at checkout. Payment is collected upon delivery. Admin tracks payment status.

**User Story**
As a customer, I want to pay when my order arrives so I don't have to pay online.

**User Story (Admin)**
As an admin, I want to track which orders have been paid and which are still pending.

**Trigger (Customer)**
- Customer completes checkout with COD payment

**Trigger (Admin)**
- Admin updates order payment status in dashboard

**Pre-conditions**
- Order created with COD payment method

**Post-conditions (Customer)**
- Order marked as "Pending Payment"
- Delivery instructions provided

**Post-conditions (Admin)**
- Payment status visible in admin dashboard
- Admin can mark payment as received

**Main Flow (Customer)**
1. Customer selects COD at checkout
2. Order created with status = "Pending Payment"
3. Confirmation shows: "Pay upon delivery"
4. Customer receives order confirmation email
5. Customer tracks order status until delivery
6. Delivery partner collects payment
7. Customer receives order

**Main Flow (Admin)**
1. Admin views order in dashboard
2. Order shows status "Pending Payment"
3. After delivery partner collects payment, admin updates order
4. Admin clicks "Mark as Paid"
5. Payment status changes to "Received"
6. Customer receives "Payment Received" notification (optional for v1)

**Acceptance Criteria**
- [ ] COD payment option visible at checkout
- [ ] Order marked "Pending Payment" by default
- [ ] Admin can toggle payment status
- [ ] Payment status change recorded in order history
- [ ] Customer notified of payment requirement in email
- [ ] Reports show pending vs. received payments clearly

---

### P0-F007: Order Management (Admin)

**Description**
Admin dashboard displays all orders with ability to view details, update status, and track fulfillment.

**User Story**
As an admin, I want to manage customer orders, update statuses, and track shipments so I can ensure timely delivery and customer satisfaction.

**Trigger**
- Admin logs in and navigates to "Orders" in dashboard

**Pre-conditions**
- Admin is authenticated
- Orders exist in database

**Post-conditions**
- Admin can view, filter, and update orders

**Main Flow**
1. Admin logs in
2. Clicks "Orders" in dashboard
3. Dashboard displays table of all orders (paginated, 20 per page)
4. Columns: Order ID, Customer Name, Total, Order Date, Status, Actions
5. Orders sorted by date (newest first)
6. Admin can filter by status: Pending Payment, Processing, Shipped, Delivered, Cancelled
7. Admin can click order to view details: customer info, items, address, payment status
8. Admin clicks "Update Status" button
9. Status dropdown: Processing → Shipped → Delivered
10. Admin confirms update
11. System updates order, sends email notification to customer
12. Admin can also cancel orders (with confirmation)

**Alternate Flow: Search Orders**
1. Admin uses search bar to find order by ID or customer name
2. Results displayed instantly (debounced search)

**Alternate Flow: Bulk Actions**
1. Admin checks multiple orders
2. Selects "Mark as Shipped" from bulk menu
3. All checked orders updated at once

**Acceptance Criteria**
- [ ] Orders load in under 1 second
- [ ] Pagination works smoothly (20 orders per page)
- [ ] Status filters update list instantly
- [ ] Order details show all relevant information
- [ ] Status update confirmation prevents accidental changes
- [ ] Customer email sent immediately on status change
- [ ] Order notes/comments can be added (optional for v1)
- [ ] Search case-insensitive and fast

---

### P0-F008: Product Management (Admin)

**Description**
Admin can create, read, update, and delete products. Bulk import via CSV supported. Images uploaded to CDN.

**User Story**
As an admin, I want to manage my product catalog — add new products, edit existing ones, and upload images — so I can keep the catalog up to date.

**Trigger**
- Admin clicks "Products" in dashboard

**Pre-conditions**
- Admin is authenticated

**Post-conditions**
- Product data saved to database
- Images stored on CDN

**Main Flow: Create Product**
1. Admin clicks "Add Product"
2. Form displayed with fields:
   - Name (required)
   - Description (rich text editor)
   - Price (required, numeric)
   - Category (required, dropdown)
   - Subcategory (required, dropdown)
   - Stock quantity (required, numeric)
   - SKU (optional)
   - Images (multiple upload)
   - Meta description (for SEO)
3. Admin fills fields, uploads 1+ images
4. Images uploaded to CDN, URLs stored
5. Admin clicks "Save Product"
6. Product saved to database, assigned product ID
7. Admin redirected to product list
8. Success notification displayed

**Main Flow: Edit Product**
1. Admin clicks "Edit" on product in list
2. Form pre-populated with current data
3. Admin modifies fields
4. Admin can upload new images or remove old ones
5. Clicks "Save Changes"
6. Updates saved to database
7. CDN images updated

**Main Flow: Bulk Import (CSV)**
1. Admin clicks "Import Products"
2. CSV upload dialog opens
3. Admin selects CSV file with product data:
   - Name, Description, Price, Category, Subcategory, Stock, SKU
4. System validates CSV (checks required fields, data types)
5. If valid, preview shows products to import
6. Admin confirms
7. Products batch-inserted into database
8. Admin shown import summary (success count, errors if any)

**Main Flow: Delete Product**
1. Admin clicks "Delete" on product
2. Confirmation dialog appears
3. Admin confirms (irreversible)
4. Product marked as archived (soft delete) or removed
5. Images remain on CDN but no longer linked

**Acceptance Criteria**
- [ ] Product form validates all required fields
- [ ] Image upload supports JPG, PNG, WebP (max 5MB each)
- [ ] Multiple images sortable/reorderable
- [ ] Rich text editor (description) supports basic formatting
- [ ] CSV import handles 1,000+ products without timing out
- [ ] SKU uniqueness validated (if provided)
- [ ] Product list shows pagination and sorting
- [ ] Bulk delete with confirmation prevents accidents
- [ ] Changes recorded with timestamp and admin user

---

### P0-F009: Coupon Code System

**Description**
Admin creates coupon codes with discount percentages or fixed amounts. Coupons can be applied to specific products or entire cart. Customer enters code at checkout.

**User Story (Admin)**
As an admin, I want to create promotional coupon codes so I can offer discounts and drive sales.

**User Story (Customer)**
As a customer, I want to apply a coupon code at checkout to receive a discount.

**Trigger (Admin)**
- Admin clicks "Coupons" in dashboard

**Trigger (Customer)**
- Customer enters coupon code field at checkout

**Pre-conditions (Admin)**
- Admin is authenticated

**Pre-conditions (Customer)**
- Cart has items
- Valid coupon code exists

**Post-conditions (Admin)**
- Coupon saved to database with metadata

**Post-conditions (Customer)**
- Discount applied to cart/order total
- Coupon usage tracked

**Main Flow (Admin: Create Coupon)**
1. Admin clicks "Coupons" → "Create Coupon"
2. Form displayed:
   - Coupon Code (required, alphanumeric, uppercase)
   - Discount Type: Percentage (%) or Fixed Amount (EGP)
   - Discount Value (e.g., 20 for 20%)
   - Applicable Scope: Cart-wide or Specific Products
   - Expiration Date (required)
   - Usage Limit: Max uses (optional)
   - Min Purchase Amount (optional)
3. Admin fills form, selects which products if product-specific
4. Clicks "Create Coupon"
5. Coupon saved to database
6. Admin sees confirmation

**Main Flow (Customer: Apply Coupon)**
1. Customer in checkout, sees "Coupon Code" input field
2. Customer enters valid coupon code
3. System validates:
   - Code exists and is not expired
   - Usage limit not exceeded
   - Min purchase amount met (if applicable)
   - Code is applicable to items in cart (if product-specific)
4. If valid, discount calculated and applied instantly
5. Cart total updated
6. Success message: "Coupon applied: Save X EGP"
7. Customer proceeds to checkout
8. Discount honored on final order
9. Coupon usage incremented in database

**Main Flow (Admin: View Coupon Performance)**
1. Admin views coupon list
2. Columns: Code, Discount, Expiration, Uses, Revenue Impact
3. Admin can enable/disable or delete coupons
4. Admin can view usage analytics (total discounts given, usage rate)

**Acceptance Criteria**
- [ ] Coupon code case-insensitive at entry
- [ ] Invalid codes show clear error message
- [ ] Expired coupons rejected with message
- [ ] Usage limit enforced
- [ ] Discount calculated correctly (% and fixed)
- [ ] Discount applied before tax/shipping
- [ ] Multiple coupons per cart not allowed (only one active)
- [ ] Coupon codes unique in database
- [ ] Admin can track total discount given per coupon

---

### P0-F010: User Profile & Order History

**Description**
Customers can view and manage their profile, see past orders, track current shipments, and manage account settings.

**User Story**
As a customer, I want to see all my past orders, track current shipments, and manage my account information.

**Trigger**
- Customer logs in and clicks "My Account" or "Orders"

**Pre-conditions**
- Customer is logged in
- Customer has placed at least one order

**Post-conditions**
- Customer can view profile and order data

**Main Flow**
1. Customer clicks "My Account" in header
2. Profile page loads with tabs: Profile, Orders, Address Book, Settings
3. Profile tab shows:
   - Name, email, phone (editable)
   - Account creation date
   - Total orders placed
   - Edit Profile button
4. Customer clicks "Edit Profile"
5. Form displayed with current data
6. Customer updates name, phone, email
7. Clicks "Save Changes"
8. Changes saved, confirmation shown
9. Customer clicks "Orders" tab
10. Order list displayed (paginated, newest first)
11. Columns: Order ID, Date, Total, Status, Actions
12. Customer clicks order to view details:
    - Items ordered, quantities, prices
    - Shipping address
    - Order status timeline (Processing → Shipped → Delivered)
    - Estimated delivery date (if available)
    - Option to print receipt
13. Customer can track order: status updates, tracking number (if available)

**Alternate Flow: Address Book**
1. Customer manages saved addresses
2. Add new address, edit existing, delete unused
3. Primary address marked for checkout

**Alternate Flow: Account Settings**
1. Customer can change password
2. Manage email preferences (opt-in/out of notifications)
3. Delete account (deferred to v2)

**Acceptance Criteria**
- [ ] Profile updates persist immediately
- [ ] Email change requires verification link
- [ ] Password change requires current password confirmation
- [ ] Orders display with correct totals
- [ ] Order status timeline shows accurate progression
- [ ] Estimated delivery date calculated correctly
- [ ] Addresses saved and retrieved correctly
- [ ] Email preferences respected (no emails if opted out)

---

### P0-F011: Admin Dashboard

**Description**
Centralized hub for admin functions: product management, order management, coupon management, and basic analytics.

**User Story**
As an admin, I want a single dashboard where I can manage all aspects of the business — products, orders, and promotions.

**Trigger**
- Admin logs in

**Pre-conditions**
- Admin is authenticated

**Post-conditions**
- Dashboard displays overview and navigation to all admin features

**Main Flow**
1. Admin logs in
2. Dashboard homepage loads with overview cards:
   - Total Revenue (monthly)
   - Total Orders (monthly)
   - Active Customers
   - Pending Orders count
3. Quick-access cards for key metrics (clickable)
4. Sidebar navigation with options:
   - Products (with count)
   - Orders (with pending count)
   - Coupons
   - Analytics (basic)
   - Settings
5. Admin clicks each section to manage
6. Each section has its own interface (see P0-F008, P0-F007, P0-F009)

**Acceptance Criteria**
- [ ] Dashboard loads in under 2 seconds
- [ ] Metrics updated within 5 minutes (near real-time)
- [ ] Navigation is intuitive and accessible
- [ ] Admin can complete daily tasks without leaving dashboard
- [ ] Mobile-responsive (admin may access from phone)

---

### P0-F012: Email Notifications

**Description**
System sends transactional emails: order confirmations, shipment updates, delivery notifications.

**User Story**
As a customer, I want to receive email updates about my order status so I'm always informed.

**Trigger**
- Order placed (confirmation)
- Order status changes (shipment, delivery)

**Pre-conditions**
- Email service configured (SendGrid, Mailgun, etc.)
- Customer email is valid

**Post-conditions**
- Email sent to customer
- Email log recorded

**Email Types**

**Order Confirmation Email**
- Sent immediately after order creation
- Contains: Order ID, order date, items, shipping address, total, estimated delivery
- Call-to-action: Track Order button
- Unsubscribe link

**Shipment Notification**
- Sent when admin marks order as "Shipped"
- Contains: Tracking number (if available), expected delivery date
- Call-to-action: Track Order button

**Delivery Confirmation**
- Sent when order marked as "Delivered"
- Contains: "Your order has been delivered" message
- Prompt to leave review (links to product review page)
- Call-to-action: Shop Again button

**Acceptance Criteria**
- [ ] Emails sent within 5 seconds of trigger event
- [ ] Emails formatted correctly (no broken layout, readable on mobile)
- [ ] All dynamic data (order ID, address, total) accurate
- [ ] Unsubscribe link functional and removes customer from all emails
- [ ] Email templates consistent with brand
- [ ] Failed email delivery handled gracefully (retry mechanism)
- [ ] Email logs stored for audit trail

---

## SECTION 8 — Non-Functional Requirements

**Performance**

- Page load time: < 2 seconds (measured at p95, with median under 1 second)
- API response time: < 500ms (median response at p95)
- Search results returned in < 1 second
- Cart operations (add, remove, update) instant (< 100ms)
- Product detail page loads in < 500ms
- Admin dashboard loads in < 1.5 seconds

**Security**

- All passwords hashed with bcrypt (min 12 rounds)
- All API endpoints require authentication (JWT) except public product listing and auth endpoints
- CSRF protection on all state-changing endpoints
- Input validation and sanitization on all forms (server-side)
- SQL injection prevention via parameterized queries (Prisma ORM)
- XSS protection via Content Security Policy headers
- Rate limiting on auth endpoints (max 5 failed login attempts per minute per IP)
- TLS 1.3 for all data in transit
- AES-256 encryption for sensitive data at rest (if stored beyond JWT)
- Admin dashboard accessible only via HTTPS
- Coupon codes not exposed in API responses (only on server-side validation)

**Availability & Uptime**

- Target uptime: 99.9% (allows ~43 minutes downtime per month)
- Graceful degradation during peak traffic (1M monthly users)
- Database replication and backup: daily backups with 30-day retention
- Automated failover for database connection failures
- Health check monitoring every 5 minutes; alerts if endpoint returns non-200 status

**Scalability**

- **Expected traffic at launch:** 100,000 monthly users
- **Peak traffic:** 1,000,000 monthly during promotions
- **Expected growth target (12 months):** Scale to 5-10x monthly users without rewrite
- **Concurrent users:** Support 5,000+ concurrent users during peak hours
- **Database:** PostgreSQL with read replicas for scaling queries
- **Caching:** Redis for session management, cart data, and frequently accessed product data
- **CDN:** Cloudflare for image delivery and static asset caching
- **Load balancing:** VPS with horizontal scaling (multiple app servers behind load balancer, if needed)
- **Database connection pooling:** PgBouncer to handle connection limits

**Accessibility**

- WCAG 2.1 Level AA compliance
- Alt text on all images
- Semantic HTML structure
- Keyboard navigation support
- Color contrast ratio ≥ 4.5:1 for text
- Forms have associated labels
- Error messages clear and linked to form fields

**Compatibility**

**Browsers:**
- Chrome/Edge 100+
- Safari 15+
- Firefox 100+

**Devices:**
- Desktop (1920x1080 and above)
- Tablet (768px and above)
- Mobile (375px and above)
- All major modern mobile browsers

**Data & Compliance**

- GDPR compliance: Users can request and delete personal data
- Data retention: User accounts retained until deletion; order data retained for 7 years (legal requirement)
- Privacy policy and Terms of Service displayed and linked prominently
- Cookies disclosed and consent managed (even though COD has minimal tracking)
- PCI-DSS compliance: No card data stored; COD only for v1

**Observability & Logging**

- Structured JSON logging for all events (auth, errors, orders, API calls)
- Log retention: 90 days minimum
- Error tracking with stack traces (e.g., Sentry)
- Application monitoring (e.g., New Relic) tracking performance metrics
- Admin dashboard includes basic analytics: daily revenue, order count, top products
- Alerting thresholds:
  - Error rate > 1% → alert
  - Response time p95 > 1 second → alert
  - Uptime < 99.9% → alert
  - Database connection failures → immediate alert

---

## SECTION 9 — Technical Architecture

**Frontend Stack**

- **Framework:** Next.js 14+ with React 18
- **Language:** TypeScript
- **Styling:** Tailwind CSS
- **State Management:** React Context or Zustand (minimal for v1)
- **UI Components:** Headless UI / Radix UI or custom components
- **Form handling:** React Hook Form + Zod for validation
- **HTTP Client:** Fetch API or Axios
- **Build tool:** Next.js built-in (Webpack)
- **Package manager:** pnpm or npm
- **Deployment:** Vercel (for v1) or self-hosted on VPS

**Backend Stack**

- **Runtime:** Node.js 18+
- **Framework:** Express.js
- **Language:** TypeScript
- **ORM:** Prisma
- **Validation:** Zod or Joi
- **Authentication:** JWT (jsonwebtoken library) with refresh token rotation
- **Email:** SendGrid SDK or Mailgun
- **File uploads:** Cloudflare R2 or AWS S3 (images to CDN)
- **Job queue:** Bull (for async tasks like email sending)
- **Testing:** Jest + Supertest
- **Package manager:** pnpm or npm
- **Deployment:** VPS (self-hosted or managed platform)

**Database Architecture**

- **Primary DB:** PostgreSQL 14+
- **Caching layer:** Redis 7+
- **Backups:** Automated daily backups, 30-day retention
- **Replication:** Master-replica setup for scaling reads
- **Connection pooling:** PgBouncer
- **Migrations:** Prisma Migrate

**Authentication & Authorization**

- **Strategy:** JWT-based stateless authentication
- **Token issuance:** Access token (15 min expiry) + Refresh token (30 day expiry)
- **Google OAuth:** OAuth 2.0 integration for Sign-In with Google
- **Email verification:** One-time use links with 24-hour expiry
- **Role-based access control (RBAC):** Admin vs User roles stored in JWT claims
- **Password hashing:** bcrypt with 12+ rounds
- **Session management:** Redis stores session metadata if needed; primarily stateless via JWT

**Infrastructure & Deployment**

- **Hosting:** VPS (provider TBD: Linode, DigitalOcean, Hetzner, etc.)
- **OS:** Linux (Ubuntu 22.04 LTS or similar)
- **Container orchestration:** Docker (containerized app) or systemd (simpler for single VPS)
- **Reverse proxy:** Nginx
- **SSL/TLS:** Let's Encrypt with auto-renewal
- **CDN:** Cloudflare (for images, static assets, DDoS protection)
- **CI/CD:** GitHub Actions
  - Run tests on every push to main/develop
  - Build Docker image on merge to main
  - Deploy to VPS on successful build
- **Environment management:** .env files (development, staging, production)
- **Monitoring & logging:** Structured JSON logs shipped to centralized logger (e.g., Datadog, LogRocket, or simple file logging)

**External Integrations**

- **Email service:** SendGrid or Mailgun API for transactional emails
- **OAuth provider:** Google OAuth for Sign-In
- **Payment gateway:** None for v1 (COD only); integration deferred to v2
- **Image storage:** Cloudflare R2 or AWS S3 for product images
- **CDN:** Cloudflare for global distribution
- **Analytics:** PostHog or Mixpanel (optional for v1, deferred to v2)

**API Design (High Level)**

All endpoints follow REST principles with versioning:

/api/v1/auth/register
/api/v1/auth/login
/api/v1/auth/verify-email
/api/v1/auth/refresh-token
/api/v1/auth/logout

/api/v1/products
/api/v1/products/:id
/api/v1/categories
/api/v1/categories/:id/subcategories

/api/v1/cart
/api/v1/cart/items
/api/v1/cart/apply-coupon

/api/v1/orders
/api/v1/orders/:id
/api/v1/orders/:id/status

/api/v1/users/profile
/api/v1/users/addresses

[Admin only]
/api/v1/admin/products
/api/v1/admin/products/import
/api/v1/admin/orders
/api/v1/admin/orders/:id/status
/api/v1/admin/coupons
/api/v1/admin/analytics


**Data Model (Core Entities)**

User

id (UUID)
email (unique)
password_hash
name
phone
role (Admin | User)
email_verified_at
created_at
updated_at

Product

id (UUID)
name
description
price (decimal)
stock_quantity
category_id (FK)
subcategory_id (FK)
sku (optional, unique)
images (JSON array or separate table)
rating (calculated from reviews)
created_at
updated_at

Category

id (UUID)
name
slug
description
created_at

Subcategory

id (UUID)
category_id (FK)
name
slug
created_at

Order

id (UUID)
user_id (FK)
total_amount (decimal)
status (Pending Payment | Processing | Shipped | Delivered | Cancelled)
payment_status (Pending | Received)
shipping_address (JSON)
created_at
updated_at

OrderItem

id (UUID)
order_id (FK)
product_id (FK)
quantity
unit_price
discount_applied (decimal, optional)

Coupon

id (UUID)
code (unique, uppercase)
discount_type (Percentage | Fixed)
discount_value (decimal)
applicable_scope (CartWide | SpecificProducts)
product_ids (JSON array if specific products)
expiration_date
usage_limit (optional)
usage_count
created_at

Cart (stored in Redis or session)

user_id (key)
items (array): { product_id, quantity }
created_at
updated_at

---

## SECTION 10 — Implementation Phases

---

### Phase 1 — Foundation (Weeks 1–2)

**Goal:** Set up authentication system, product database and catalog display, and admin dashboard infrastructure.

**Duration:** 2 weeks

**Deliverables:**
- User authentication (email/password + email verification + Google Sign-In)
- Product database with 1,000 products pre-loaded
- 20 categories and subcategories structure
- Product catalog homepage and listing page
- Product detail page
- Admin dashboard homepage and navigation
- Product management interface (CRUD)
- Admin login (same auth as customers, role-based)

**Task Checklist:**
- [ ] Set up Node.js/Express backend project structure
- [ ] Set up Next.js frontend project structure
- [ ] Create PostgreSQL schema (User, Product, Category, Order, Coupon, Cart)
- [ ] Implement authentication endpoints (register, login, logout, verify-email, google-oauth)
- [ ] Create JWT middleware and role-based access control
- [ ] Build product catalog API endpoints
- [ ] Create product listing page (homepage + all products)
- [ ] Create product detail page
- [ ] Set up Redis for caching and sessions
- [ ] Create admin dashboard layout and navigation
- [ ] Implement product CRUD in admin dashboard
- [ ] Set up email service (SendGrid/Mailgun) for verification emails
- [ ] Configure Cloudflare CDN for image delivery
- [ ] Set up GitHub Actions CI/CD pipeline (automated tests, Docker build)
- [ ] Deploy to VPS (staging environment)
- [ ] Load 1,000 products into database (CSV import)

**Validation at End of Phase:**
- [ ] Users can register, verify email, and log in
- [ ] Google Sign-In works end-to-end
- [ ] All 1,000 products display without performance issues
- [ ] Admin can create, edit, delete products
- [ ] Images load via CDN with caching
- [ ] Database queries perform under 500ms at scale
- [ ] Authentication works for both users and admin

---

### Phase 2 — Core Features (Weeks 3–4)

**Goal:** Build shopping cart, checkout, order management, and coupon system.

**Duration:** 2 weeks

**Deliverables:**
- Shopping cart (add, remove, update quantities)
- Checkout flow with address collection
- Order creation and confirmation
- Cash on Delivery payment placeholder
- Order management for admin (view, update status)
- Coupon code system (admin create, customer apply)
- Order tracking for customers

**Task Checklist:**
- [ ] Create shopping cart endpoints (add item, remove, update quantity)
- [ ] Implement cart persistence (Redis + database)
- [ ] Build cart page UI (frontend)
- [ ] Create checkout flow (address form, payment method selection, order review)
- [ ] Build order creation endpoint
- [ ] Send order confirmation emails
- [ ] Create order tracking page for customers
- [ ] Implement admin order management interface
- [ ] Build order status update endpoints
- [ ] Send status update emails (shipment, delivery)
- [ ] Create coupon code endpoints (admin create, customer apply)
- [ ] Implement coupon validation (expiration, usage limit, min purchase)
- [ ] Apply discount calculations in checkout
- [ ] Add coupon management UI to admin dashboard
- [ ] Write integration tests for checkout flow
- [ ] Performance test: cart operations under 100ms

**Validation at End of Phase:**
- [ ] Users can add products to cart and persist across sessions
- [ ] Checkout collects address and creates order
- [ ] Order confirmation emails sent immediately
- [ ] Admin can view and update order status
- [ ] Customers receive status update emails
- [ ] Coupon codes apply discounts correctly
- [ ] No critical bugs in end-to-end purchase flow

---

### Phase 3 — Polish & P1 Features (Weeks 5–6)

**Goal:** Add search, filtering, product reviews, and admin analytics.

**Duration:** 2 weeks

**Deliverables:**
- Full-text product search
- Filtering (category, price range, rating)
- Sorting options (price, popularity, newest, rating)
- Product reviews and ratings system
- Customer user profile and order history
- Basic admin analytics dashboard
- Email notification improvements

**Task Checklist:**
- [ ] Implement full-text search in PostgreSQL
- [ ] Build search UI (autocomplete, suggestions)
- [ ] Implement filtering endpoints (category, price, stock)
- [ ] Add sorting UI (price asc/desc, popularity, rating)
- [ ] Create reviews/ratings endpoints
- [ ] Build reviews UI on product detail page
- [ ] Implement review moderation in admin dashboard
- [ ] Create user profile page
- [ ] Build order history page
- [ ] Create address book functionality
- [ ] Build admin analytics dashboard (revenue, order count, top products)
- [ ] Implement email preference management
- [ ] Add product review request emails after delivery
- [ ] Performance test search on 1,000 products
- [ ] Load testing: simulate 5,000 concurrent users

**Validation at End of Phase:**
- [ ] Search returns relevant products in < 1 second
- [ ] Filters work smoothly and update results instantly
- [ ] Reviews calculate rating correctly
- [ ] Admin analytics are accurate
- [ ] Customer profile pages load quickly
- [ ] Load test passes (no errors at 5,000 concurrent users)

---

### Phase 4 — Launch Hardening (Weeks 7–8)

**Goal:** Security hardening, performance optimization, monitoring setup, and production readiness.

**Duration:** 2 weeks

**Deliverables:**
- Security audit and fixes
- Performance optimization (caching, CDN tuning)
- Monitoring and alerting setup
- Backup and disaster recovery procedures
- Production environment setup
- Load balancing and auto-scaling (if needed)
- Beta testing with real users
- Public launch

**Task Checklist:**
- [ ] Conduct security review (OWASP Top 10, dependency scanning)
- [ ] Fix any security vulnerabilities
- [ ] Set up WAF (Web Application Firewall) via Cloudflare
- [ ] Implement rate limiting on all endpoints
- [ ] Optimize images (compression, format conversion, lazy loading)
- [ ] Set up Redis caching for high-traffic endpoints
- [ ] Implement CDN caching headers
- [ ] Set up monitoring (error tracking, performance monitoring, uptime checks)
- [ ] Configure alerting (error rate, response time, uptime)
- [ ] Test backup and restore procedures
- [ ] Document disaster recovery plan
- [ ] Set up production database with replication
- [ ] Configure VPS load balancer (if needed for scaling)
- [ ] Stress test: simulate 1M monthly user traffic spikes
- [ ] Prepare launch communication (email, social media)
- [ ] Beta testing with 100 real users (2-3 days)
- [ ] Fix any issues found in beta
- [ ] Cutover to production (or gradual rollout)
- [ ] Post-launch monitoring and quick fixes

**Validation at End of Phase:**
- [ ] Zero critical security issues
- [ ] All API endpoints under 500ms at p95
- [ ] Uptime monitoring in place and reporting accurately
- [ ] Backup tested and restorable
- [ ] Stress test passes (handles 1M user spikes)
- [ ] Beta users report no critical issues
- [ ] Ready for public launch

---

## SECTION 11 — Advanced Execution Rules (Applied)

**User Flow (Real, Not Generic)**

1. **Prospective customer** lands on homepage
2. **Sees featured products** (top-rated perfumes) and 20 category links in sidebar
3. **Clicks "Shop All Perfumes"** or a category (e.g., "Floral")
4. **Product listing page** loads with 20 products, filters available (category, price, rating), sorting options
5. **Finds desired perfume**, clicks product card
6. **Product detail page** shows full description, all images, customer reviews, price, stock status, "Add to Cart" button
7. **Clicks "Add to Cart"**, toast notification confirms addition
8. **Continues shopping or clicks cart icon** in header
9. **Cart page** shows all items, quantities, subtotal, option to apply coupon code
10. **Enters coupon code** (e.g., "SAVE20"), discount applied, total updated
11. **Clicks "Proceed to Checkout"**
12. **Checkout page** asks for shipping address (name, phone, address, city, postal code)
13. **Selects payment method**: "Cash on Delivery"
14. **Reviews order** (items, quantities, address, total including discount)
15. **Clicks "Confirm Order"**
16. **Order created**, confirmation page displays order ID and tracking info
17. **Confirmation email** sent immediately with order details
18. **Customer receives "Your order is being prepared"** email within a few hours (when admin updates status)
19. **Customer receives "Your order has shipped"** email with estimated delivery date
20. **Delivery partner delivers** package; customer pays cash
21. **Customer receives "Delivered"** email, invited to leave a review
22. **Customer can log in**, go to "My Orders", view order details and current status anytime

**Admin Flow**

1. Admin logs in
2. Dashboard shows overview: total revenue (month), total orders, pending orders count
3. Admin clicks "Orders" → sees list of all orders, filtered by status
4. Admin updates status of orders as they are fulfilled (Pending → Processing → Shipped → Delivered)
5. Customers receive automated emails on each status change
6. Admin clicks "Products" to manage catalog
7. Can add new products, edit existing, delete, or bulk import via CSV
8. Admin clicks "Coupons" to create promotional codes
9. Creates coupon "SAVE20" — 20% discount, no expiration, applicable to all products
10. Coupon appears in customer checkout flow, drives conversions
11. Admin views basic analytics: revenue trend, top selling products, customer count

**Edge Cases & Error Handling**

| Condition | System Behavior | User Feedback |
|-----------|-----------------|---------------|
| **User enters invalid email during signup** | Validation fails server-side | "Invalid email format" error message inline under field |
| **User's email is already registered** | Registration endpoint returns 409 Conflict | "Email already in use. Try logging in or use a different email" |
| **User clicks verification link after 24 hours** | Token is expired | "Verification link has expired. Request a new one." with link to resend |
| **Cart is empty at checkout** | Checkout page prevents navigation | "Your cart is empty. Browse products to continue." with Shop button |
| **Product goes out of stock while in cart** | Stock check at checkout | "Product [Name] is no longer available. Remove from cart?" with option to remove |
| **User applies expired coupon** | Validation fails on server | "This coupon has expired" error message |
| **User applies coupon not applicable to their items** | Validation fails | "This coupon cannot be applied to your items" error message |
| **Order fails to create (DB error)** | Transaction rolls back | "An error occurred. Please try again." with option to retry or contact support |
| **Admin tries to update order status out of order** (e.g., mark as Delivered when still Pending) | Business logic prevents | "This order must be marked Shipped before Delivered" |
| **User's session expires mid-checkout** | JWT refresh token used | If refresh fails, user redirected to login with message "Your session expired. Please log in again." |
| **Network error during payment/order creation** | Retry mechanism in frontend | Loading spinner with "Please wait..." then retry button if it fails |
| **Email service is down** | Order is created but email fails | Order succeeds; email retry logic queued; customer can view order in their profile |
| **CDN is slow loading images** | Fallback to origin server | Images load from origin if CDN times out (handled by Cloudflare) |
| **Admin deletes a product that's in active orders** | Product marked as archived; orders unaffected | Admin sees warning "This product is in X active orders"; can still delete (soft delete) |
| **Rate limit exceeded on auth endpoint** | Request rejected with 429 status | "Too many login attempts. Try again in 15 minutes." |

**API Design (Real, Matching Features)**

Authentication:
POST /api/v1/auth/register
Body: { email, password, name }
Response: { user_id, email, message: "Verification email sent" }

POST /api/v1/auth/verify-email
Body: { token }
Response: { message: "Email verified", ready_to_login: true }

POST /api/v1/auth/login
Body: { email, password }
Response: { access_token, refresh_token, user: { id, name, role } }

GET /api/v1/auth/me (requires Auth header)
Response: { user: { id, email, name, role } }

Products:
GET /api/v1/products
Query: ?page=1&limit=20&category=floral&sort=price_asc&min_price=100&max_price=500
Response: { products: [...], total, page, pages }

GET /api/v1/products/:id
Response: { product: { id, name, description, price, images, rating, reviews: [...] } }

POST /api/v1/products/search
Body: { query: "oud" }
Response: { results: [...], count }

Cart:
POST /api/v1/cart/items
Body: { product_id, quantity }
Response: { cart: { items: [...], total } }

DELETE /api/v1/cart/items/:product_id
Response: { cart: { items: [...], total } }

POST /api/v1/cart/apply-coupon
Body: { coupon_code }
Response: { cart: { items: [...], discount, total } }

Orders:
POST /api/v1/orders
Body: { address: { name, phone, address, city }, payment_method: "cod" }
Response: { order_id, order_number, total, status: "Pending Payment", next_steps: "Your order is being prepared." }

GET /api/v1/orders/:id (customer seeing own order)
Response: { order: { id, date, items: [...], total, status, address, created_at, updated_at } }

[Admin only]
GET /api/v1/admin/orders
Query: ?status=shipped&page=1
Response: { orders: [...], total, page }

PUT /api/v1/admin/orders/:id/status
Body: { status: "shipped" }
Response: { order: { id, status }, message: "Status updated. Email sent to customer." }

Coupons:
POST /api/v1/admin/coupons
Body: { code: "SAVE20", discount_type: "percentage", discount_value: 20, expiration_date: "2026-12-31" }
Response: { coupon: { id, code, ... }, message: "Coupon created" }


**Data Model (Real, Matching Features)**

```sql
-- Users
CREATE TABLE users (
  id UUID PRIMARY KEY,
  email VARCHAR(255) UNIQUE NOT NULL,
  password_hash VARCHAR(255) NOT NULL,
  name VARCHAR(255) NOT NULL,
  phone VARCHAR(20),
  role ENUM('admin', 'user') DEFAULT 'user',
  email_verified_at TIMESTAMP,
  created_at TIMESTAMP DEFAULT CURRENT_TIMESTAMP,
  updated_at TIMESTAMP DEFAULT CURRENT_TIMESTAMP
);

-- Products
CREATE TABLE products (
  id UUID PRIMARY KEY,
  name VARCHAR(255) NOT NULL,
  description TEXT,
  price DECIMAL(10, 2) NOT NULL,
  stock_quantity INT DEFAULT 0,
  category_id UUID NOT NULL,
  subcategory_id UUID NOT NULL,
  sku VARCHAR(100) UNIQUE,
  images JSONB, -- array of image URLs
  rating DECIMAL(3, 2) DEFAULT 0,
  created_at TIMESTAMP DEFAULT CURRENT_TIMESTAMP,
  updated_at TIMESTAMP DEFAULT CURRENT_TIMESTAMP,
  FOREIGN KEY (category_id) REFERENCES categories(id),
  FOREIGN KEY (subcategory_id) REFERENCES subcategories(id)
);

-- Categories
CREATE TABLE categories (
  id UUID PRIMARY KEY,
  name VARCHAR(255) NOT NULL,
  slug VARCHAR(255) UNIQUE NOT NULL,
  description TEXT,
  created_at TIMESTAMP DEFAULT CURRENT_TIMESTAMP
);

-- Subcategories
CREATE TABLE subcategories (
  id UUID PRIMARY KEY,
  category_id UUID NOT NULL,
  name VARCHAR(255) NOT NULL,
  slug VARCHAR(255) NOT NULL,
  created_at TIMESTAMP DEFAULT CURRENT_TIMESTAMP,
  FOREIGN KEY (category_id) REFERENCES categories(id),
  UNIQUE(category_id, slug)
);

-- Orders
CREATE TABLE orders (
  id UUID PRIMARY KEY,
  order_number VARCHAR(50) UNIQUE NOT NULL,
  user_id UUID NOT NULL,
  total_amount DECIMAL(10, 2) NOT NULL,
  status ENUM('pending_payment', 'processing', 'shipped', 'delivered', 'cancelled') DEFAULT 'pending_payment',
  payment_status ENUM('pending', 'received') DEFAULT 'pending',
  shipping_address JSONB NOT NULL,
  created_at TIMESTAMP DEFAULT CURRENT_TIMESTAMP,
  updated_at TIMESTAMP DEFAULT CURRENT_TIMESTAMP,
  FOREIGN KEY (user_id) REFERENCES users(id)
);

-- Order Items
CREATE TABLE order_items (
  id UUID PRIMARY KEY,
  order_id UUID NOT NULL,
  product_id UUID NOT NULL,
  quantity INT NOT NULL,
  unit_price DECIMAL(10, 2) NOT NULL,
  discount_applied DECIMAL(10, 2) DEFAULT 0,
  created_at TIMESTAMP DEFAULT CURRENT_TIMESTAMP,
  FOREIGN KEY (order_id) REFERENCES orders(id),
  FOREIGN KEY (product_id) REFERENCES products(id)
);

-- Coupons
CREATE TABLE coupons (
  id UUID PRIMARY KEY,
  code VARCHAR(50) UNIQUE NOT NULL,
  discount_type ENUM('percentage', 'fixed') NOT NULL,
  discount_value DECIMAL(10, 2) NOT NULL,
  applicable_scope ENUM('cart_wide', 'specific_products') DEFAULT 'cart_wide',
  product_ids JSONB, -- array of product IDs if specific
  expiration_date DATE,
  usage_limit INT,
  usage_count INT DEFAULT 0,
  created_at TIMESTAMP DEFAULT CURRENT_TIMESTAMP
);

-- Reviews
CREATE TABLE reviews (
  id UUID PRIMARY KEY,
  product_id UUID NOT NULL,
  user_id UUID NOT NULL,
  rating INT NOT NULL, -- 1-5
  text TEXT,
  created_at TIMESTAMP DEFAULT CURRENT_TIMESTAMP,
  FOREIGN KEY (product_id) REFERENCES products(id),
  FOREIGN KEY (user_id) REFERENCES users(id)
);
```

**Build Order (Real, Logical)**

| Phase | Features | Why This Order |
|-------|----------|-----------------|
| **Phase 1** | Auth + Products + Admin Dashboard | Users need to sign in; products are the core inventory; admin needs tools to manage catalog |
| **Phase 2** | Cart + Checkout + Orders + Coupons | Once products exist, users need to buy; coupons drive sales; admin needs order tracking |
| **Phase 3** | Search + Filtering + Reviews + Profile | UX enhancements make browsing easier; reviews build trust; customer profiles track history |
| **Phase 4** | Security + Performance + Monitoring + Launch | Hardening before public launch; monitoring for stability at scale |

**UX Rules (Consistent Across System)**

1. **All form submissions have loading state**: "Saving..." spinner replaces button text
2. **All errors shown inline** under the field that failed, in red with icon
3. **All success actions trigger toast notification** at top of page (e.g., "Added to cart", "Order placed")
4. **All data updates persist immediately** or show optimistic UI with rollback on fail
5. **All interactive elements have clear hover/active states**
6. **All empty states show helpful message** (e.g., "No products found. Try another search.")
7. **All confirmation dialogs** for destructive actions (delete product, cancel order)
8. **All navigation breadcrumbs** showing current location (e.g., Home > Products > Floral > Details)
9. **All long-running operations** (checkout, bulk import) show progress indicator
10. **All prices displayed in EGP** with currency symbol (e.g., "250 EGP")

---

## SECTION 12 — Success Metrics and KPIs

**Business Metrics**

| Metric | Target | Measurement |
|--------|--------|-------------|
| Monthly Revenue | 100,000 EGP (Month 1), 500,000 EGP (Month 6) | Sum of all order totals in Stripe/payment gateway reports |
| Average Order Value (AOV) | 300–400 EGP | Total revenue ÷ total orders |
| Customer Acquisition Cost (CAC) | < 100 EGP | Marketing spend ÷ new customers acquired |
| Customer Lifetime Value (CLV) | > 1,200 EGP | Average order value × average repeat purchases |
| Repeat Customer Rate | > 30% (Month 3) | Customers who placed 2+ orders ÷ total customers |
| Conversion Rate (product → order) | > 2% | Orders placed ÷ product detail page views |

**Product Metrics**

| Metric | Target | Measurement |
|--------|--------|-------------|
| Task Completion Rate (checkout) | > 80% | Orders completed ÷ checkouts initiated |
| Cart Abandonment Rate | < 50% | Carts abandoned ÷ carts created (lower is better) |
| Product Search Success | > 70% | Users who search and click a product ÷ users who search |
| Average Product Rating | > 4.0 stars | Mean of all product ratings |
| Coupon Usage Rate | > 15% | Orders with coupons ÷ total orders (sign coupon is driving sales) |
| Product Browse Time | 2–5 min | Average time spent on product detail page (via analytics) |

**Technical Metrics**

| Metric | Target | Measurement |
|--------|--------|-------------|
| API Response Time (p95) | < 500ms | Measure all API calls; 95th percentile should be < 500ms |
| Page Load Time (p95) | < 2 seconds | Measure via Lighthouse / WebVitals; p95 < 2s |
| Uptime | 99.9% | Uptime monitoring tool (Uptime Robot, New Relic); 43min/month downtime allowed |
| Error Rate | < 1% | 5xx errors ÷ total requests (via application monitoring) |
| Database Query Time | < 100ms | 95th percentile for database queries |
| CDN Cache Hit Rate | > 80% | Cached requests ÷ total CDN requests (Cloudflare stats) |
| Zero Security Incidents | 100% | Security audit passes; no data breaches |

**User Satisfaction Metrics**

| Metric | Target | Measurement |
|--------|--------|-------------|
| Overall Review Rating | > 4.2 stars | Mean rating across all product reviews |
| Customer Support Response Rate | 100% (v2) | All support inquiries answered within 24h (v1: email only) |
| Net Promoter Score (NPS) | > 40 | Post-purchase survey: "Would you recommend us?" scale 0-10 |
| Customer Satisfaction (CSAT) | > 85% | Post-purchase survey: "How satisfied are you?" (1-5 scale) |

**Tracking Setup**

- **Tool:** PostHog (open-source) or Mixpanel (cloud)
- **Events to track:**
  - User sign-up, login, logout
  - Product view, add to cart, remove from cart
  - Coupon applied
  - Checkout started, order placed
  - Order status change (shipped, delivered)
  - Review left
  - Search query, filter applied
- **Dashboard:** Admin dashboard displays key metrics (revenue, orders, active users)
- **Review Frequency:** 
  - Daily: Check error rate, uptime, active users
  - Weekly: Review revenue, conversion rate, top products
  - Monthly: Comprehensive review of all KPIs, customer feedback, operational issues

**Success Criteria at Launch**

- Zero critical bugs
- 99.9% uptime maintained
- All pages load under 2 seconds
- 2%+ conversion rate (product view → order)
- Customers receive timely order confirmation emails
- Admin can manage 1,000 products without lag
- Zero data loss or security incidents

---

## SECTION 13 — Timeline and Milestones

**Overall Timeline**

- **Start Date:** 2026-10-05 (Today)
- **Target Launch Date:** 2026-11-30 (8 weeks)
- **Total Duration:** 8 weeks

---

### Milestones

| Milestone | Description | Due Date | Status | Owner |
|-----------|-------------|----------|--------|-------|
| **Kickoff** | Project approved, team assembled, repos created, infrastructure planned | 2026-10-05 | TODO | Yousef |
| **PRD Approved** | This document reviewed and signed off by stakeholders | 2026-10-07 | TODO | Yousef |
| **Phase 1 Done** | Authentication, products, categories, admin dashboard operational | 2026-10-19 | TODO | Dev Team |
| **Phase 2 Done** | Cart, checkout, orders, coupons fully functional | 2026-11-02 | TODO | Dev Team |
| **Phase 3 Done** | Search, filtering, reviews, customer profiles complete | 2026-11-16 | TODO | Dev Team |
| **Phase 4 Done** | Security audit passed, performance optimized, monitoring live | 2026-11-23 | TODO | Dev Team |
| **Beta Launch** | Internal testing with 100 real users (2-3 days) | 2026-11-24 to 2026-11-26 | TODO | QA + Users |
| **Bug Fixes Post-Beta** | Critical issues from beta resolved | 2026-11-27 to 2026-11-29 | TODO | Dev Team |
| **Public Launch** | Go live to general audience | 2026-11-30 | TODO | Yousef |
| **Post-Launch Support** | Monitor errors, quick fixes, customer support | 2026-12-01 onwards | TODO | Dev Team |

---

## SECTION 14 — Risk Register

| ID | Description | Likelihood | Impact | Score | Mitigation | Owner |
|----|-------------|-----------|--------|-------|-----------|-------|
| **R001** | Scope creep — new features requested mid-project | High | High | 9 | Strictly enforce MoSCoW; defer all non-P0/P1 to v2; weekly scope check-ins | Yousef |
| **R002** | Technical unknowns — performance issues at scale (100k users → 1M peak) | Medium | High | 6 | Phase 1 spike on load testing; use Redis/CDN early; stress test in Phase 4 | Dev Lead |
| **R003** | Key person dependency — Yousef is sole decision-maker and product owner | High | High | 9 | Document all decisions in PRD; create playbook for admin operations; train backup admin (future) | Yousef |
| **R004** | Payment gateway not ready for v1 (COD only defers revenue options) | Low | Medium | 2 | Plan integration timeline for v2; communicate COD-only limitation clearly to customers | Yousef |
| **R005** | Third-party service outage (SendGrid email, Cloudflare CDN) | Low | Medium | 2 | Use multiple email providers; implement retry logic; have fallback CDN (AWS CloudFront) | Dev Lead |
| **R006** | Data loss or backup failure | Low | High | 3 | Test backup/restore monthly; use managed database with automated backups; replicate to separate server | Dev Lead |
| **R007** | Security breach or data leak | Low | High | 3 | Regular security audits; dependency scanning; rate limiting; WAF enabled; encrypt sensitive data | Dev Lead |
| **R008** | Delayed product image uploads (1,000 products × 5 images each) | Medium | Low | 2 | Prepare bulk upload pipeline; test with full dataset before launch; schedule off-peak upload | Yousef |
| **R009** | Unexpected VPS provider downtime | Low | High | 3 | Choose reliable VPS provider; have disaster recovery plan; consider multi-region backup (v2) | DevOps |
| **R010** | Team burnout (8-week tight deadline) | Medium | Medium | 4 | Clear phase milestones; realistic task estimation; breaks on weekends; post-launch recovery time | Yousef |

**Risk Score = Likelihood × Impact** (High=3, Medium=2, Low=1)

---

## SECTION 15 — Stakeholders and Approvals

**Stakeholders**

| Name | Role | Involvement | Contact |
|------|------|-------------|---------|
| **Yousef Abdallah** | Product Owner / CEO / Developer | Makes all decisions; owns roadmap; codes part of backend | yousef@code95.com |
| **Development Team** | Developers (Frontend, Backend, DevOps) | Builds the platform | TBD |
| **QA Team** | QA Engineer | Tests functionality, security, performance | TBD |
| **Marketing** | Growth / Social Media | Drives customer acquisition | TBD |
| **Support** | Customer Support (Future) | Handles customer inquiries (v2) | TBD |

**Approval Gates**

| Gate | Approver | Required By | Status | Approval Trigger |
|------|----------|------------|--------|-----------------|
| **PRD Approval** | Yousef Abdallah | 2026-10-07 | TODO | Confirm project scope and approach |
| **Phase 1 Completion** | Yousef Abdallah | 2026-10-19 | TODO | Auth and products working; admin can manage |
| **Phase 2 Completion** | Yousef Abdallah | 2026-11-02 | TODO | Cart, checkout, orders tested and validated |
| **Phase 3 Completion** | Yousef Abdallah | 2026-11-16 | TODO | Search, filtering, profile features complete |
| **Phase 4 Completion & Security Audit** | Yousef Abdallah | 2026-11-23 | TODO | Security and performance baselines met |
| **Beta Testing Results** | Yousef Abdallah | 2026-11-26 | TODO | No critical issues from 100 beta users |
| **Public Launch Approval** | Yousef Abdallah | 2026-11-30 | TODO | Final go/no-go decision; readiness confirmed |

---

## SECTION 16 — References and Links

| Item | Link | Status |
|------|------|--------|
| **Repository (Frontend)** | [TBD] | TBD |
| **Repository (Backend)** | [TBD] | TBD |
| **API Documentation** | [TBD] | TBD |
| **Design Files (Figma)** | [TBD] | TBD |
| **Staging Environment** | [TBD] | TBD |
| **Production Environment** | [TBD] | TBD |
| **CI/CD Pipeline (GitHub Actions)** | [TBD] | TBD |
| **Monitoring Dashboard** | [TBD] | TBD |
| **VPS Provider Account** | [TBD] | TBD |
| **Cloudflare CDN** | [TBD] | TBD |
| **Email Service (SendGrid/Mailgun)** | [TBD] | TBD |
| **Database Backups** | [TBD] | TBD |
| **Project Slack Channel** | [TBD] | TBD |
| **Weekly Status Meeting Notes** | [TBD] | TBD |
| **Customer Feedback Form** | [TBD] | TBD |

---

## SECTION 17 — Revision History

| Version | Date | Author | Changes |
|---------|------|--------|---------|
| v1.0 | 2026-10-05 | Yousef Abdallah | Initial PRD created; all sections completed |

---

**END OF DOCUMENT**