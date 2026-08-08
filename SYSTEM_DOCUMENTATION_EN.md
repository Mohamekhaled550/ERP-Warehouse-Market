# Full Functional Documentation for the Distribution, Warehouse, Wholesale, and Retail Management System

> This document describes the complete system in English, including user journeys, modules, workflows, hosting notes, pricing, and delivery phases.

## 1. System Overview

The proposed system is not only an e-commerce website or invoicing tool. It is a complete distribution, wholesale, and retail management system that connects customers, products, warehouses, warehouse sections, warehouse keepers, sales representatives, geographic zones, orders, invoices, collections, returns, and operational reports.

The organization already has an existing customer mobile application. This application will be integrated with the new system through shared backend APIs, so orders created from the existing app will follow the same workflow as orders created from the website, admin dashboard, or sales representative application.

## 2. System Goals

- Centralize customers, products, prices, stock, orders, invoices, and payments.
- Integrate the existing customer application with the new backend instead of building a separate system.
- Support cash and credit sales according to each customer’s permissions and credit limit.
- Track each order from creation to picking, packing, dispatch, delivery, invoicing, and collection.
- Manage warehouses, sections, stock keepers, and stock ledger transactions.
- Track sales representatives through their mobile phones, not through standalone tracking devices.
- Define geographic zones and link them with customers and sales representatives.
- Generate invoices, payment receipts, customer statements, and management reports.

## 3. Main System Roles

### 3.1 Management

Management controls and monitors the full system, including:

- Main dashboard.
- Users, roles, and permissions.
- Customers, credit limits, and customer price lists.
- Products, categories, brands, units, and unit conversions.
- Warehouses, warehouse sections, and warehouse keepers.
- Zones, sales representatives, and vehicles.
- Orders, invoices, and payment collections.
- Representative tracking and map monitoring.
- Returns, adjustments, expenses, and reports.

### 3.2 Customer

The customer uses the existing customer app or the web customer account. The customer can:

- Sign in.
- Browse products.
- View applicable prices.
- Create orders.
- Select available payment methods: cash or credit.
- Track order status.
- View invoices, payments, balance, and statement.
- Reorder from a previous order or invoice.

### 3.3 Sales Representative

The sales representative uses an Android application and can:

- Start the working day.
- Enable phone-based location tracking.
- View assigned customers and daily route.
- Register visits and arrivals.
- Deliver orders.
- Collect cash or old debts.
- Capture proof of delivery and payment.
- End the day and settle collected cash.

### 3.4 Warehouse Keeper

The warehouse keeper manages one or more warehouse sections and can:

- Receive goods.
- Record inspection results and damaged quantities.
- Pick and pack orders.
- Request or process internal stock transfers.
- Record stock counts and adjustments.
- Process returned products after inspection.

## 4. System Components

### 4.1 Website

The website serves customers through the web and includes:

- Product and category browsing.
- Customer-specific pricing.
- Cart and checkout.
- Order creation.
- Payment method selection.
- Order tracking.

### 4.2 Admin Dashboard

The admin dashboard is the main control center and includes:

- Main indicators and reports.
- Users, roles, and permissions.
- Customers and suppliers.
- Products and pricing.
- Warehouses and warehouse sections.
- Zones, representatives, and vehicles.
- Orders, invoices, collections, and returns.
- Tracking map.
- Reports and settings.

### 4.3 Sales Representative Dashboard

The representative dashboard displays:

- Representative profile.
- Assigned customers.
- Assigned orders.
- Daily visits.
- Sales and collections.
- End-of-day summary.

### 4.4 Web Customer Account

The web customer account is connected to the same data used by the existing customer app and displays:

- Account data.
- Current balance.
- Credit limit.
- Available credit.
- Orders.
- Invoices.
- Payments.
- Customer statement.

### 4.5 Android Sales Representative App

The representative app is Android-only and includes:

- Login.
- Start day and end day.
- Periodic phone-based location updates.
- Daily route.
- Customers and orders.
- Arrival, delivery, and payment collection.
- Optional signature or photo proof according to company policy.

### 4.6 Tracking and Zone Management

Tracking depends on the representative’s phone. The app periodically sends:

- Latitude.
- Longitude.
- Speed.
- Heading.
- Accuracy.
- Timestamp.
- Battery status.

The system supports:

- Drawing zones on the map.
- Assigning customers to zones based on location.
- Assigning sales representatives to zones.
- Viewing active representatives on the map.
- Measuring zone performance.

## 5. Master Data

### 5.1 Products

Each product includes:

- SKU.
- Barcode.
- Arabic name.
- English name when needed for administration.
- Category.
- Brand.
- Unit.
- Pack size.
- Minimum stock.
- Maximum stock.
- Cost price.
- Wholesale price.
- Retail price.
- Tax.
- Active status.

### 5.2 Units and Conversions

The system supports multiple units, such as piece, pack, and carton. For example, one carton can equal 12 bottles. The system converts quantities automatically to maintain accurate stock.

