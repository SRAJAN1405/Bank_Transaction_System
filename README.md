# 🏦 Bank Transaction System

A production-inspired backend banking system built with **Node.js**, **Express.js**, **MongoDB**, and **Mongoose**. This project demonstrates how modern banking applications ensure **secure**, **consistent**, and **reliable** money transfers using **ACID transactions**, **double-entry ledger accounting**, and **idempotent APIs**.

---

## ✨ Features

- 🔐 JWT Authentication & Authorization
- 👤 User Registration & Login
- 🏦 Bank Account Management
- 💸 Secure Money Transfer
- 📒 Double Entry Ledger System
- 🔄 MongoDB ACID Transactions
- 🛡️ Idempotent Transaction Handling
- 🚫 JWT Token Blacklisting (Logout Support)
- ⏳ Automatic Cleanup using MongoDB TTL Index
- 📊 Transaction History
- ⚡ Async Error Handling
- 📁 Modular MVC Architecture

---

## 🛠️ Tech Stack

| Technology | Usage |
|------------|-------|
| Node.js | Backend Runtime |
| Express.js | REST API Framework |
| MongoDB | Database |
| Mongoose | ODM |
| JWT | Authentication |
| bcrypt | Password Hashing |
| Express Validator | Request Validation |

---

# 📂 Project Structure

```text
Bank_Transaction_System/
│
├── controllers/
├── middleware/
├── models/
├── routes/
├── services/
├── utils/
├── config/
├── app.js
├── server.js
└── package.json
```

---

# 🔄 Money Transfer Workflow

```text
Client
   │
   ▼
Authenticate User
   │
   ▼
Validate Request
   │
   ▼
Check Idempotency Key
   │
   ▼
Start MongoDB Session
   │
   ▼
Create Transaction
   │
   ▼
Debit Sender
   │
   ▼
Credit Receiver
   │
   ▼
Create Ledger Entries
   │
   ▼
Commit Transaction
   │
   ▼
Return Success
```

---

# 📒 Double Entry Ledger

Every transaction creates **two ledger entries**.

Example:

Transfer ₹1000 from Alice to Bob

| Account | Entry Type | Amount |
|----------|------------|--------|
| Alice | Debit | ₹1000 |
| Bob | Credit | ₹1000 |

The account balance is calculated dynamically.

```text
Balance = Total Credits − Total Debits
```

---

# 🔄 MongoDB Transactions

The project uses **MongoDB Sessions** to guarantee ACID properties.

If any database operation fails:

- Debit is rolled back
- Credit is rolled back
- Ledger entries are rolled back
- Transaction record is rolled back

This ensures **all-or-nothing execution**.

---

# 🛡️ Idempotency

Each transfer request includes an **Idempotency Key**.

This prevents duplicate money transfers caused by:

- Network retries
- Double-clicking the transfer button
- Client timeouts

The same request is processed only once.

---

# 🔐 Authentication

- JWT Authentication
- Protected Routes
- Token Blacklisting
- Automatic blacklist cleanup using MongoDB TTL Index

---

# 📌 API Endpoints

## Authentication

```http
POST /api/auth/register
POST /api/auth/login
POST /api/auth/logout
```

## Account

```http
POST /api/accounts
GET /api/accounts
GET /api/accounts/:id
```

## Transactions

```http
POST /api/transactions/transfer
GET /api/transactions
GET /api/transactions/:id
```

---

# 🚀 Installation

## Clone Repository

```bash
git clone https://github.com/SRAJAN1405/Bank_Transaction_System.git
```

## Move into Project

```bash
cd Bank_Transaction_System
```

## Install Dependencies

```bash
npm install
```

## Create Environment Variables

Create a `.env` file.

```env
PORT=5000

MONGO_URI=your_mongodb_connection_string

JWT_SECRET=your_jwt_secret
```

## Run Server

```bash
npm run dev
```

---

# 📖 Concepts Implemented

- MongoDB Aggregation Pipeline
- MongoDB Sessions
- ACID Transactions
- Double Entry Accounting
- Idempotency Keys
- JWT Authentication
- Token Blacklisting
- MongoDB TTL Index
- Express Middleware
- Mongoose Schema Methods
- Async Error Handling
- MVC Architecture

---

# 🎯 Learning Outcomes

This project demonstrates real-world backend engineering concepts used in financial systems, including:

- Secure money transfers
- Reliable transaction processing
- Preventing duplicate financial operations
- Ledger-based accounting
- MongoDB transaction management
- JWT-based authentication
- Scalable backend architecture

---

# 🤝 Contributing

Contributions, issues, and feature requests are welcome!

If you'd like to improve this project, feel free to fork the repository and submit a pull request.

---

# ⭐ Support

If you found this project helpful, consider giving it a ⭐ on GitHub!

---

# 📜 License

This project is developed for educational purposes and backend system design practice.
