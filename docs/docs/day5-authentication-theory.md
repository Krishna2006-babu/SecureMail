# Day 5 – Authentication Theory (Password Hashing & JWT)
**Project:** SecureMail  
**Focus:** Secure Authentication Fundamentals

This document explains the **theoretical concepts** learned on Day 5.
No implementation details are assumed here — only *why* things are done
and *how authentication works conceptually*.

---

## 1. Why Authentication Is Required
Authentication is the process of verifying **who a user is**.

Without authentication:
- Anyone can access protected APIs
- User data is exposed
- There is no identity or security

Every real-world backend must authenticate users before granting access.

---

## 2. Why Passwords Must Never Be Stored in Plain Text
Storing passwords as plain text is a critical security vulnerability.

If a database is compromised:
- All user passwords are immediately exposed
- Users often reuse passwords across platforms
- This can lead to large-scale account compromise

### Rule:
> **A backend should never know or store a user’s actual password.**

---

## 3. What Is Password Hashing?
Password hashing is the process of converting a password into a
**one-way, irreversible string**.

Example:password123 → $2b$10$9Sdf8F...Xz


Key properties:
- Hashes cannot be reversed
- Same password produces same hash (with salt)
- Original password cannot be retrieved

---

## 4. What Is bcrypt and Why It Is Used
`bcrypt` is a password hashing algorithm designed for security.

Why bcrypt is preferred:
- Slow by design (resists brute-force attacks)
- Uses salting automatically
- Industry standard for password storage

### Important Concept: Salt Rounds
Salt rounds determine how computationally expensive hashing is.
- Higher rounds = more secure, slower
- Common standard: **10 rounds**

---

## 5. Password Verification (Login Time)
During login:
- The entered password is **never compared directly**
- Instead, it is hashed again
- The hash is compared with the stored hash

This ensures:
- Backend never stores or compares raw passwords
- Even developers cannot see user passwords

---

## 6. What Is JWT (JSON Web Token)?
JWT is a **digitally signed token** that represents an authenticated user.

JWT allows the backend to say:
> “This user has already proven who they are.”

A JWT contains:
- Payload (user data)
- Signature (ensures integrity)
- Expiry time

JWTs are:
- Stateless
- Compact
- Secure when used correctly

---

## 7. Why JWT Is Needed After Login
Without JWT:
- User would need to send email & password on every request
- This is insecure and inefficient

With JWT:
- User logs in once
- Backend issues a token
- Token is sent with each protected request

---

## 8. JWT Authentication Flow (High Level)
User enters credentials
↓
Frontend sends login request
↓
Backend verifies credentials
↓
Backend generates JWT
↓
Frontend stores JWT
↓
Frontend sends JWT with each request
↓
Backend verifies JWT
↓
Access granted or denied


This is known as **stateless authentication**.

---

## 9. What Is Stateless Authentication?
Stateless authentication means:
- Backend does NOT store session data
- Each request is verified independently
- JWT contains all required verification data

Benefits:
- Scalable
- Simple
- No server-side session storage

---

## 10. JWT Expiry and Security
JWTs always have an expiration time.

Why expiry is important:
- Limits damage if token is stolen
- Forces re-authentication
- Improves security

Expired tokens are automatically rejected.

---

## 11. What Is a Protected Route?
A protected route is an API endpoint that:
- Requires authentication
- Rejects unauthenticated users
- Is accessible only with a valid JWT

Examples:
- User profile
- Inbox
- Messages
- Settings

---

## 12. Authentication Middleware Concept
Authentication logic should not be repeated in every route.

Middleware:
- Runs before route handlers
- Verifies JWT
- Allows or blocks access

This ensures:
- Clean code
- Centralized security
- Consistent behavior

---

## 13. HTTP Status Codes in Authentication
Correct status codes are essential for clarity.

Common codes:
- `400` – Bad request (invalid input)
- `401` – Unauthorized (missing token / wrong credentials)
- `403` – Forbidden (invalid or expired token)
- `200` – Success

Using proper status codes improves debugging and API clarity.

---

## 14. Security Principles Learned on Day 5
- Never trust frontend input
- Never store plain passwords
- Always hash passwords
- Use tokens instead of sessions
- Protect routes using middleware
- Use expiry for authentication tokens

---

## 15. Why These Concepts Matter in Real Projects
These authentication concepts are used in:
- Banking systems
- Social media platforms
- Enterprise applications
- Secure messaging apps

Without these principles:
- Applications are insecure
- User data is at risk
- Backend is not production-ready

---

## Conclusion
Day 5 established the **core security foundation** of the SecureMail project.

Password hashing and JWT-based authentication ensure:
- Secure user identity
- Safe access to protected resources
- Scalable and professional backend design

These concepts are fundamental to real-world backend development.


