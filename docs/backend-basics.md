# Backend Basics – SecureMail Project

## 1. What is Backend?
Backend is the part of a web application that runs on a server and handles
logic, data, and security. It is responsible for processing requests coming
from the frontend and sending responses back.

The backend is not visible to the user and cannot be accessed directly
from the browser UI.

---

## 2. What is a Server?
A server is a computer or program that is always running and listens for
incoming requests from clients (frontend or browser).

In web development, a backend application (like Node.js with Express)
acts as a server.

---

## 3. Frontend vs Backend
Frontend:
- Runs in the browser
- Handles UI and user interaction
- Sends requests to backend

Backend:
- Runs on a server
- Handles authentication, logic, and data
- Communicates with the database
- Sends responses to frontend

Frontend should never directly access the database.

---

## 4. What is Request and Response?
Request:
- Data sent from frontend to backend
- Example: email and password during login

Response:
- Data sent from backend to frontend
- Example: success message or error message

Backend always works in this flow:
Request → Logic → Response

---

## 5. What is an API?
API (Application Programming Interface) is an endpoint (URL) provided
by the backend that frontend can call to perform actions.

Examples:
- POST /login
- GET /messages
- POST /send-message

Each API does one specific task.

---

## 6. Why Frontend Alone is Not Enough
Frontend code runs in the browser and can be seen or modified by users.
If authentication or logic is written only in frontend, it is insecure.

Backend is required to:
- Protect passwords
- Validate users
- Secure data
- Control access

---

## 7. Backend Role in SecureMail Project
In SecureMail, backend will:
- Handle user authentication
- Store encrypted messages
- Manage inbox and conversations
- Never read message content (end-to-end encryption)

Frontend will:
- Show UI
- Encrypt messages before sending
- Decrypt messages after receiving

---

## Conclusion
Backend is the core of any secure and scalable application.
It ensures data safety, correct logic, and proper communication
between frontend and database.