### 5.3 Pricing

The system supports several price types:

- Retail price.
- Wholesale price.
- Special customer price.
- Promotional price with date range.
- Quantity-based price.

### 5.4 Customers

Customer data includes:

- Name.
- Phone.
- Email.
- Address.
- Geographic location.
- Zone.
- Customer type.
- Price list.
- Assigned sales representative.
- Credit limit.
- Payment terms.
- Current balance.
- Overdue balance.

### 5.5 Zones

Zones are organized hierarchically:

- Country.
- City.
- Zone.
- Sub-zone.
- Customers.

Zone boundaries can be drawn on the map, and customers inside those boundaries can be assigned automatically or manually.

### 5.6 Warehouses and Sections

A warehouse can contain multiple sections, and each section can be assigned to a warehouse keeper.

## 6. User Journeys

### 6.1 Customer Order Journey

1. The customer signs in through the existing app or web account.
2. The customer browses products.
3. The system shows the applicable customer price.
4. The customer adds products to the cart.
5. The customer selects the delivery address.
6. The customer selects an available payment method.
7. If credit is selected, the system validates credit limit, current balance, overdue balance, and order value.
8. The system creates the order.
9. The system detects the customer zone and assigned sales representative.
10. The system checks stock availability.
11. The order moves to review or approval according to company policy.
12. The customer tracks the order until delivery.

### 6.2 Management Order Journey

1. The order appears in the admin dashboard.
2. Management reviews customer, payment method, and stock data.
3. If the credit limit is exceeded, the order is rejected or moved to special approval.
4. After approval, the order moves to picking.
5. Management monitors picking and packing.
6. The order is assigned to the suitable representative.
7. Management tracks delivery and collection through maps and reports.

### 6.3 Warehouse Keeper Journey

1. The warehouse keeper receives the picking request.
2. The system displays products, quantities, and storage locations.
3. The warehouse keeper starts picking.
4. Actual picked quantities are recorded.
5. Shortages are recorded if found.
6. After picking, the order moves to packing.
7. After packing, the order becomes ready for delivery.
8. The shipment is handed over to the representative or delivery team.

### 6.4 Sales Representative Daily Journey

1. The representative logs in to the Android app.
2. The representative starts the day.
3. Phone-based tracking is enabled.
4. Assigned orders, customers, and route are displayed.
5. The representative goes to the first customer.
6. On arrival, the system records GPS location and timestamp.
7. The representative reviews invoice, balance, and payment method.
8. The representative delivers the order.
9. For cash orders, payment is collected and recorded.
10. For credit orders, the invoice amount is posted to the customer account.
11. Old debt can be collected using a separate payment receipt.
12. The representative moves to the next customer.
13. At the end of the day, the app displays sales and collection totals.
14. The representative submits collected cash to the cashier.
15. The day is closed after settlement.

### 6.5 Collection Journey

1. A payment receipt is created when money is received from a customer.
2. The system records customer, representative, payment method, and amount.
3. Signature, image, or note can be attached if required.
4. GPS location and timestamp are stored.
5. The amount is deducted from the customer balance.
6. The receipt appears in the representative’s end-of-day settlement.
7. After cash handover, the receipt is marked as reconciled.

### 6.6 Return Journey

1. The customer or representative creates a return request.
2. Management reviews the request.
3. Goods return to the warehouse for inspection.
4. Good items return to available stock.
5. Damaged items are recorded as damaged stock.
6. A credit note is issued when the return is approved.

## 7. Full Order Cycle

The customer signs in, selects products, creates an order, the system validates pricing, payment, balance, and stock, then the order is approved, picked, packed, assigned to a representative, delivered, invoiced, collected or posted to credit, confirmed by customer signature, deducted from stock, reflected in the customer balance, settled by the representative, reconciled by the warehouse, and reported to management.

## 8. Order Statuses

- Draft.
- Pending.
- Confirmed.
- Approved.
- Picking.
- Picked.
- Packing.
- Ready for delivery.
- Assigned.
- Out for delivery.
- Delivered.
- Partially delivered.
- Delivery failed.
- Returned.
- Cancelled.
- Completed.

## 9. Invoice Statuses

- Draft.
- Issued.
- Partially paid.
- Paid.
- Overdue.
- Cancelled.
- Returned.

## 10. Collection Statuses

- Pending.
- Collected.
- Partially collected.
- Rejected.
- Cancelled.
- Reconciled.

## 11. Inventory Ledger

The system uses a stock ledger instead of relying only on a single product quantity. Every movement is recorded with date, quantity, reason, user, warehouse, and section.

Transaction types include:

- Opening balance.
- Purchase.
- Sale.
- Transfer out.
- Transfer in.
- Good return.
- Damaged return.
- Positive adjustment.
- Negative adjustment.

## 12. Internal Warehouse Transfers

Internal transfers follow this cycle:

