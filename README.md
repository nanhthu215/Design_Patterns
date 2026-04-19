# ☕ Coffee Shop - Architectural Design Patterns Defense

[![Design Patterns](https://img.shields.io/badge/Design%20Patterns-6%20Implemented-blueviolet?style=for-the-badge)](https://github.com/nanhthu215/Design_Patterns_Final)
[![React](https://img.shields.io/badge/Frontend-React.js-61DAFB?style=for-the-badge&logo=react)](https://reactjs.org/)
[![Node.js](https://img.shields.io/badge/Backend-Node.js-339933?style=for-the-badge&logo=nodedotjs)](https://nodejs.org/)
[![MongoDB](https://img.shields.io/badge/Database-MongoDB-47A248?style=for-the-badge&logo=mongodb)](https://www.mongodb.com/)

> **Academic Final Project**: An advanced E-Commerce platform built with a focus on robust software architecture and deep integration of GOF Design Patterns.

---

## 🏛️ Architectural Overview

This project is a dedicated demonstration of how **Design Patterns** solve real-world software engineering challenges in an E-Commerce context. It moves beyond simple CRUD operations to provide a scalable, pluggable, and maintainable codebase.

### The 6 Core Patterns

| Pattern | Application Area | Key Benefit |
| :--- | :--- | :--- |
| **🏗️ Factory** | Product Creation & Enrichment | Extensible product lines without code mutation. |
| **💍 Singleton** | Unified Cart Management | Single Source of Truth for shared application state. |
| **🔔 Observer** | Real-time UI & WebSocket Sync | Decoupled notifications and cross-tab concurrency. |
| **🎯 Strategy** | Payment Gateway & Data Export | Pluggable algorithms for checkout and reporting. |
| **🔌 Adapter** | Infrastructure Abstraction | Vendor-agnostic storage (LocalStorage/Mongoose). |
| **🗄️ Repository** | Data Access Layer | Domain-centric data fetching decoupled from DB. |

---

## 📂 Design Pattern Matrix (File Mapping)

| Pattern | Implementation File | Location |
| :--- | :--- | :--- |
| **Factory** | `ProductFactory.js`, `Product.js` | `src/backend/patterns/factory/` |
| **Singleton** | `Singleton.js`, `CartService.js` | `src/backend/patterns/singleton/` |
| **Observer** | `Observer.js`, `ReviewObserver.js` | `src/backend/patterns/observer/` |
| **Strategy** | `PaymentProcessor.js`, `DataExportService.js` | `src/backend/patterns/strategy/` |
| **Adapter** | `MongooseRepositoryAdapter.js`, `Storage.js` | `src/backend/patterns/adapter/` |
| **Repository** | `ProductRepository.js`, `OrderRepository.js` | `src/backend/repositories/` |

---

## 🚀 Key Technical Features

### 1. Dynamic Product Enrichment (Factory)
The system automatically generates SKU prefixes (`COF-`, `ACC-`, `CMB-`) and category-specific attributes at runtime based on the product type.

### 2. Multi-Tab Cart Synchronization (Singleton + Observer)
Leverages a **Registry-based Singleton** in the frontend to ensure all open browser tabs reflect the same cart state in real-time when changes occur in any tab.

### 3. Pluggable Payment & Export (Strategy)
Adding a new payment method (e.g., Crypto) or a new export format (e.g., JSON) requires only a new Strategy subclass—no existing business logic is modified (**Open/Closed Principle**).

### 4. Database Agnostic Data Layer (Repository + Adapter)
Business logic interacts only with Repositories. Switching from MongoDB to PostgreSQL would only require updating the **Adapter** implementation.

---

## 🛠️ Technology Stack

- **Frontend**: React.js with Context API & Framer Motion for animations.
- **Backend**: Node.js & Express.js.
- **Database**: MongoDB (Mongoose ODM).
- **Patterns**: Custom ES6 Classes for Pattern implementations.
- **Communication**: WebSockets for real-time review broadcasting.

---

## 💻 Installation & Setup

### Prerequisites
- Node.js (v16+)
- MongoDB (Running locally or via Atlas)

### 1. Clone & Install
```bash
git clone https://github.com/nanhthu215/Design_Patterns_Final.git
cd Design_Patterns_Final
npm install
```

### 2. Configure Environment
Create a `.env` file in the root directory:
```env
PORT=5000
MONGODB_URI=your_mongodb_uri
JWT_SECRET=your_secret_key
```

### 3. Run the Application
```bash
# Start Backend
npm run server

# Start Frontend
cd frontend
npm start
```

---

## 🎓 Academic Defense Notes

This project was built to demonstrate proficiency in:
- **SOLID Principles** (Specifically OCP and SRP).
- **Loose Coupling** through Object-Oriented Design.
- **Real-time Synchronization** mechanisms.
- **Generic Programming** in JavaScript (Singleton Utility).

---

**Author**: `nanhthu215`  
**Project**: Design Patterns Final Examination  
**Status**: 🏆 Production Ready for Defense