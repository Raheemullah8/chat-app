# 🚀 Deployment Guide

## Step 1: Backend Deploy (Vercel)

1. Push backend folder to GitHub
2. Go to vercel.com → Import Project
3. Select backend repository
4. Add Environment Variables:
   - `MONGO_URI` = your MongoDB connection string
   - `JWT_SECRET` = your secret key
   - `FRONTEND_URL` = (add after frontend is deployed)
   - `NODE_ENV` = production
5. Deploy
6. Copy your backend URL

## Step 2: Frontend Deploy (Vercel)

1. Update `frontend/.env.production`:
   ```
   VITE_API_BASE_URL=<your-backend-url>
   VITE_SOCKET_URL=<your-backend-url>
   VITE_CLOUDINARY_CLOUD_NAME=<your-cloudinary-name>
   ```

2. Push frontend to GitHub
3. Go to vercel.com → Import Project
4. Select frontend repository
5. Framework: Vite
6. Build: `npm run build`
7. Output: `dist`
8. Add same environment variables from .env.production
9. Deploy

## Step 3: Update Backend CORS

1. Go back to backend project in Vercel
2. Update `FRONTEND_URL` with your deployed frontend URL
3. Redeploy

Done! ✅
