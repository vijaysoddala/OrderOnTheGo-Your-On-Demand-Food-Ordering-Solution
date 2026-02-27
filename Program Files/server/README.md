# Food Ordering App - Server (Backend)

Node.js and Express.js backend API for the Food Ordering App MERN stack application.

## 📋 Overview

This server provides RESTful API endpoints for managing users, restaurants, food items, orders, and cart functionality. Built with Express.js and MongoDB.

## 🛠️ Tech Stack

- **Runtime**: Node.js
- **Framework**: Express.js
- **Database**: MongoDB
- **Authentication**: bcrypt (password hashing)
- **Middleware**: 
  - body-parser
  - CORS
  - express.json()

## 📁 File Structure

```
server/
├── index.js          # Main server file with all API endpoints
├── Schema.js         # MongoDB schemas
├── package.json      # Dependencies
└── README.md         # This file
```

## 🚀 Installation & Setup

### Prerequisites
- Node.js (v14+)
- MongoDB (running locally on port 27017 or MongoDB Atlas)
- npm or yarn

### Steps

1. **Install dependencies**
   ```bash
   npm install
   ```

2. **Configure MongoDB**
   - Default: `mongodb://localhost:27017/foodDelivery`
   - Update the connection string in `index.js` if using MongoDB Atlas or different local setup

3. **Start the server**
   ```bash
   npm start
   ```
   - Server runs on **PORT 6001**
   - Console output: `running @ 6001`

## 📚 Database Collections

### User Schema
- `username` - User's display name
- `email` - Unique email address
- `password` - Hashed password (bcrypt)
- `usertype` - 'customer', 'restaurant', or 'admin'
- `approval` - 'pending', 'approved', or 'rejected'

### Restaurant Schema
- `ownerId` - Reference to User ID
- `title` - Restaurant name
- `address` - Restaurant location
- `mainImg` - Restaurant image URL
- `menu` - Array of menu categories

### FoodItem Schema
- `title` - Item name
- `description` - Item details
- `itemImg` - Item image URL
- `category` - Type (veg, non-veg, beverage)
- `menuCategory` - Custom category
- `restaurantId` - Reference to Restaurant
- `price` - Item price
- `discount` - Discount percentage
- `rating` - Customer rating

### Order Schema
- `userId`, `name`, `email`, `mobile` - Customer details
- `address`, `pincode` - Delivery address
- `restaurantId`, `restaurantName` - Restaurant info
- `foodItemId`, `foodItemName`, `foodItemImg` - Item details
- `quantity`, `price`, `discount` - Order details
- `paymentMethod` - Payment type
- `orderDate` - Order timestamp
- `orderStatus` - 'order placed', 'preparing', 'out for delivery', 'delivered', 'cancelled'

### Cart Schema
- `userId` - Customer ID
- `restaurantId`, `restaurantName` - Restaurant info
- `foodItemId`, `foodItemName`, `foodItemImg` - Item details
- `quantity`, `price`, `discount` - Item details

### Admin Schema
- `categories` - Array of food categories
- `promotedRestaurants` - Array of promoted restaurant IDs

## 🔌 API Endpoints

### Authentication
- `POST /register` - Register new user
- `POST /login` - User login

### User Management
- `GET /fetch-users` - Get all users
- `GET /fetch-user-details/:id` - Get specific user
- `POST /approve-user` - Approve restaurant (Admin)
- `POST /reject-user` - Reject restaurant (Admin)

### Restaurant Management
- `GET /fetch-restaurants` - Get all restaurants
- `GET /fetch-restaurant/:id` - Get restaurant by ID
- `GET /fetch-restaurant-details/:id` - Get restaurant by owner ID

### Food Items
- `GET /fetch-items` - Get all food items
- `GET /fetch-item-details/:id` - Get specific item
- `POST /add-new-product` - Add new food item
- `PUT /update-product/:id` - Update food item

### Orders
- `GET /fetch-orders` - Get all orders
- `POST /place-cart-order` - Place order from cart
- `PUT /update-order-status` - Update order status
- `PUT /cancel-order` - Cancel order

### Cart
- `GET /fetch-cart` - Get all cart items
- `POST /add-to-cart` - Add item to cart
- `PUT /remove-item` - Remove item from cart

### Admin
- `GET /fetch-categories` - Get all food categories
- `POST /update-promote-list` - Update promoted restaurants
- `GET /fetch-promoted-list` - Get promoted restaurants

## 📦 Dependencies

```json
{
  "express": "^4.x",
  "mongoose": "^6.x",
  "bcrypt": "^5.x",
  "body-parser": "^1.x",
  "cors": "^2.x"
}
```

## 🔐 Security Notes

- Passwords are hashed using bcrypt (salt rounds: 10)
- CORS enabled for frontend communication
- Input validation recommended (consider adding express-validator)

## 🐛 Error Handling

- All endpoints return appropriate HTTP status codes
- Server errors return 500 with error messages
- Validation errors return 400 status

## 📝 Notes

- MongoDB must be running before starting the server
- Default database: `foodDelivery`
- CORS is enabled for frontend communication
- Request body limit: 30MB

## 🚀 Future Improvements

- Add request validation middleware
- Implement JWT authentication
- Add pagination for GET endpoints
- Add rate limiting
- Implement transaction support for orders
- Add logging system

---

**Server is ready to support the Food Ordering App frontend!** 🚀