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


## 20. Complete Operational Workflow by Zones, Representatives, and Customers

This scenario explains a full operating day. Assume there are five operating zones. Each zone has ten customers and five sales representatives. This means the organization manages fifty customers and twenty-five representatives during the operating day.

### 20.1 Zone Distribution

```text
Organization
│
├── Zone 1
│   ├── 10 customers
│   └── 5 representatives
│
├── Zone 2
│   ├── 10 customers
│   └── 5 representatives
│
├── Zone 3
│   ├── 10 customers
│   └── 5 representatives
│
├── Zone 4
│   ├── 10 customers
│   └── 5 representatives
│
└── Zone 5
    ├── 10 customers
    └── 5 representatives
```

### 20.2 Full Day Cycle from the First Step

```text
Prepare master data
↓
Open the operating day
↓
Receive customer orders from the existing app, website, admin, or representative
↓
Detect the customer zone from location
↓
Assign the order to the suitable representative in the zone
↓
Validate balance and credit limit
↓
Validate stock in the correct section
↓
Approve the order
↓
Pick the order in the warehouse
↓
Pack and prepare for delivery
↓
Hand shipments to representatives
↓
Start phone-based representative tracking
↓
Start daily route
↓
Visit customers one by one
↓
Deliver goods or record delivery failure
↓
Issue invoice and collect cash or post credit
↓
Update stock and customer balance automatically
↓
End representative day
↓
Settle collected cash
↓
Management reviews reports
↓
Close the day
```

### 20.3 Detailed Example for One Zone

Zone 1 has ten customers and five representatives. Customers can be distributed by geographic proximity and order volume.

| Representative | Customers | Expected work |
|---|---:|---|
| Representative 1 | Customer 1 and Customer 2 | Delivery and collection |
| Representative 2 | Customer 3 and Customer 4 | Delivery only |
| Representative 3 | Customer 5 and Customer 6 | Old debt collection and follow-up |
| Representative 4 | Customer 7 and Customer 8 | New orders and delivery |
| Representative 5 | Customer 9 and Customer 10 | Returns and collection |

```text
Zone Supervisor
│
├── Representative 1 ← Customer 1 ← Customer 2
├── Representative 2 ← Customer 3 ← Customer 4
├── Representative 3 ← Customer 5 ← Customer 6
├── Representative 4 ← Customer 7 ← Customer 8
└── Representative 5 ← Customer 9 ← Customer 10
```

### 20.4 What Happens When a Customer Creates an Order

1. The customer orders from the existing app or web account.
2. The system reads the customer location and links the order to a zone.
3. The system selects the customer price list.
4. The system validates the payment method.
5. For credit sales, credit limit and overdue balance are checked.
6. The system checks available stock in the warehouse and section.
7. If stock is available, the quantity is reserved for the order.
8. If stock is not available, partial fulfillment or order hold is applied according to policy.
9. After approval, the order appears for the warehouse keeper.
10. After preparation, the order is assigned to one representative in the zone.

### 20.5 How Five Representatives Work in the Same Zone

- Each representative sees only assigned customers.
- Each representative sees only assigned orders and route.
- The zone supervisor sees the five representatives in the zone.
- Management sees all zones and all representatives.
- When a representative reaches the customer radius, arrival is recorded.
- On delivery, order, invoice, stock, and balance are updated.
- On collection, the amount remains in representative custody until settlement.

## 21. Separate Role Journeys

### 21.1 General Manager Journey

1. Opens the admin dashboard.
2. Reviews daily indicators.
3. Monitors sales, collections, and receivables.
4. Reviews zone and representative performance.
5. Reviews low-stock and out-of-stock products.
6. Approves exceptions such as credit-limit overrides or major adjustments.
7. Exports final reports.

### 21.2 Sales Manager Journey

1. Reviews daily orders.
2. Distributes orders by zones and representatives.
3. Reviews customers with overdue balances.
4. Monitors representative visits.
5. Follows failed deliveries and reasons.
6. Reviews representative targets and commissions.

### 21.3 Zone Supervisor Journey

1. Opens the zone map.
2. Reviews the ten customers in the zone.
3. Reviews the five representatives in the zone.
4. Tracks representatives from their phones.
5. Redistributes orders when workload changes or a representative is absent.
6. Reviews the zone before day closure.

### 21.4 Sales Representative Journey

1. Logs in from the Android app.
2. Starts the day and enables tracking.
3. Receives assigned orders.
4. Follows the suggested route.
5. Records arrival for every customer.
6. Delivers orders or records failure reasons.
7. Records cash collection or old debt collection.
8. Captures delivery or payment proof according to company policy.
9. Ends the day and views expected cash.
10. Hands over cash and closes custody.

### 21.5 Warehouse Keeper Journey

1. Opens the warehouse dashboard.
2. Views picking requests for the assigned section.
3. Picks quantities from assigned shelves.
4. Records actual picked quantities.
5. Sends the order to packing.
6. Hands over the shipment to the representative.
7. Reviews returns, stock counts, and daily movements.

### 21.6 Accountant or Cashier Journey

1. Reviews daily invoices.
2. Reviews payment receipts.
3. Matches expected cash with received cash.
4. Records shortages or overages if found.
5. Reviews customer balances and statements.
6. Closes the daily financial settlement.

