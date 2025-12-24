What have we built till Day 6?

👉 A secure backend that can:

Register users

Store users in database

Login users

Generate JWT tokens

Protect routes using JWT

Persist data using MongoDB (Docker)

//env file use
<img width="841" height="759" alt="image" src="https://github.com/user-attachments/assets/9247821e-9dba-4c6b-a5d3-f2f199b1f93d" />

//auth.js
5️⃣ routes/auth.js — Register & Login Logic

📍 backend/routes/auth.js

This file handles authentication.

🔹 REGISTER FLOW
router.post("/register", ...)

What happens:

User sends name, email, password

Backend validates input

Checks if user already exists

Hashes password

Saves user in MongoDB

Why hash password?

❌ Plain password = dangerous
✔ Hashed password = secure

🔹 LOGIN FLOW
router.post("/login", ...)

What happens:

User sends email & password

Backend finds user in DB

Compares hashed password

Generates JWT token

Sends token to frontend

Why JWT?

Stateless authentication

No session storage

Scales well

🧠 auth.js in one line:

“Handles user authentication securely.”
