# 💬 MERN Chat App - WhatsApp Clone

A full-stack real-time chat application built with MERN stack (MongoDB, Express, React, Node.js) and Socket.io.

## ✨ Features

- 🔐 User Authentication (Register/Login with JWT)
- 💬 Real-time Messaging with Socket.io
- 👥 One-on-One Chat
- 👨‍👩‍👧‍👦 Group Chat Creation
- 📱 Fully Responsive Design (Mobile, Tablet, Desktop)
- 🌓 Light/Dark Theme Toggle
- 😀 Emoji Picker
- 📎 File Upload (Images, Videos)
- ✅ Online/Offline Status
- 🔔 Message Notifications
- ⌨️ Typing Indicators
- 🎨 Material-UI Design

## 🛠️ Tech Stack

### Frontend
- React 19
- Material-UI (MUI)
- Socket.io-client
- Axios
- React Router
- Emoji Picker React
- Moment.js

### Backend
- Node.js
- Express.js
- MongoDB with Mongoose
- Socket.io
- JWT Authentication
- Bcrypt.js

## 📋 Prerequisites

- Node.js (v16+)
- MongoDB (Atlas or Local)
- Cloudinary Account (for file uploads)

## 🚀 Installation

### 1. Clone the repository
```bash
git clone <your-repo-url>
cd mern-chat-app
```

### 2. Backend Setup
```bash
cd backend
npm install

# Create .env file
cp .env.example .env
```

Edit `backend/.env`:
```env
PORT=5001
MONGO_URI=your_mongodb_connection_string
JWT_SECRET=your_jwt_secret_key
FRONTEND_URL=http://localhost:5173
NODE_ENV=development
```

### 3. Frontend Setup
```bash
cd frontend
npm install

# Create .env file
cp .env.example .env
```

Edit `frontend/.env`:
```env
VITE_API_BASE_URL=http://localhost:5001
VITE_SOCKET_URL=http://localhost:5001
VITE_CLOUDINARY_CLOUD_NAME=your_cloudinary_cloud_name
```

### 4. Run the Application

**Backend** (Terminal 1):
```bash
cd backend
npm run dev
```

**Frontend** (Terminal 2):
```bash
cd frontend
npm run dev
```

Application will run on:
- Frontend: http://localhost:5173
- Backend: http://localhost:5001

## 📦 Deployment

See [DEPLOYMENT.md](./DEPLOYMENT.md) for detailed deployment instructions on Vercel.

### Quick Deploy

**Backend on Vercel:**
```bash
cd backend
vercel --prod
```

**Frontend on Vercel:**
```bash
cd frontend
npm run build
vercel --prod
```

⚠️ **Note**: For production Socket.io, consider using Railway.app or Render.com for backend instead of Vercel.

## 🌐 Environment Variables

### Backend Variables
| Variable | Description | Example |
|----------|-------------|---------|
| `MONGO_URI` | MongoDB connection string | `mongodb+srv://...` |
| `JWT_SECRET` | Secret key for JWT | `your_secret_key` |
| `FRONTEND_URL` | Frontend URL for CORS | `http://localhost:5173` |
| `PORT` | Server port | `5001` |

### Frontend Variables
| Variable | Description | Example |
|----------|-------------|---------|
| `VITE_API_BASE_URL` | Backend API URL | `http://localhost:5001` |
| `VITE_SOCKET_URL` | Socket.io server URL | `http://localhost:5001` |
| `VITE_CLOUDINARY_CLOUD_NAME` | Cloudinary cloud name | `your_cloud_name` |

## 📱 Features Demo

### Authentication
- Secure user registration and login
- JWT token-based authentication
- Protected routes

### Messaging
- Real-time message delivery
- Send text, images, and videos
- Emoji support
- Message timestamps

### User Interface
- Clean, modern WhatsApp-inspired design
- Responsive layout for all devices
- Dark mode support
- Smooth animations

### Chat Management
- Create group chats (3+ members)
- Search users
- View online status
- Message notifications

## 🗂️ Project Structure

```
mern-chat-app/
├── backend/
│   ├── config/
│   │   └── db.js
│   ├── controllers/
│   │   ├── authController.js
│   │   ├── chatController.js
│   │   └── userController.js
│   ├── middleware/
│   │   └── authMiddleware.js
│   ├── models/
│   │   ├── User.js
│   │   ├── Chat.js
│   │   └── Message.js
│   ├── routes/
│   │   ├── authRoutes.js
│   │   ├── chatRoutes.js
│   │   └── userRoutes.js
│   ├── server.js
│   ├── package.json
│   └── vercel.json
│
└── frontend/
    ├── src/
    │   ├── components/
    │   │   ├── Chat/
    │   │   │   └── ChatBox.jsx
    │   │   └── Sidebar/
    │   │       └── Sidebar.jsx
    │   ├── context/
    │   │   └── ChatContext.jsx
    │   ├── pages/
    │   │   ├── Home.jsx
    │   │   └── Login.jsx
    │   ├── App.jsx
    │   ├── main.jsx
    │   └── App.css
    ├── package.json
    └── vercel.json
```

## 🐛 Troubleshooting

### CORS Issues
- Verify `FRONTEND_URL` in backend `.env`
- Check URLs don't have trailing slashes

### Socket.io Connection Failed
- Ensure backend is running
- Check Socket.io URL in frontend
- For Vercel, consider alternative hosting

### MongoDB Connection Error
- Verify MongoDB URI is correct
- Check network access in MongoDB Atlas
- Ensure database user has permissions

## 🤝 Contributing

1. Fork the repository
2. Create your feature branch (`git checkout -b feature/AmazingFeature`)
3. Commit your changes (`git commit -m 'Add some AmazingFeature'`)
4. Push to the branch (`git push origin feature/AmazingFeature`)
5. Open a Pull Request

## 📄 License

This project is licensed under the MIT License.

## 👨‍💻 Author

Your Name

## 🙏 Acknowledgments

- Material-UI for the component library
- Socket.io for real-time communication
- MongoDB for the database
- Vercel for hosting

---

Made with ❤️ using MERN Stack
