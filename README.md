# 🏦 Bank Transaction System

> **A production-inspired banking backend that simulates secure money transfers using ACID transactions, double-entry ledger accounting, MongoDB sessions, and idempotent request handling.**

![Node.js](https://img.shields.io/badge/Node.js-339933?style=for-the-badge&logo=node.js&logoColor=white)
![Express.js](https://img.shields.io/badge/Express.js-000000?style=for-the-badge&logo=express&logoColor=white)
![MongoDB](https://img.shields.io/badge/MongoDB-47A248?style=for-the-badge&logo=mongodb&logoColor=white)
![Mongoose](https://img.shields.io/badge/Mongoose-880000?style=for-the-badge)
![JWT](https://img.shields.io/badge/JWT-black?style=for-the-badge&logo=jsonwebtokens)

---

# 📖 Overview

**Bank Transaction System** is a backend application that models the core transaction flow of a banking system. It focuses on **transaction reliability**, **data consistency**, and **secure fund transfers** by implementing **MongoDB ACID transactions**, **double-entry ledger accounting**, **JWT authentication**, **idempotent request handling**, and **dynamic balance computation**.

---

# ✨ Features

- 🔐 JWT Authentication & Authorization
- 👤 User Registration & Login
- 🏦 Multiple Bank Account Management
- 💸 Secure Fund Transfers
- 🔄 MongoDB Session-Based ACID Transactions
- 📒 Double-Entry Ledger Accounting
- 🛡️ Idempotent Transaction Processing
- 📊 Dynamic Balance Calculation using Aggregation Pipeline
- 🚫 JWT Token Blacklisting
- ⏳ Automatic Blacklisted Token Cleanup using MongoDB TTL Index
- 📧 Email Notifications
- ⚡ Centralized Error Handling
- 📂 Modular MVC Architecture

---

# 🛠 Tech Stack

| Category | Technologies |
|----------|--------------|
| Backend | Node.js, Express.js |
| Database | MongoDB, Mongoose |
| Authentication | JWT, bcrypt |
| Email Service | Nodemailer |
| Architecture | MVC |

---

# 🏗 Core Banking Concepts

- MongoDB ACID Transactions
- MongoDB Sessions
- Double-Entry Ledger Accounting
- Transaction Rollback
- Idempotency Keys
- Aggregation Pipelines
- JWT Authentication
- Token Blacklisting
- MongoDB TTL Index

---

# 🔄 Transaction Workflow

```text
Authenticate User
        │
        ▼
Validate Request
        │
        ▼
Verify Idempotency Key
        │
        ▼
Start MongoDB Session
        │
        ▼
Create Transaction Record
        │
        ▼
Debit Sender Account
        │
        ▼
Credit Receiver Account
        │
        ▼
Create Ledger Entries
        │
        ▼
Commit Transaction
        │
        ▼
Return Success Response
```

---

# 📒 Double-Entry Ledger

Every successful transfer generates two immutable ledger entries.

| Account | Entry |
|---------|-------|
| Sender | Debit |
| Receiver | Credit |

Account balances are computed dynamically instead of storing mutable balances.

```text
Balance = Total Credits − Total Debits
```

---

# 📡 REST API

## 🔐 Authentication

| Method | Endpoint | Description |
|--------|----------|-------------|
| POST | `/api/auth/register` | Register a new user |
| POST | `/api/auth/login` | Login user and generate JWT |
| POST | `/api/auth/logout` | Logout user and blacklist JWT |

---

## 🏦 Accounts

| Method | Endpoint | Description |
|--------|----------|-------------|
| POST | `/api/accounts/` | Create a new bank account |
| GET | `/api/accounts/` | Retrieve all accounts of the authenticated user |
| GET | `/api/accounts/balance/:accountId` | Retrieve current account balance |

---

## 💸 Transactions

| Method | Endpoint | Description |
|--------|----------|-------------|
| POST | `/api/transactions/` | Create a fund transfer transaction |
| POST | `/api/transactions/system/initial-funds` | Credit initial funds using the system account |

---

# 📂 Project Structure

```text
Bank_Transaction_System
│
├── src
│   ├── config
│   ├── controllers
│   ├── middleware
│   ├── models
│   ├── routes
│   ├── services
│   └── app.js
│
├── server.js
├── package.json
└── README.md
```

---

# 🚀 Getting Started

## Clone Repository

```bash
git clone https://github.com/SRAJAN1405/Bank_Transaction_System.git
```

## Navigate to Project

```bash
cd Bank_Transaction_System
```

## Install Dependencies

```bash
npm install
```

## Configure Environment Variables

Create a `.env` file in the root directory.

```env
PORT=5000

MONGO_URI=your_mongodb_connection_string

JWT_SECRET=your_jwt_secret

SYSTEM_EMAIL=your_email

SYSTEM_EMAIL_PASSWORD=your_email_password
```

## Start Development Server

```bash
npm run dev
```

---

# 🎯 Project Highlights

- Simulates secure banking workflows with atomic money transfers.
- Guarantees transaction consistency using MongoDB ACID transactions.
- Prevents duplicate fund transfers through idempotency keys.
- Maintains accurate balances using double-entry ledger accounting.
- Dynamically computes balances using MongoDB aggregation pipelines.
- Enhances authentication security with JWT token blacklisting and automatic TTL cleanup.

---

# 📚 Learning Outcomes

This project demonstrates backend engineering concepts commonly used in financial systems:

- Atomic transaction processing
- Ledger-based accounting
- MongoDB Sessions
- Aggregation Pipelines
- JWT Authentication
- Idempotent APIs
- Database consistency
- Scalable backend architecture

---

# 🤝 Contributing

Contributions, issues, and feature requests are welcome.

Feel free to fork the repository and submit a pull request.

---

# ⭐ Support

If you found this project useful, consider giving it a **⭐ Star** on GitHub.

---

# 📄 License

This project is intended for educational purposes and backend system design practice.
