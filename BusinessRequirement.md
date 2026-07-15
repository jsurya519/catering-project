# Catering Management ERP + CRM + Employee Portal + WhatsApp Automation

## Project Overview

A web-based Catering Management ERP + CRM application to manage the complete catering business workflow.

The application will cover:

- Customer lead management
- Quotation generation
- Booking management
- Employee management
- Salary and payslip management
- Expense tracking
- GST invoice generation
- Calendar management
- WhatsApp automation
- Employee portal

---

# Business Workflow Understanding

The expected business flow:

```
Customer contacts through WhatsApp / Phone

        ↓

Staff communicates with customer

        ↓

Lead is created

        ↓

Quotation is generated

        ↓

Customer confirms booking

        ↓

Advance payment received

        ↓

Food preparation and event execution

        ↓

Employees assigned

        ↓

GST Invoice generated

        ↓

Follow-up messages sent

        ↓

Salary processed
```

---

# Module 1 - Authentication & User Management

## User Roles

The application will support two primary roles:

- Super Admin
- Employee

---

## Super Admin

Features:

- Login
- Dashboard access
- Manage employees
- Manage menu
- Manage permissions
- Manage salary
- Manage expenses
- Generate GST invoices
- View calendar
- Manage settings

---

## Employee

Features:

- Login
- Dashboard access
- Manage leads
- Create quotations
- Update bookings
- View calendar
- Send WhatsApp messages
- View profile
- View payslips

---

# Module 2 - Lead Management

## Lead Creation

Customer contacts the business through:

- WhatsApp
- Phone call
- Other communication channels

Employee manually creates the lead in the application.

---

## Lead Information

Each lead contains:

- Customer Name
- Mobile Number
- Event Date
- Event Type
- Location
- Number of Guests
- Notes
- Lead Status

---

## Lead Status

Possible lead statuses:

- New Lead
- Follow-up
- Quotation Sent
- Booked
- Cancelled

Employees can manually update the lead status.

---

# Module 3 - WhatsApp Integration & Automation

## Phase 1 Approach

Employee triggers WhatsApp communication from the application.

Workflow:

```
Employee clicks "Send WhatsApp"

        ↓

Spring Boot Application

        ↓

n8n Workflow Automation

        ↓

WhatsApp Business API

        ↓

Customer receives message
```

---

## Future Enhancement

Automatic lead creation from incoming WhatsApp messages.

Workflow:

```
Customer sends WhatsApp message

        ↓

WhatsApp Business API

        ↓

n8n

        ↓

Spring Boot API

        ↓

Lead automatically created
```

---

## Future WhatsApp Automations

Possible automated messages:

- New Year greetings
- Birthday wishes
- Booking confirmation
- Payment reminder
- Event reminder
- Thank you message
- Follow-up reminders

---

# Module 4 - Menu Management

Admin can configure catering menu items.

---

## Menu Categories

Examples:

- Sweet
- Curry
- Rice
- Snacks
- Starters
- Desserts

---

## Menu Item Details

Each menu item contains:

- Item Name
- Category
- Price
- Unit
- Active / Inactive Status

---

## Menu Usage

Employees can select menu items while creating quotations.

---

# Module 5 - Quotation Management

## Quotation Workflow

Customer requests quotation.

Workflow:

```
Employee selects menu items

        ↓

Add quantity and price

        ↓

System calculates total amount

        ↓

Generate quotation PDF

        ↓

Send quotation through WhatsApp
```

---

## Quotation Details

Quotation contains:

- Customer details
- Event details
- Selected menu items
- Quantity
- Rate
- Total amount
- Terms and conditions

---

## Important Business Rule

Quotation should maintain the price snapshot at the time of generation.

Example:

Current menu price:

```
Sweet A - ₹50
```

Quotation generated:

```
Sweet A - ₹50
```

Later menu price changes:

```
Sweet A - ₹60
```

Existing quotation should still show:

```
Sweet A - ₹50
```

---

# Module 6 - Booking Management

Once customer confirms:

```
Lead

↓

Booking
```

---

## Booking Information

Booking contains:

- Customer details
- Event date
- Venue/location
- Number of guests
- Selected menu
- Total amount
- Advance paid
- Total paid amount
- Remaining amount
- Booking status

---

## Payment Tracking

Payment gateway integration is not included.

Payments will be updated manually.

Example:

```
Total Amount     : ₹1,50,000

Advance Paid     : ₹30,000

Additional Paid  : ₹50,000

Remaining Amount : ₹70,000
```

---

# Module 7 - Calendar Management

Calendar view for business planning.

---

## Calendar Displays

- Booked events
- Upcoming events
- Event dates
- Customer details

Purpose:

- Check availability
- Plan resources
- Avoid booking conflicts

---

# Module 8 - Employee Management

Admin can manage employees.

---

## Employee Information

Employee details:

- Name
- Mobile Number
- Email
- Role
- Status

---

# Permission Management (RBAC)

Admin can customize employee access.

Example:

Employee A:

```
☑ Leads

☑ Calendar

☑ Booking

☐ Salary

☐ Expenses

☐ GST
```

Access will be controlled based on assigned permissions.

---

# Module 9 - Salary Management

## Admin Features

Admin can:

- Generate salary
- Generate payslip PDF
- Update salary details

---

## Employee Features

Employee can:

- View profile
- View payslips

---

# Module 10 - Expense Management

Track daily business expenses.

---

## Expense Examples

- Vegetables
- Gas
- Fuel
- Transportation
- Employee payments
- Other operational expenses

---

## Expense Features

- Add expense
- Categorize expense
- View expense history
- Generate reports

---

# Module 11 - GST Invoice Management

Generate GST invoices.

Details to be finalized:

- Invoice format
- GST details
- Tax calculation
- HSN information
- Invoice numbering

---

# Module 12 - Follow-up Automation

Automated follow-up workflows using n8n.

Workflow:

```
Spring Boot

        ↓

n8n

        ↓

WhatsApp Business API

        ↓

Customer
```

Examples:

- Pending quotation reminder
- Payment reminder
- Event reminder
- Customer greetings

---

# Module 13 - Employee Portal

Employee-specific portal.

---

## Employee Features

### Dashboard

- Assigned leads
- Upcoming events
- Pending tasks

### Lead Management

- View leads
- Create leads
- Update lead status
- Send WhatsApp messages

### Booking Management

- View bookings
- Update booking details
- Update payment information

### Calendar

- View upcoming events

### Profile

- View and update profile information

### Payslip

- View generated payslips

---

# Future Enhancements

Possible future modules:

- Automatic WhatsApp lead creation
- Payment gateway integration
- Mobile application
- Attendance management
- Inventory management
- Advanced analytics dashboard
- Customer self-service portal