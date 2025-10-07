Store Rating System
Overview
A full-stack web application that allows users to browse and rate stores, while providing store owners with insights into customer feedback. The system includes role-based access control with different dashboards for users, store owners, and administrators.

Features
User Roles
Admin: Manage all users and stores, view system statistics
Store Owner: View and analyze customer ratings for their store
User: Browse stores, leave ratings and comments
Key Features
Authentication & Authorization: Secure login with role-based access
Store Browsing: Search and filter stores by name, rating, etc.
Rating System: Users can rate stores and leave comments
Owner Dashboard: View all ratings with sorting options (by date/rating)
Admin Dashboard: Comprehensive user and store management
Responsive Design: Mobile-friendly interface using Tailwind CSS
Tech Stack
Frontend
React
React Router DOM
Tailwind CSS
Vite
Axios
React Hot Toast
Lucide React (icons)
Backend
Node.js
Express.js
MySQL
JSON Web Tokens (JWT)
bcryptjs
Project Structure
├── BACKEND
│   ├── database            # SQL scripts for database setup
│   ├── src
│   │   ├── controllers     # Business logic
│   │   ├── db              # Database connection
│   │   ├── middlewares     # Auth and validation middlewares
│   │   ├── models          # Data models
│   │   └── routes          # API routes
│   ├── server.js           # Entry point
│   └── package.json        # Backend dependencies
└── FRONTEND
    ├── public              # Static assets
    ├── src
    │   ├── assets          # Images and other assets
    │   ├── components      # Reusable UI components
    │   ├── contexts        # React contexts (Auth, etc.)
    │   ├── hooks           # Custom React hooks
    │   ├── pages           # Page components
    │   ├── services        # API service functions
    │   └── utils           # Utility functions
    ├── index.html          # HTML template
    └── package.json        # Frontend dependencies
Installation
Prerequisites
Node.js (v16 or higher)
MySQL (v8 or higher)
Backend Setup
Navigate to the backend directory:

cd BACKEND
Install dependencies:

npm install
Create a .env file in the backend directory with the following variables:

PORT=3000
DB_HOST=localhost
DB_USER=your_mysql_username
DB_PASSWORD=your_mysql_password
DB_NAME=store_rating_system
JWT_SECRET=your_jwt_secret
Set up the database using the SQL scripts in the database folder or run:

node setup-database.js
Start the backend server:

npm start
Frontend Setup
Navigate to the frontend directory:

cd FRONTEND
Install dependencies:

npm install
Start the development server:

npm run dev
The application will be available at http://localhost:5173 or http://localhost:5174

Usage
User Registration and Login
Register a new account with your email and password
Log in with your credentials
You'll be redirected to the appropriate dashboard based on your role
Store Browsing and Rating (User)
Browse available stores on the user dashboard
Search for stores by name or filter by rating
Click on a store to view details
Rate the store and leave a comment
Store Management (Owner)
View your store dashboard
See all customer ratings for your store
Sort ratings by date or rating value
Update your store profile information
Admin Functions
Manage users (view, edit, delete)
Manage stores (view, edit, delete)
View system statistics
API Endpoints
Authentication
POST /api/auth/register - Register a new user
POST /api/auth/login - Login a user
GET /api/auth/me - Get current user info
Stores
GET /api/stores/public - Get all public stores
GET /api/stores/public/authenticated - Get all stores with user ratings
GET /api/stores/profile - Get store profile for owner
POST /api/stores/profile - Create/update store profile
Ratings
GET /api/ratings/:storeId - Get ratings for a store
POST /api/ratings/:storeId - Create/update a rating
DELETE /api/ratings/:storeId - Delete a rating
GET /api/owner/my-ratings - Get all ratings for owner's store
Admin
GET /api/admin/users - Get all users
GET /api/admin/stores - Get all stores
DELETE /api/admin/users/:id - Delete a user
DELETE /api/admin/stores/:id - Delete a store

