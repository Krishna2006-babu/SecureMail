# 📦 SecureMail – Day 6  
## Database Integration (MongoDB with Mongoose)

---

## 📌 Overview

Day 6 focuses on integrating a **real database** into the SecureMail backend.  
This step converts the backend from a temporary, in-memory system into a **persistent, production-ready application**.

By the end of Day 6:
- User data is permanently stored
- Authentication uses real database records
- Backend follows industry-standard architecture

---

## 🎯 Objectives of Day 6

- Integrate MongoDB with Node.js
- Use Mongoose for schema and data modeling
- Store users securely in the database
- Load sensitive configuration using environment variables
- Run MongoDB using Docker for reliability

---

## ❓ Why Database Integration Is Necessary

Before database integration:
- User data existed only in memory
- Server restart caused complete data loss
- Application was not production-ready

After database integration:
- Data persists across server restarts
- Authentication becomes reliable
- Messaging and inbox features become possible

> **Database integration is the backbone of any real-world backend application.**

---

## 🗄️ Why MongoDB?

MongoDB is a **NoSQL, document-based database**.

### Key Advantages:
- Stores data in JSON-like documents
- Flexible schema design
- Scales easily
- Works naturally with JavaScript (Node.js)

### Example MongoDB Document

```json
{
  "_id": "64ab12...",
  "name": "Krishna",
  "email": "krishna@gmail.com",
  "password": "$2a$10$hashedPassword",
  "createdAt": "2025-01-01T10:00:00Z"
}
