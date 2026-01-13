# MERN Chat App - Deployment Guide

## 📋 Prerequisites
1. Vercel Account (https://vercel.com)
2. MongoDB Atlas Account (https://www.mongodb.com/cloud/atlas)
3. Cloudinary Account (https://cloudinary.com)

## 🚀 Backend Deployment (Vercel)

### Step 1: Setup MongoDB Atlas
1. Create a MongoDB Atlas cluster
2. Get your connection string
3. Whitelist all IPs (0.0.0.0/0) for Vercel

### Step 2: Deploy Backend
1. Go to Vercel dashboard
2. Import your backend folder as a new project
3. Set Environment Variables in Vercel:
   ```
   MONGO_URI=your_mongodb_atlas_connection_string
   JWT_SECRET=your_secret_key_here
   FRONTEND_URL=https://your-frontend-url.vercel.app
   NODE_ENV=production
   PORT=5001
   ```
4. Deploy!
5. Copy your backend URL (e.g., https://your-backend.vercel.app)

## 🎨 Frontend Deployment (Vercel)

### Step 1: Update Environment Variables
1. Update `frontend/.env.production` with your backend URL:
   ```
   VITE_API_BASE_URL=https://your-backend-url.vercel.app
   VITE_SOCKET_URL=https://your-backend-url.vercel.app
   VITE_CLOUDINARY_CLOUD_NAME=your_cloudinary_name
   ```

### Step 2: Deploy Frontend
1. Go to Vercel dashboard
2. Import your frontend folder as a new project
3. Set Build Settings:
   - Framework Preset: Vite
   - Build Command: `npm run build`
   - Output Directory: `dist`
4. Set Environment Variables in Vercel:
   ```
   VITE_API_BASE_URL=https://your-backend-url.vercel.app
   VITE_SOCKET_URL=https://your-backend-url.vercel.app
   VITE_CLOUDINARY_CLOUD_NAME=your_cloudinary_name
   ```
5. Deploy!

### Step 3: Update Backend CORS
1. Go back to backend Vercel project
2. Update FRONTEND_URL environment variable with your deployed frontend URL
3. Redeploy backend

## 📝 Important Notes

### Socket.io on Vercel
⚠️ **Important**: Vercel has limitations with WebSocket connections. For production Socket.io, consider:
- Using Vercel's Serverless Functions with polling fallback
- Or deploy backend on Railway/Render/Heroku for better WebSocket support

### Alternative Backend Hosting (Recommended for Socket.io)
**Railway.app** (Recommended):
1. Create Railway account
2. Import backend repository
3. Add environment variables
4. Deploy
5. Update frontend environment variables with Railway URL

**Render.com**:
1. Create Render account
2. New Web Service
3. Connect repository
4. Add environment variables
5. Deploy

## 🧪 Testing
1. Open frontend URL
2. Register a new user
3. Login
4. Create a chat
5. Send messages
6. Test on mobile device

## 🔧 Troubleshooting

### Issue: CORS errors
- Check FRONTEND_URL in backend env variables
- Ensure URLs don't have trailing slashes

### Issue: Socket.io not connecting
- Consider alternative hosting for backend (Railway/Render)
- Check browser console for WebSocket errors

### Issue: MongoDB connection failed
- Verify MongoDB Atlas IP whitelist
- Check connection string format
- Ensure database user has read/write permissions

## 📦 Local Development
```bash
# Backend
cd backend
npm install
npm run dev

# Frontend
cd frontend
npm install
npm run dev
```

## 🌐 Environment Variables Summary

### Backend (.env)
- `MONGO_URI` - MongoDB connection string
- `JWT_SECRET` - Secret key for JWT
- `FRONTEND_URL` - Frontend URL (for CORS)
- `PORT` - Server port (5001)

### Frontend (.env)
- `VITE_API_BASE_URL` - Backend API URL
- `VITE_SOCKET_URL` - Socket.io server URL
- `VITE_CLOUDINARY_CLOUD_NAME` - Cloudinary cloud name

## 🎯 Quick Deploy Commands

### Backend
```bash
cd backend
vercel --prod
```

### Frontend
```bash
cd frontend
npm run build
vercel --prod
```

---
Good luck with your deployment! 🚀
