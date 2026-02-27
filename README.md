## 📁 Project Structure

```
Food-Ordering-App-MERN/
├── Program Files/          # Main application code
│   ├── client/            # React frontend
│   └── server/            # Node.js/Express backend
├── Documentation/         # Project documentation
├── Video Demo/           # Demo videos
└── README.md            # This file
```

## 🚀 Getting Started

### Prerequisites
- Node.js (v14+)
- npm or yarn
- MongoDB (local or Atlas)

### Installation

#### Backend Setup
```bash
cd "Program Files/server"
npm install
# Configure your MongoDB connection in index.js
npm start
```

#### Frontend Setup
```bash
cd "Program Files/client"
npm install
npm start
```

The app will run on `http://localhost:3000`

## 📋 Features

### Client (React)
- **Authentication**: User login and registration
- **User Roles**: 
  - Customers: Browse restaurants, order food, manage cart and profile
  - Restaurant Owners: Manage menu items and view orders
  - Admins: Manage users, restaurants, products, and orders
- **Components**: Navbar, Footer, Popular Restaurants display
- **Pages**: Home, Authentication, Customer dashboard, Restaurant dashboard, Admin panel

### Server (Node.js/Express)
- RESTful API endpoints
- MongoDB schema for users, restaurants, products, and orders
- Authentication and authorization
- Order management

## 🛠️ Tech Stack

**Frontend:**
- React.js
- Context API for state management
- CSS for styling

**Backend:**
- Node.js
- Express.js
- MongoDB
- Schema-based data validation

## 📂 Key Directories

- `Program Files/client/src/pages/` - Page components (admin, customer, restaurant roles)
- `Program Files/client/src/components/` - Reusable components
- `Program Files/client/src/context/` - Global state management
- `Program Files/server/` - Backend API and database configuration

## 🎯 User Roles

1. **Customer**: Browse restaurants, add items to cart, place orders, view profile
2. **Restaurant Owner**: Create/edit menu items, manage orders
3. **Admin**: Manage all users, restaurants, products, and orders

## 📝 Notes

- Refer to `DocumentationAVVL/` for detailed documentation
- Check `Video Demo/` for application walkthrough

## 📧 Support

For issues or questions, please refer to the documentation or check the codebase comments.

---

**Happy ordering! 🍕🍔🍜**
