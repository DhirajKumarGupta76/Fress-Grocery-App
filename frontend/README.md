# React + Vite

This template provides a minimal setup to get React working in Vite with HMR and some ESLint rules.

Currently, two official plugins are available:

- [@vitejs/plugin-react](https://github.com/vitejs/vite-plugin-react/blob/main/packages/plugin-react) uses [Babel](https://babeljs.io/) (or [oxc](https://oxc.rs) when used in [rolldown-vite](https://vite.dev/guide/rolldown)) for Fast Refresh
- [@vitejs/plugin-react-swc](https://github.com/vitejs/vite-plugin-react/blob/main/packages/plugin-react-swc) uses [SWC](https://swc.rs/) for Fast Refresh

## React Compiler

The React Compiler is not enabled on this template because of its impact on dev & build performances. To add it, see [this documentation](https://react.dev/learn/react-compiler/installation).

## Expanding the ESLint configuration

If you are developing a production application, we recommend using TypeScript with type-aware lint rules enabled. Check out the [TS template](https://github.com/vitejs/vite/tree/main/packages/create-vite/template-react-ts) for information on how to integrate TypeScript and [`typescript-eslint`](https://typescript-eslint.io) in your project.


 # 🛒 Fress Grocery App

A full-stack **online grocery e-commerce platform** built using the **MERN stack**. Fress Grocery App allows customers to browse grocery products, manage their shopping cart, place orders, and make online payments.

The project also includes a dedicated **Admin Dashboard** for managing products and orders.

---

## 📌 Project Overview

**Fress Grocery App** is designed to provide a complete online grocery shopping experience.

The application is divided into three major parts:

* 🛍️ **Frontend** — Customer-facing grocery shopping application
* ⚙️ **Backend** — REST API, authentication, products, cart, orders and payment processing
* 👨‍💼 **Admin Dashboard** — Product and order management

The project follows a client-server architecture where the React frontend communicates with the Node.js/Express backend through REST APIs.

---

## ✨ Features

### 👤 User Features

* User registration and login
* User authentication
* Browse grocery products
* View product information
* Product listing
* Add products to cart
* Increase/decrease product quantity
* Remove products from cart
* View cart total
* Place grocery orders
* Select payment method
* Online payment integration
* Cash on Delivery support
* View order information
* Order history
* User-specific data

---

### 🛍️ Product Features

* Product listing
* Product categories
* Product images
* Product pricing
* Product quantity management
* Product availability
* Product details
* Admin product creation
* Admin product updating
* Admin product deletion

---

### 🛒 Shopping Cart

The cart system allows customers to:

1. Select a grocery product
2. Add it to the cart
3. Change quantity
4. Remove products
5. Review selected products
6. Calculate the total amount
7. Continue to checkout

The cart communicates with the backend APIs so that product and user information can be processed securely.

---

### 📦 Order Management

Customers can create grocery orders containing:

* Customer information
* Ordered products
* Product quantities
* Total amount
* Payment method
* Delivery information
* Order notes
* Delivery date
* Order ID
* Order status

The backend generates a unique order identifier for each order.

Example:

```text
ORD-xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx
```

---

### 💳 Payment System

The application supports online payment processing through **Stripe**.

The checkout flow is approximately:

```text
Customer
   ↓
Shopping Cart
   ↓
Checkout
   ↓
Order Details
   ↓
Payment Method
   ↓
Stripe / Cash on Delivery
   ↓
Order Created
   ↓
Order Management
```

For Cash on Delivery orders, the payment method is stored as:

```text
Cash on Delivery
```

---

### 👨‍💼 Admin Dashboard

The project contains a separate admin application.

Administrators can manage the grocery store from the dashboard.

#### Product Management

* Add new products
* Update products
* Delete products
* Manage product information
* Manage product availability

#### Order Management

* View customer orders
* View order details
* Manage order status
* Process customer orders

This provides a separate management interface from the customer-facing application.

---

## 🏗️ Project Architecture

```text
                    ┌─────────────────────┐
                    │      Customer       │
                    └──────────┬──────────┘
                               │
                               ▼
                    ┌─────────────────────┐
                    │   React Frontend    │
                    │      Vite            │
                    └──────────┬──────────┘
                               │
                         REST API Calls
                               │
                               ▼
                    ┌─────────────────────┐
                    │ Node.js + Express   │
                    │      Backend        │
                    └──────┬─────┬────────┘
                           │     │
              ┌────────────┘     └────────────┐
              ▼                               ▼
      ┌───────────────┐               ┌──────────────┐
      │    MongoDB    │               │    Stripe    │
      │   Database    │               │   Payments   │
      └───────────────┘               └──────────────┘

                           ▲
                           │
                       REST APIs
                           │
                    ┌──────┴───────┐
                    │    Admin     │
                    │   Dashboard  │
                    └──────────────┘
```

---

## 🛠️ Technology Stack

### Frontend

* React.js
* Vite
* JavaScript
* Tailwind CSS
* HTML5
* CSS3
* React components
* REST API integration

### Backend

* Node.js
* Express.js
* JavaScript
* REST APIs
* MongoDB
* Mongoose
* Middleware
* Authentication
* CORS
* Environment variables

### Database

* MongoDB
* MongoDB Atlas
* Mongoose ODM

### Payment

* Stripe

### Email

* Nodemailer
* Gmail SMTP

### Background Processing

* RabbitMQ
* Message consumers/producers

### Development Tools

* Git
* GitHub
* VS Code
* Postman
* Vercel
* Render

---

## 📁 Project Structure

```text
Fress-Grocery-App/
│
├── frontend/
│   ├── src/
│   │   ├── components/
│   │   ├── pages/
│   │   ├── assets/
│   │   ├── context/
│   │   ├── services/
│   │   └── App.jsx
│   │
│   ├── package.json
│   └── ...
│
├── backend/
│   ├── controllers/
│   ├── middleware/
│   ├── models/
│   ├── routes/
│   ├── config/
│   ├── utils/
│   ├── server.js
│   └── package.json
│
├── admin/
│   ├── src/
│   │   ├── components/
│   │   ├── pages/
│   │   └── ...
│   │
│   ├── package.json
│   └── ...
│
└── README.md
```

---

# 🔄 Application Flow

## 1. User Opens the Website

The customer accesses the React frontend.

```text
Browser
   ↓
React Application
   ↓
Product API
   ↓
Express Backend
   ↓
MongoDB
   ↓
Products returned to frontend
```

The frontend displays the available grocery products.

---

## 2. User Adds Product to Cart

```text
Product
   ↓
Add to Cart
   ↓
Cart State
   ↓
Backend API
   ↓
Database
```

The selected product and quantity are associated with the customer's cart.

---

## 3. User Proceeds to Checkout

The customer reviews:

* Products
* Quantities
* Prices
* Total amount
* Customer information
* Delivery information
* Payment method

---

## 4. Order Creation

The frontend sends order information to the backend.

Example order information:

```javascript
{
    customer,
    items,
    paymentMethod,
    notes,
    deliveryDate
}
```

The backend processes the request and creates an order.

A unique order ID is generated:

```text
ORD-xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx
```

---

## 5. Payment Processing

For online payment:

```text
Frontend
   ↓
Backend
   ↓
Stripe
   ↓
Payment
   ↓
Order Confirmation
```

For Cash on Delivery:

```text
Frontend
   ↓
Backend
   ↓
Order Created
   ↓
Cash on Delivery
```

---

## 6. Order Processing

After an order is created, the backend can process related operations such as:

```text
Order Created
      ↓
Order Data Saved
      ↓
Email / Notification Processing
      ↓
Admin Dashboard
      ↓
Order Status Management
```

RabbitMQ is used for background message processing for operations such as email and order-status related tasks.

---

# 🗄️ Database

The application uses **MongoDB** as the primary database.

MongoDB Atlas can be used for cloud database hosting.

Mongoose is used to define schemas and communicate with MongoDB.

Typical application data includes:

```text
Users
Products
Cart
Orders
```

---

# 🔐 Authentication

The application contains user authentication functionality.

The general authentication flow is:

```text
User
 ↓
Login / Register
 ↓
Backend API
 ↓
Authentication
 ↓
User Data
 ↓
Authenticated Application
```

Protected backend routes can use authentication middleware to verify the user's access before processing requests.

---

# 🔌 Backend API Structure

The backend is organized using Express routes.

Major route groups include:

```text
/api/user
/api/items
/api/cart
/api/orders
```

The exact available endpoints may change as the project develops.

The backend separates responsibilities into:

```text
Routes
   ↓
Controllers
   ↓
Models
   ↓
MongoDB
```

---

# 📧 Email System

The backend includes email functionality using **Nodemailer**.

Email-related operations can include:

* User-related emails
* OTP emails
* Welcome emails
* Order status emails
* Order confirmation emails

The project also uses RabbitMQ consumers to process different email-related tasks.

---

# 📨 RabbitMQ

RabbitMQ is used for asynchronous/background processing.

The backend includes consumers for operations such as:

```text
Email Consumer
Welcome Consumer
OTP Consumer
Order Status Consumer
```

A simplified architecture is:

```text
Main Backend
     ↓
RabbitMQ Producer
     ↓
Message Queue
     ↓
Consumer
     ↓
Email / Background Task
```

This helps separate time-consuming background operations from the main request-response cycle.

---

# 👨‍💼 Admin Architecture

The admin application communicates with the same backend API.

```text
                 ┌───────────────┐
                 │    Backend    │
                 └───────┬───────┘
                         │
              ┌──────────┴──────────┐
              │                     │
              ▼                     ▼
       Customer Frontend      Admin Dashboard
```

The customer application is responsible for shopping, while the admin application is responsible for store management.

---

# 🌐 Deployment

The project can be deployed as separate services.

### Backend

```text
https://fress-grocery-app-backend.onrender.com
```

### Customer Frontend

```text
https://fress-grocery-app-frontend.onrender.com
```

### Admin Dashboard

```text
https://fress-grocery-app-admin.onrender.com
```

The frontend communicates with the deployed backend using an environment variable such as:

```env
VITE_BACKEND_URL=https://your-backend-url
```

---

# ⚙️ Environment Variables

Create a `.env` file in the backend.

Example:

```env
PORT=4000

MONGODB_URI=your_mongodb_connection_string

JWT_SECRET=your_jwt_secret

STRIPE_SECRET_KEY=your_stripe_secret_key

SMTP_HOST=smtp.gmail.com
SMTP_PORT=465
SMTP_USER=your_email
SMTP_PASS=your_app_password

ALLOWED_ORIGINS=http://localhost:5173,http://localhost:5174
```

Frontend:

```env
VITE_BACKEND_URL=http://localhost:4000
```

> Never commit `.env` files or API keys, database credentials, SMTP passwords, JWT secrets, or Stripe secret keys to GitHub.

---

# 🚀 Installation

## Prerequisites

Make sure you have installed:

* Node.js
* npm
* MongoDB / MongoDB Atlas account
* Git
* VS Code
* Stripe account if online payment is required
* RabbitMQ if running the complete background-processing system locally

---

## 1. Clone the Repository

```bash
git clone https://github.com/DhirajKumarGupta76/Fress-Grocery-App.git
```

```bash
cd Fress-Grocery-App
```

---

## 2. Setup Backend

```bash
cd backend
```

Install dependencies:

```bash
npm install
```

Create your `.env` file and configure the required environment variables.

Start the backend:

```bash
node server.js
```

The backend runs locally on:

```text
http://localhost:4000
```

---

## 3. Setup Frontend

Open another terminal:

```bash
cd frontend
```

Install dependencies:

```bash
npm install
```

Configure:

```env
VITE_BACKEND_URL=http://localhost:4000
```

Start the frontend:

```bash
npm run dev
```

---

## 4. Setup Admin

Open another terminal:

```bash
cd admin
```

Install dependencies:

```bash
npm install
```

Configure the backend URL if required:

```env
VITE_BACKEND_URL=http://localhost:4000
```

Start the admin application:

```bash
npm run dev
```

---

# 🔗 Local Development

After starting all applications:

```text
Customer Frontend
        │
        │
        ▼
http://localhost:5173
        │
        ▼
Backend API
http://localhost:4000
        │
        ▼
MongoDB
```

Admin:

```text
Admin Dashboard
        │
        ▼
Backend API
http://localhost:4000
```

---

# 🧪 API Testing

The backend APIs can be tested using **Postman**.

Recommended testing flow:

```text
1. User Registration
        ↓
2. User Login
        ↓
3. Get Products
        ↓
4. Add Product / Cart
        ↓
5. Update Cart
        ↓
6. Create Order
        ↓
7. Payment
        ↓
8. Check Order
        ↓
9. Admin Order Management
```

---

# 🔒 CORS

Because the project contains separate frontend, admin and backend applications, CORS configuration is required.

Example:

```env
ALLOWED_ORIGINS=http://localhost:5173,http://localhost:5174
```

For production, add the deployed frontend and admin origins.

Example:

```env
ALLOWED_ORIGINS=https://fress-grocery-app-frontend.onrender.com,https://fress-grocery-app-admin.onrender.com
```

---

# 📊 Key Backend Responsibilities

The backend is responsible for:

* API handling
* User authentication
* Product management
* Cart operations
* Order creation
* Payment processing
* Database operations
* Email processing
* Order status processing
* CORS configuration
* Admin operations

---

# 🧩 Important Technologies Explained

### React.js

Used to build the customer-facing and admin user interfaces.

### Node.js

Provides the JavaScript runtime for the backend.

### Express.js

Used to create REST APIs and handle HTTP requests.

### MongoDB

Stores application data such as users, products, carts and orders.

### Mongoose

Provides schemas and database interaction between Node.js and MongoDB.

### Stripe

Handles online payment processing.

### Nodemailer

Used for sending emails.

### RabbitMQ

Used for asynchronous/background processing.

### Tailwind CSS

Used to build and style the frontend UI.

### Render

Used to deploy the backend and frontend applications.

### Vercel

Can be used for frontend deployment where applicable.

---

# 🧠 What I Learned From This Project

Building this project helped in understanding:

* Full-stack MERN development
* React component architecture
* Frontend-backend communication
* REST API development
* MongoDB database operations
* Mongoose schemas
* Authentication
* Middleware
* CORS
* Environment variables
* Shopping cart logic
* Order processing
* Payment integration
* Stripe integration
* Email services
* RabbitMQ
* Admin dashboards
* Deployment
* Production environment configuration
* Debugging deployment issues
* Git and GitHub workflow

---

# 🐛 Common Development Issues

### MongoDB Connection Error

Check:

```text
MongoDB URI
MongoDB Atlas IP access
Network connection
Database credentials
```

### CORS Error

Check:

```text
ALLOWED_ORIGINS
Frontend URL
Admin URL
Backend URL
```

### Frontend Cannot Reach Backend

Check:

```env
VITE_BACKEND_URL
```

Make sure the frontend is not accidentally using:

```text
localhost
```

after production deployment.

### Stripe URL Error

Stripe URLs must use a valid URL format such as:

```text
https://example.com
```

rather than an incomplete or invalid URL.

### SMTP Error on Deployment

Cloud hosting environments may restrict outbound SMTP connections. Check the hosting provider's networking restrictions and SMTP configuration.

---

# 🔮 Future Improvements

Possible improvements for the project:

* Product search
* Advanced product filtering
* Product reviews and ratings
* Wishlist
* Coupon system
* Inventory management
* Low-stock alerts
* Delivery tracking
* User profile management
* Multiple delivery addresses
* Order cancellation
* Order refund system
* Better payment verification
* Admin analytics
* Sales charts
* Customer analytics
* Email templates
* Push notifications
* Better mobile responsiveness
* Automated testing
* CI/CD pipeline

---

# 📸 Screenshots

Add screenshots of the major application pages here.

Recommended screenshots:

```text

1. Home Page
2. Product Listing
3. Product Details
4. Shopping Cart
5. Checkout
6. Order Confirmation
7. User Orders
8. Admin Dashboard
9. Product Management
10. Order Management
```

Example:

```md
## 📸 Screenshots

### Home Page

![Home Page](./screenshots/home.png)

### Product Page

![Product Page](./screenshots/products.png)

### Shopping Cart

![Cart](./screenshots/cart.png)

### Admin Dashboard

![Admin Dashboard](./screenshots/admin-dashboard.png)
```

---

# 📁 Recommended Repository Organization

```text
Fress-Grocery-App
│
├── frontend
│   ├── src
│   ├── public
│   ├── package.json
│   └── README.md
│
├── backend
│   ├── controllers
│   ├── middleware
│   ├── models
│   ├── routes
│   ├── config
│   ├── utils
│   ├── server.js
│   └── package.json
│
├── admin
│   ├── src
│   ├── public
│   ├── package.json
│   └── README.md
│
├── screenshots
│
├── .gitignore
└── README.md
```

---

# 🌍 Live Applications

### Customer Application

[Open Customer Application](https://fress-grocery-app-frontend.onrender.com)

### Admin Dashboard

[Open Admin Dashboard](https://fress-grocery-app-admin.onrender.com)

### Backend API

[Open Backend](https://fress-grocery-app-backend.onrender.com)

### GitHub Repository

[View Source Code](https://github.com/DhirajKumarGupta76/Fress-Grocery-App)

---

# 👨‍💻 Author

**Dhiraj Kumar Gupta**

B.Tech Computer Science & Engineering

Interested in:

* Full-Stack Development
* MERN Stack
* Artificial Intelligence & Machine Learning
* Software Development

GitHub:

[github.com/DhirajKumarGupta76](https://github.com/DhirajKumarGupta76)

---

# ⭐ Project

If you find this project useful, consider giving the repository a ⭐ on GitHub.

---

## 📄 License

This project is created for learning, development, and portfolio purposes.