1. Transfer request.
2. Approval.
3. In transit.
4. Received by destination section.
5. Completed.

## 13. Permissions

Permissions are role-based. Examples:

- General manager: full access.
- Sales manager: customers, orders, representatives, and reports.
- Warehouse manager: warehouses, picking, stock counts, and transfers.
- Warehouse keeper: assigned section only.
- Accountant: invoices, collections, customer statements, and settlements.
- Sales representative: assigned customers, orders, and collections only.
- Customer: own account, orders, invoices, and payments only.

## 14. Dashboards and Reports

The admin dashboard displays:

- Today’s sales.
- Today’s orders.
- Cash sales.
- Credit sales.
- Collections.
- Outstanding balances.
- Stock value.
- Low-stock products.
- Out-of-stock products.
- Pending picking.
- Pending delivery.
- Active representatives.
- Daily visits.
- Failed deliveries.
- Sales by representative.
- Collections by representative.
- Performance by zone.

## 15. Existing Customer App Integration

The existing customer app will be connected to the new system through shared APIs. This means the app will use the same products, prices, orders, invoices, and balances as the new system. Any order created from the app enters the same operational cycle and no separate backend will be created for the app.

## 16. Recommended Hostinger Hosting

Because the system includes an admin dashboard, website, APIs, database, representative tracking, inventory, and invoicing, a VPS is recommended instead of shared hosting.

According to Hostinger information checked on August 8, 2026, Hostinger KVM VPS plans include options from smaller to larger servers, and Hostinger describes a plan with 2 virtual CPU cores, 8 GB RAM, and 100 GB NVMe SSD storage as suitable for medium-scale applications. The recommendation is:

### 16.1 Initial Launch

- VPS resources not less than 2 CPU cores, 8 GB RAM, and 100 GB fast storage.
- Suitable for the website, admin dashboard, APIs, representative app, and a medium-sized database.

### 16.2 Scaling Stage

- Upgrade to at least 4 CPU cores, 16 GB RAM, and 200 GB storage.
- Recommended when the number of customers, representatives, orders, and tracking events increases.

### 16.3 External Services Not Included

The project prices do not include:

- Hosting cost.
- Domain name.
- Paid certificates or add-ons if any.
- Paid maps, messaging, or email providers.
- Payment gateway fees.
- Paid external backup services.

## 17. Pricing in Egyptian Pounds

| Item | Price |
|---|---:|
| Website | 7,000 EGP |
| Admin dashboard including employee roles and permissions | 8,000 EGP |
| Sales representative dashboard | 3,000 EGP |
| Web customer account connected to the existing customer app | 2,000 EGP |
| Android-only sales representative app | 5,000 EGP |
| Tracking, zone management, and linking zones with customers and representatives | 5,000 EGP |
| Deployment to hosting | 1,000 EGP |
| Total | 31,000 EGP |

> Prices are in Egyptian Pounds and exclude all external services such as hosting, domain, maps, messaging, payment gateways, or any third-party provider.

## 18. Work Breakdown

### Phase 1: Analysis and Documentation

- Confirm final business workflow.
- Define roles and permissions.
- Define master data.
- Approve order, invoice, collection, and stock statuses.

### Phase 2: Database and APIs

- Design the database.
- Build core APIs.
- Prepare integration with the existing customer app.
- Build user and permission management.

### Phase 3: Admin Dashboard and Website

- Build the admin dashboard.
- Build the website.
- Build the web customer account.
- Connect products, pricing, orders, and invoices.

### Phase 4: Warehouse, Orders, and Delivery

- Build warehouses and sections.
- Build the stock ledger.
- Build picking and packing.
- Build delivery and invoice workflows.

### Phase 5: Representative App and Tracking

- Build the Android representative app.
- Enable phone-based tracking.
- Build routes and visits.
- Build collections and end-of-day settlement.
- Connect zones, customers, and representatives.

### Phase 6: Testing and Delivery

- Test the full order cycle.
- Test inventory, collections, and invoices.
- Test existing customer app integration.
- Test tracking and zones.
- Deploy the system to hosting.
- Train key users.

## 19. Estimated Delivery Time

The estimated delivery time is 8 to 12 weeks depending on data readiness, approvals, and feedback speed.

| Phase | Estimated Duration |
|---|---:|
| Final analysis and documentation | 1 week |
| Database and APIs | 2 weeks |
| Admin dashboard, website, and customer web account | 2 to 3 weeks |
| Warehouses, orders, invoices, and collections | 2 weeks |
| Representative app, tracking, and zones | 2 weeks |
| Testing, revisions, deployment, and training | 1 to 2 weeks |

## 20. Important Notes Before Implementation

- The business workflow must be approved before final screen design.
- Product data, units, and conversions must be entered accurately.
- Credit sales policies must be clearly defined.
- Employee permissions must be defined before go-live.
- Existing customer app integration must be tested early.
- Representative tracking policy must be clarified because it depends on the representative’s phone, battery, and internet connection.
