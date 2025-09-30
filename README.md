🍔 Building an Online Food Ordering Application with MERN
🔹 Introduction

In this project, I built a full-stack food ordering system using the MERN stack (MongoDB, Express, React, Node.js). The application allows users to browse food items, add them to a cart, and place orders with Stripe payment or Cash on Delivery. It also has an Admin panel for managing foods and tracking orders.

This project gave me hands-on experience with authentication, API development, image uploads, and real-time order management — along with writing clear documentation so others can set it up easily.

🔹 Features
👨‍💻 User Side

Register and login with JWT authentication

Browse food items by category

Add to cart / remove from cart

Place orders with Stripe or Cash on Delivery

View past orders and payment status

🛠️ Admin Side

Secure login for admins

Add new food items (with image upload using Multer)

List and remove foods

View all user orders

Update order status (e.g., Preparing → Out for Delivery → Completed)

🔹 Tech Stack

Frontend: React + Vite, Tailwind CSS

Backend: Node.js + Express

Database: MongoDB (Mongoose ODM)

Auth: JWT + bcrypt for password hashing

Payments: Stripe API

File Upload: Multer (images stored in backend server)

🔹 How It Works

1. User Flow

User signs up or logs in.

Browses food menu and adds items to cart.

Places an order → chooses payment (Stripe / COD).

Backend creates an order and stores it in MongoDB.

User can track order status in their dashboard.

2. Admin Flow

Admin logs in with secure credentials.

Adds food items with details + image.

Manages all incoming orders.

Updates status, which reflects in the user’s dashboard.

🔹 API Endpoints
🔸 User APIs

POST /api/user/register → Register new user

POST /api/user/login → Login and get JWT token

🔸 Food APIs

GET /api/food/list → Get all foods

POST /api/food/add → Add new food (admin only)

POST /api/food/remove → Remove a food (admin only)

🔸 Cart APIs

POST /api/cart/add → Add item to cart (auth required)

POST /api/cart/remove → Remove item from cart

POST /api/cart/get → Get user’s cart

🔸 Order APIs

POST /api/order/place → Place an order (Stripe)

POST /api/order/placecod → Place an order (Cash on Delivery)

POST /api/order/verify → Verify Stripe payment

POST /api/order/userorders → View all orders for a user

POST /api/order/status → Update order status (admin)

🔹 Setup Guide
📦 Prerequisites

Node.js LTS

MongoDB Atlas URI

Stripe API Keys

⚙️ Installation

Clone repo:

git clone https://github.com/<your-username>/food-delivery.git
cd food-delivery


Create .env in backend:

MONGODB_URI=your_mongo_uri
JWT_SECRET=your_secret
STRIPE_SECRET_KEY=your_stripe_secret


Install dependencies:

cd backend && npm install
cd frontend && npm install


Start servers:

# backend
npm run server
# frontend
npm run dev

🔹 Example Workflow
Add a Food Item (Admin)

Login as admin, get JWT token.

Send POST /api/food/add with form-data:

name = Burger

description = Spicy chicken burger

price = 350

category = Fast Food

image = (upload file)

Response:

{
  "success": true,
  "message": "Food Added"
}

🔹 Learning Outcomes

Implementing JWT auth and secure routes

Handling image uploads with Multer

Integrating Stripe payments

Writing clear setup documentation for developers and admins

Managing frontend and backend as separate modules

🔹 Conclusion

This project helped me practice full-stack development and technical documentation. By building both user and admin sides, I understood real-world problems like authentication, payments, and data consistency
