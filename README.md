![Real-Time Chat Application Logo](https://github.com/user-attachments/assets/9cb181b1-67a0-4386-afd6-b3887f787874)
# Real-Time Chat Application

## Overview
A full-stack real-time chat application that enables users to communicate instantly with each other. The platform features user authentication, real-time messaging using Socket.IO, profile management with image uploads, online user status, and a modern, responsive user interface. Built with the MERN stack and deployed on Render and Netlify.

## Table of Contents
* **About the Project**
  * **Features**
  * **Screenshots**
  * **Demo**
  * **Live Demo**
  * **Tech Stack**
* **Getting Started**
  * **Prerequisites**
  * **Installation**
    * **Clone Project**
    * **Backend Setup**
    * **Frontend Setup**
  * **Configuration**
* **Usage**
* **Contact**

## About the Project

### Features
* **User Authentication**: Secure signup and login with JWT-based authentication
* **Real-Time Messaging**: Instant message delivery using Socket.IO
* **Online Status**: See which users are currently online
* **Profile Management**: Update profile pictures with Cloudinary integration
* **Image Sharing**: Send images in chat conversations
* **Responsive Design**: Fully responsive UI that works on all devices
* **Message History**: Persistent message storage with MongoDB
* **Cookie-Based Sessions**: Secure session management with HTTP-only cookies
* **Toast Notifications**: Real-time feedback for user actions

### Screenshots
![Signup Page](https://github.com/user-attachments/assets/c109fb2f-c932-4913-b27c-40980ee836cd)

![Login Page](https://github.com/user-attachments/assets/dfa226ed-e488-4e2b-84a8-47bfbd574db7)

![Chat Interface](https://github.com/user-attachments/assets/772d37d0-8890-4d3d-bb85-a362a7759165)


![Profile Page](https://github.com/user-attachments/assets/067aa387-ebfb-489f-9309-3ed1990bc25a)

### Demo
https://github.com/user-attachments/assets/f8b67f32-6337-466e-a743-ae77186acaf3

### Live Demo
**[Click here for live demo](https://frolicking-zabaione-b66282.netlify.app/)**

### Tech Stack
* **Frontend**: React, Vite, Tailwind CSS
* **State Management**: Zustand
* **Backend**: Node.js, Express.js
* **Real-Time Communication**: Socket.IO
* **Database**: MongoDB with Mongoose
* **Authentication**: JWT (JSON Web Tokens)
* **File Upload**: Cloudinary
* **Password Hashing**: bcrypt
* **HTTP Client**: Axios
* **Notifications**: React Hot Toast
* **Deployment**: 
  * Backend: Render
  * Frontend: Netlify

## Getting Started

### Prerequisites
* **Node.js**: Install Node.js from [here](https://nodejs.org/)
* **MongoDB Atlas Account**: Set up a MongoDB database [here](https://www.mongodb.com/cloud/atlas)
* **Cloudinary Account**: Sign up for Cloudinary [here](https://cloudinary.com/)

### Installation

#### Clone Project
```bash
git clone https://github.com/Riddhi-chavan/chat_app.git
cd chat_app
```

#### Backend Setup

1. Navigate to the backend directory:
```bash
cd backend
```

2. Install the dependencies:
```bash
npm install
```

3. Set up environment variables:
   * Create a `.env` file in the backend directory and add the following:
```env
MONGO_URI=your-mongodb-connection-string
JWT_SECRET=your-jwt-secret-key
CLOUDINARY_CLOUD_NAME=your-cloudinary-cloud-name
CLOUDINARY_API_KEY=your-cloudinary-api-key
CLOUDINARY_API_SECRET=your-cloudinary-api-secret
NODE_ENV=development
FRONTEND_URL=http://localhost:5173
PORT=5001
```

4. Start the backend server:
```bash
npm run dev
```

The backend will run on `http://localhost:5001`

#### Frontend Setup

1. Navigate to the frontend directory:
```bash
cd ../frontend
```

2. Install the dependencies:
```bash
npm install
```

3. Set up environment variables:
   * Create a `.env` file in the frontend directory and add the following:
```env
VITE_API_URL=http://localhost:5001
```

4. Start the frontend development server:
```bash
npm run dev
```

The frontend will run on `http://localhost:5173`

### Configuration

#### MongoDB Setup
1. Create a MongoDB Atlas cluster
2. Whitelist your IP address (or use `0.0.0.0/0` for development)
3. Create a database user with read/write permissions
4. Get your connection string and add it to the `MONGO_URI` in your `.env` file

#### Cloudinary Setup
1. Sign up for a Cloudinary account
2. Navigate to your dashboard
3. Copy your Cloud Name, API Key, and API Secret
4. Add these credentials to your backend `.env` file

#### JWT Secret
Generate a secure random string for your JWT secret:
```bash
node -e "console.log(require('crypto').randomBytes(32).toString('hex'))"
```

## Usage
* Open `http://localhost:5173` to view the app in the browser
* **Sign Up**: Create a new account with your email and password
* **Log In**: Access your account with your credentials
* **Start Chatting**: Select a user from the sidebar to start a conversation
* **Send Messages**: Type your message and press Enter or click Send
* **Share Images**: Click the image icon to upload and share images
* **Update Profile**: Go to the Profile page to update your profile picture
* **See Online Users**: Users currently online are highlighted in the sidebar

## Deployment

### Backend (Render)
1. Push your code to GitHub
2. Create a new Web Service on Render
3. Connect your GitHub repository
4. Set Root Directory to `backend`
5. Add all environment variables
6. Deploy!

### Frontend (Netlify)
1. Build your frontend: `npm run build`
2. Deploy the `dist` folder to Netlify
3. Add `VITE_API_URL` environment variable pointing to your Render backend URL
4. Configure build settings:
   - Base directory: `frontend`
   - Build command: `npm run build`
   - Publish directory: `frontend/dist`

## API Endpoints

### Authentication
* `POST /api/auth/signup` - Register a new user
* `POST /api/auth/login` - Login user
* `POST /api/auth/logout` - Logout user
* `GET /api/auth/check` - Check authentication status
* `PUT /api/auth/update-profile` - Update user profile

### Messages
* `GET /api/messages/user` - Get all users for sidebar
* `GET /api/messages/:id` - Get messages with a specific user
* `POST /api/messages/send/:id` - Send a message to a user

## Project Structure
```
chat_app/
├── backend/
│   ├── src/
│   │   ├── controller/
│   │   │   ├── auth.controller.js
│   │   │   └── message.controller.js
│   │   ├── lib/
│   │   │   ├── cloudinary.js
│   │   │   ├── db.js
│   │   │   └── socket.js
│   │   ├── middleware/
│   │   │   └── auth.middleware.js
│   │   ├── models/
│   │   │   ├── message.model.js
│   │   │   └── user.model.js
│   │   ├── routes/
│   │   │   ├── auth.routes.js
│   │   │   └── message.routes.js
│   │   ├── utils/
│   │   │   └── utils.js
│   │   └── index.js
│   ├── package.json
│   └── .env
├── frontend/
│   ├── src/
│   │   ├── components/
│   │   ├── lib/
│   │   ├── pages/
│   │   ├── store/
│   │   ├── App.jsx
│   │   └── main.jsx
│   ├── package.json
│   └── .env
└── README.md
```

## Features in Detail

### Real-Time Communication
The application uses Socket.IO for bidirectional communication between the client and server, enabling:
- Instant message delivery
- Real-time online/offline status updates
- Typing indicators (future enhancement)
- Message read receipts (future enhancement)

### Security Features
- Passwords are hashed using bcrypt before storage
- JWT tokens stored in HTTP-only cookies
- Protected API routes with authentication middleware
- CORS configured for cross-origin requests
- Secure cookie settings with SameSite and Secure flags

## Future Enhancements
- [ ] Typing indicators
- [ ] Message read receipts
- [ ] Group chat functionality
- [ ] Voice messages
- [ ] Video calls
- [ ] Message search
- [ ] Emoji reactions
- [ ] Message deletion and editing
- [ ] Push notifications

## Troubleshooting

### Common Issues

**Backend not connecting to MongoDB:**
- Verify your MongoDB connection string
- Check if your IP is whitelisted in MongoDB Atlas
- Ensure database user has proper permissions

**Frontend can't connect to backend:**
- Verify `VITE_API_URL` is set correctly
- Check CORS settings in backend
- Ensure both servers are running

**Cookies not being set:**
- Verify `credentials: true` in CORS configuration
- Check `withCredentials: true` in axios configuration
- Ensure `sameSite: "none"` and `secure: true` for production

## Contact
**Email**: [riddhic164@gmail.com](mailto:riddhic164@gmail.com)  
**Project Link**: [https://github.com/Riddhi-chavan/chat_app](https://github.com/Riddhi-chavan/chat_app)  
**Live Demo**: [https://frolicking-zabaione-b66282.netlify.app](https://frolicking-zabaione-b66282.netlify.app)

---

Thank you for checking out my project! If you have any suggestions or find issues, feel free to open an issue or submit a pull request. Your feedback is highly appreciated!


