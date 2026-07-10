# Chat-App — Real-Time Chat Application

[![React](https://img.shields.io/badge/React-19-black?style=for-the-badge&logo=react)](https://react.dev/)
[![Vite](https://img.shields.io/badge/Vite-Build-646CFF?style=for-the-badge&logo=vite)](https://vitejs.dev/)
[![Tailwind CSS](https://img.shields.io/badge/Tailwind-CSS-06B6D4?style=for-the-badge&logo=tailwindcss)](https://tailwindcss.com/)
[![Node.js](https://img.shields.io/badge/Node.js-Express-339933?style=for-the-badge&logo=node.js)](https://nodejs.org/)
[![Socket.io](https://img.shields.io/badge/Socket.io-Realtime-010101?style=for-the-badge&logo=socket.io)](https://socket.io/)
[![MongoDB](https://img.shields.io/badge/MongoDB-Database-47A248?style=for-the-badge&logo=mongodb)](https://www.mongodb.com/)
[![Render](https://img.shields.io/badge/Deployed-Render-46E3B7?style=for-the-badge&logo=render)](https://chat-app-p35t.onrender.com)

> A full-stack real-time chat application featuring secure custom authentication, instant messaging, live online/offline presence, and seamless media sharing — all built from the ground up with a smooth, modern interface.

🔗 **Live Demo:** [chat-app-p35t.onrender.com](https://chat-app-p35t.onrender.com)

---

## 📸 Screenshots

### 🔐 Login Page
![Login Page](https://github.com/amesharawat/Chat-App/blob/eddd35e0318d9aabbbc54c1c840717582043cf07/Screenshot%20(1029).png)

### 📝 Sign Up Page
![Sign Up Page](https://github.com/amesharawat/Chat-App/blob/88021466485d263ab8728a3df90a7a7f574d6211/Screenshot%20(1032).png)

### 💬 Chat Interface
![Chat Interface](PASTE_CHAT_INTERFACE_SCREENSHOT_URL_HERE)

### 📇 Contacts / Select Conversation View
![Contacts View](PASTE_CONTACTS_SCREENSHOT_URL_HERE)

---

## ✨ Application Features

- 🔐 **Custom Authentication System** — Built entirely from scratch using hashed passwords (via Bcrypt) and secure, HTTP-only cookies storing JWTs for session management
- 📧 **Automated Welcome Emails** — Triggers a background transactional welcome email to a user's inbox upon successful registration using the Resend API
- 💬 **Real-Time Messaging** — Delivers persistent, instant messages between online clients via Socket.io, with no manual page refresh required
- ⚡ **Optimistic UI Updates** — Renders sent messages on screen immediately for a fluid experience, before the server confirms storage
- 🟢 **Live Online/Offline Status Indicators** — Shows a dynamic status badge for each contact, tracked in real time through Socket.io connection state
- 🖼️ **Dynamic Media Uploads** — Supports profile picture customization and in-chat image sharing, with files uploaded directly to Cloudinary
- 🔊 **Interactive Audio Feedback** — Includes toggleable sound effects for typing and incoming messages
- 🛡️ **API Security Shield & Rate Limiting** — Uses Arcjet to cap traffic at 100 requests/minute and guard against bot activity and basic injection attacks
- 🗂️ **Dynamic UI Layouts** — Tab-based switching between chat threads and contacts, with auto-scroll to the latest message

---

## 🛠️ Tech Stack

| Category | Technology |
|----------|------------|
| **Frontend Framework** | React (Vite) |
| **Styling** | Tailwind CSS, Daisy UI |
| **State Management** | Zustand |
| **HTTP Client** | Axios |
| **Icons** | Lucide React |
| **Notifications** | React Hot Toast |
| **Backend** | Node.js, Express |
| **Real-Time Engine** | Socket.io, Socket.io-Client |
| **Database** | MongoDB (Mongoose ODM) |
| **Authentication** | JSON Web Tokens (JWT), HTTP-only Cookies |
| **Password Hashing** | BcryptJS |
| **Security** | Arcjet (Rate Limiting, Bot & Attack Protection) |
| **Email** | Resend |
| **Media Storage** | Cloudinary |
| **Deployment** | Render |

---

## 🚀 Getting Started

### Prerequisites

- Node.js 18+
- A MongoDB Atlas account
- A Cloudinary account
- A Resend account
- An Arcjet account

### Installation

**1. Clone the repository**

```bash
git clone https://github.com/amesharawat/Chat-App.git
cd Chat-App
```

**2. Install dependencies**

```bash
cd backend
npm install

cd ../frontend
npm install
```

**3. Set up environment variables**

Create a `.env` file inside the `backend` folder with the following:

```env
# Server
PORT=5001
NODE_ENV=development

# MongoDB
MONGO_URI=your_mongodb_connection_string

# JWT
JWT_SECRET=your_jwt_secret

# Cloudinary
CLOUDINARY_CLOUD_NAME=your_cloudinary_cloud_name
CLOUDINARY_API_KEY=your_cloudinary_api_key
CLOUDINARY_API_SECRET=your_cloudinary_api_secret

# Resend
RESEND_API_KEY=your_resend_api_key

# Arcjet
ARCJET_KEY=your_arcjet_key

# Frontend URL (for CORS)
CLIENT_URL=http://localhost:5173
```

**4. Run the backend server**

```bash
cd backend
npm run dev
```

**5. Run the frontend**

_(in a separate terminal)_

```bash
cd frontend
npm run dev
```

Open [http://localhost:5173](http://localhost:5173) to view the app.

---

## 📁 Project Structure

```
Chat-App/
├── backend/
│ ├── src/
│ │ ├── controllers/ # auth.controller.js, message.controller.js
│ │ ├── emails/ # emailHandlers.js, emailTemplates.js
│ │ ├── lib/ # arcjet.js, cloudinary.js, db.js, env.js, resend.js, socket.js, utils.js
│ │ ├── middleware/ # arcjet.middleware.js, auth.middleware.js, socket.auth.middleware.js
│ │ ├── models/ # User.js, Message.js
│ │ ├── routes/ # auth.route.js, message.route.js
│ │ └── server.js
│ ├── package.json
│ └── package-lock.json
├── frontend/
│ ├── public/
│ │ ├── sounds/
│ │ ├── avatar.png
│ │ ├── favicon.svg
│ │ ├── icons.svg
│ │ ├── login.png
│ │ └── signup.png
│ ├── src/
│ │ ├── components/ # ActiveTabSwitch, BorderAnimatedContainer, ChatContainer, ChatHeader, ChatsList, ContactList, etc.
│ │ ├── pages/ # ChatPage.jsx, LoginPage.jsx, SignUpPage.jsx
│ │ ├── store/ # useAuthStore.js, useChatStore.js
│ │ ├── App.jsx
│ │ ├── index.css
│ │ └── main.jsx
│ ├── index.html
│ ├── package.json
│ ├── tailwind.config.js
│ └── vite.config.js
├── .gitignore
└── package.json
```

---

## 🌐 Deployment

This project is deployed on **Render**. To deploy your own instance:

1. Push your code to GitHub
2. Create a new Web Service on [render.com](https://render.com) for the backend
3. Create a Static Site (or Web Service) for the frontend
4. Add all required environment variables in Render's dashboard
5. Deploy

---

## 📬 Contact

**Amesha Rawat**
- GitHub: [@amesharawat](https://github.com/amesharawat)
- Repo: [github.com/amesharawat/Chat-App](https://github.com/amesharawat/Chat-App)
- Live Project: [chat-app-p35t.onrender.com](https://chat-app-p35t.onrender.com)
