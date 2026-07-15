# Deployment Strategy & Infrastructure

## Application Scale

Based on the expected usage:

- 3–5 Admin users
- 10–20 Employee users
- 100–200 customer interactions per day
- One Spring Boot backend application
- One React frontend application
- One MySQL database
- One n8n workflow automation instance

A simple and cost-effective deployment architecture is recommended.

---

# Recommended Deployment Approach

## Linux Virtual Private Server (VPS)

Deploy the complete application on a single Linux VPS.

### Recommended Server Specification

| Resource | Specification |
|----------|---------------|
| CPU | 2 vCPU |
| RAM | 4 GB |
| Storage | 80 GB SSD |
| Operating System | Ubuntu Linux |

### Estimated Cost

Approximately:

**₹500 – ₹1,000/month** depending on the VPS provider.

---

# Deployment Architecture

Everything will run inside Docker containers on the VPS.

```
                 Internet
                    │
                    ▼
                 Nginx
                    │
          ┌─────────┴─────────┐
          ▼                   ▼
       React             Spring Boot
                              │
                    ┌─────────┴─────────┐
                    ▼                   ▼
                 MySQL                 n8n
```

## Containerized Services

The VPS will host:

- React frontend
- Spring Boot backend
- MySQL database
- n8n workflow automation engine
- Nginx reverse proxy

Docker Compose will be used to manage and deploy all services.

---

# File Storage

Initially, application files will be stored inside the VPS.

Example:

```
/application-storage

    /quotations
        quotation_001.pdf
        quotation_002.pdf

    /payslips
        payslip_jan.pdf

    /gst-invoices
        invoice_001.pdf
```

The application will use **OpenPDF** to generate:

- Customer quotations
- Payslips
- GST invoices

No external object storage (such as AWS S3) is required for Phase 1.

If storage requirements increase in the future, migration to cloud storage can be considered.

---

# Database Backup Strategy

A daily automated database backup will be configured.

Backup workflow:

```
MySQL Database

        ↓

mysqldump

        ↓

backup.sql

        ↓

Compressed Backup

        ↓

Stored Backup Files
```

## Backup Retention

- Keep the last 30 days of backups.

## Future Enhancement

Backups can later be uploaded to external storage such as:

- Google Drive
- AWS S3
- Other cloud storage providers

for additional disaster recovery.

---

# Domain Configuration

The client will purchase a domain name.

Example:

```
www.abcatering.com
```

The domain DNS records will be configured to point to the VPS public IP address.

---

# Estimated Infrastructure & Third-Party Costs

| Item | Estimated Cost |
|------|---------------|
| VPS Hosting | ₹600–₹1,000/month |
| Domain Name | ~₹1,000/year |
| SSL Certificate (Let's Encrypt) | Free |
| Docker | Free |
| MySQL | Free |
| Spring Boot | Free |
| React | Free |
| n8n (Self-hosted) | Free |
| Nginx | Free |
| WhatsApp Business API / Business Solution Provider | Based on provider pricing |
| WhatsApp Messaging Charges | Based on Meta/provider pricing and usage |

---

# Estimated Monthly Infrastructure Cost

Excluding WhatsApp messaging charges:

**Approximately ₹700–₹1,200/month**

Additional annual expense:

- Domain registration: ~₹1,000/year

---

# Third-Party Services (Client Responsibility)

The following accounts and services should be purchased and maintained by the client.

## 1. Domain Name

Example:

```
www.abcatering.com
```

The domain will be used to access the application.

---

## 2. VPS Hosting

A Linux VPS server is required for application deployment.

The client will own and manage the hosting account.

---

## 3. WhatsApp Business Platform Account

For automated WhatsApp communication, the client needs:

Either:

- Direct WhatsApp Business Cloud API account from Meta

or

- Account through an approved WhatsApp Business Solution Provider

---

## 4. WhatsApp Messaging Charges

Any messaging charges applied by:

- Meta WhatsApp Business Platform
- Selected Business Solution Provider

will be paid separately by the client.

Charges depend on:

- Message category
- Usage volume
- Provider pricing model

---

# Important Note

The application will integrate with the client's WhatsApp Business Platform.

Any subscription fees, platform charges, or messaging charges from Meta or third-party WhatsApp providers are separate from:

- Application development cost
- Infrastructure cost
- Maintenance cost

These third-party services will be directly managed and paid by the client.