### 21.7 Human Resources Officer Journey

1. Reviews attendance and departure.
2. Reviews leave requests.
3. Records penalties or bonuses.
4. Reviews advances and deductions.
5. Approves monthly payroll.
6. Exports employee reports.

## 22. Human Resources System

A full HR module is added to manage employees, representatives, warehouse keepers, and administrators.

### 22.1 Employee Profile

Each employee profile includes:

- Name.
- Employee number.
- Job title.
- Department.
- Hiring date.
- Basic salary.
- Allowances.
- Contract type.
- Direct manager.
- Employee status.
- Documents.

### 22.2 Attendance and Departure

Attendance can be recorded through:

- Admin dashboard.
- Representative app for field representatives.
- Phone location at day start and end.

```text
Check in
↓
Record time and location
↓
Calculate lateness if any
↓
Check out
↓
Calculate working hours
↓
Send data to payroll
```

### 22.3 Leave Requests

1. The employee submits a leave request.
2. The employee selects leave type, duration, and reason.
3. The direct manager reviews the request.
4. The request is approved or rejected.
5. If approved, the leave balance is updated.
6. The leave appears in attendance and payroll reports.

### 22.4 Penalties and Deductions

The system supports recording:

- Lateness.
- Absence.
- Administrative violation.
- Cash shortage.
- Damage caused by operational error.
- Manual deduction with management approval.

### 22.5 Payroll

Payroll is calculated as:

```text
Basic salary
+
Allowances
+
Commissions
+
Bonuses
-
Deductions
-
Penalties
-
Advances
=
Net salary
```

Representative commission can be calculated based on total sales, collected sales, specific products, zones, or target achievement.

### 22.6 Advances and Bonuses

- Employee advances can be recorded.
- Advance deductions can be scheduled from salary.
- Manual or target-based bonuses can be added.

### 22.7 HR Reports

- Attendance report.
- Lateness and absence report.
- Leave report.
- Penalties report.
- Payroll report.
- Commission report.
- Advances and deductions report.

## 23. Inventory Auto-Updates, Stock Count, and Reconciliation

### 23.1 Auto-Update for Each Warehouse Section

Each warehouse section has an independent balance. Any movement updates the related section immediately.

```text
Purchase received into Section A → increase Section A
Sale from Section A → decrease Section A
Transfer from Section A to Section B → decrease Section A and increase Section B after receiving
Good return to Section B → increase Section B
Damaged return → increase damaged stock, not sellable stock
```

### 23.2 Auto-Update for the Whole Warehouse

The total warehouse balance equals the sum of all section balances.

```text
Main warehouse balance
=
Section A balance
+
Section B balance
+
Section C balance
+
Section D balance
```

Whenever any section balance changes, the total warehouse balance is updated in reports and dashboards.

### 23.3 Reservation Before Delivery

To prevent selling the same quantity twice, the system uses reserved quantity.

```text
Available quantity for sale
=
Physical balance
-
Reserved quantity for approved orders
```

When an order is approved, the quantity is reserved. When delivery is completed, it is deducted from physical stock. When an order is cancelled, the reservation is released.

### 23.4 Stock Count Methods

The system supports multiple stock count methods.

#### Full Stock Count

Warehouse or section movement is paused temporarily, then all products are counted and compared with system balance.

#### Cycle Count

Selected product groups are counted periodically without stopping the whole warehouse.

#### Surprise Count

Management selects certain products or a section to verify balance unexpectedly.

#### Barcode Count

The employee uses a barcode scanner or phone camera to scan products and count quantities.

### 23.5 Stock Reconciliation Cycle

```text
Open stock count session
↓
Select warehouse, section, or products
↓
Count physical quantities
↓
Compare physical count with system balance
↓
Show shortage or overage
↓
Review variance
↓
Approve adjustment
↓
Create stock ledger transaction
↓
Update final balance
```

## 24. Illustrative Diagrams

### 24.1 Order, Warehouse, Delivery, and Finance Relationship

```text
Customer order
↓
Payment and balance review
↓
Stock check and reservation
↓
Picking and packing
↓
Representative handover
↓
Customer delivery
↓
Invoice
↓
Collection or receivable posting
↓
Stock and accounts update
```

### 24.2 Simplified Operating Map

```text
Admin dashboard
│
├── Customers ── Orders ── Invoices ── Collections
│
├── Warehouses ── Sections ── Stock count ── Stock ledger
│
├── Zones ── Customers ── Representatives ── Tracking
│
└── Human resources ── Attendance ── Leaves ── Payroll
```

### 24.3 End-of-Day Cycle

```text
Representative finishes visits
↓
System calculates sales and collections
↓
Representative submits cash
↓
Cashier reconciles cash
↓
Accountant reviews invoices and receipts
↓
Management approves closure
↓
Daily reports are ready
```

## 25. Important Notes Before Implementation

- The business workflow must be approved before final screen design.
- Product data, units, and conversions must be entered accurately.
- Credit sales policies must be clearly defined.
- Employee permissions must be defined before go-live.
- Existing customer app integration must be tested early.
- Representative tracking policy must be clarified because it depends on the representative’s phone, battery, and internet connection.
